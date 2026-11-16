# 🔷 Template Monolítico Modular (Multi-Module Hexagonal Architecture)
#arquitetura #hexagonal #ports-and-adapters #ddd #monolito-modular #maven #design-patterns

> [!info] Visão Geral
> Este é um **template genérico** de **Monólito Modular** que combina **Arquitetura Hexagonal (Ports & Adapters)** com **Domain-Driven Design**. Cada bounded context é um **hexágono** com seus próprios módulos Maven. Duas regras são garantidas **pelo build**, não pela disciplina do time: (1) dentro de um módulo, o domínio não conhece ninguém e os adapters ficam do lado de fora; (2) entre módulos, um contexto só enxerga o **contrato público (`-api`)** do outro. O exemplo é uma **loja virtual (e-commerce)** com os contextos `pedidos` e `catalogo`. Adapte os nomes ao seu domínio.
>
> Este documento é o par do [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Clean architecture/Template Monolítico Modular (Multi-Module Clean Architecture)|Template de Clean Architecture]]. A seção 13 compara os dois.

---

## 1. O que é um Monólito Modular Hexagonal

```
Monólito Tradicional        Monólito Modular Hexagonal       Microsserviços
────────────────────        ──────────────────────────       ──────────────
Tudo num pacote único  →    1 hexágono por contexto,    →    Hexágonos em
Sem fronteiras              fronteiras fortes,               processos separados
1 deploy                    1 deploy                         N deploys

Problema:                   Vantagem:                        Custo:
big ball of mud             isolamento sem rede              rede, observabilidade,
                                                             consistência eventual
```

Cada contexto de negócio é um hexágono completo: um núcleo (domínio + aplicação), portas e adapters. O monólito é a **soma de hexágonos** que conversam só por contratos públicos.

```
                ┌──────────── bootstrap (1 deploy) ────────────┐
                │                                               │
   HTTP ──►  ┌──┴───────────────┐         ┌───────────────────┐ │
             │ PEDIDOS          │ Facade  │ CATALOGO          │ │
             │  adapter.in      │────────►│  catalogo-api     │ │
             │  application     │         │  application      │ │
             │  domain          │◄────────│  domain           │ │
             │  adapter.out     │ Eventos │  adapter.in/out   │ │
             └──────┬───────────┘         └─────────┬─────────┘ │
                    │ schema "pedidos"              │ schema "catalogo"
                    └──────────────┬────────────────┘
                              PostgreSQL (1 instância)
```

---

## 2. As duas regras inegociáveis (e as três camadas de defesa)

### Regra 1 — Intra-módulo: o domínio não conhece ninguém

```
   adapter  ──►  application  ──►  domain
   (fora)        (orquestra)       (núcleo, não depende de nada)
```

- `domain` não depende de nada (só do `shared-kernel`).
- `application` depende de `domain` e `api`. Define as **portas** (de entrada e de saída).
- `adapter` depende de `application` (implementa e chama as portas) e traz os frameworks.

### Regra 2 — Inter-módulo: só se enxerga o `-api`

```
   pedidos-application ──► catalogo-api        ✅ contrato público
   pedidos-application ──► catalogo-domain     ❌ não está no pom, não compila
   pedidos-adapter     ──► catalogo-adapter    ❌ idem
```

### As três camadas de defesa

```
Camada 1 — Maven (classpath)
  Cada módulo só enxerga o que declara no pom.
  Importar uma classe de módulo não declarado = erro de compilação.

Camada 2 — Maven Enforcer (dependências banidas)
  O pom de domain/application proíbe, inclusive transitivamente,
  Spring Web, JPA, Hibernate, Jackson etc.
  Alguém adiciona a dependência "só pra testar"? O build falha.

Camada 3 — ArchUnit (pacotes e classes)
  Pega o que o classpath não pega: adapter.in chamando adapter.out,
  uso de classe interna de outro módulo dentro do mesmo jar etc.
```

> **A frase-chave:** em um monólito modular hexagonal bem feito, o desenvolvedor não precisa lembrar das regras. O `mvn verify` lembra por ele.

---

## 3. Os 5 tipos de artefato

```
┌────────────────────┬──────────────────────────────┬───────────────────────────┐
│ Artefato           │ Responsabilidade             │ Depende de                │
├────────────────────┼──────────────────────────────┼───────────────────────────┤
│ shared-kernel      │ Kernel mínimo e estável:     │ NADA                      │
│ (1 no projeto)     │ Dinheiro, AggregateRoot,     │                           │
│                    │ DomainEvent                  │                           │
├────────────────────┼──────────────────────────────┼───────────────────────────┤
│ <ctx>-api          │ Contrato PÚBLICO do módulo:  │ shared-kernel             │
│ (por contexto)     │ Facade, DTOs, integration    │                           │
│                    │ events                       │                           │
├────────────────────┼──────────────────────────────┼───────────────────────────┤
│ <ctx>-domain       │ Núcleo: aggregates, value    │ shared-kernel             │
│                    │ objects, domain services,    │                           │
│                    │ specifications, exceptions   │                           │
├────────────────────┼──────────────────────────────┼───────────────────────────┤
│ <ctx>-application  │ Portas de entrada (use cases)│ domain + api              │
│                    │ e de saída (repositórios,    │ (+ api de outros          │
│                    │ gateways) + Application      │ contextos, se precisar)   │
│                    │ Services                     │                           │
├────────────────────┼──────────────────────────────┼───────────────────────────┤
│ <ctx>-adapter      │ Adapters de entrada          │ application               │
│                    │ (REST, listeners) e de saída │ (+ Spring Web, JPA, ...)  │
│                    │ (JPA, HTTP, eventos)         │                           │
├────────────────────┼──────────────────────────────┼───────────────────────────┤
│ shop-bootstrap     │ main(), configuração global, │ todos os adapters         │
│ (1 no projeto)     │ composição dos módulos       │                           │
└────────────────────┴──────────────────────────────┴───────────────────────────┘
```

> [!tip] Por que as portas de saída ficam na `application` e não no `domain`
> No template de Clean as interfaces (`gateways`) ficam no core. Aqui, seguindo o vocabulário hexagonal, as **portas de saída pertencem à aplicação**: o domínio fica 100% livre de interface técnica (ele só tem regra de negócio) e a aplicação declara *o que precisa do mundo externo*. Se um Domain Service precisar de algo externo (ex.: cotação de frete), a porta correspondente vai no `domain` e esse é um caso excepcional, justificado em ADR (ver anti-padrão 2 em [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Hexagonal/3. Funcionamento e Fluxo de Requisição/3.2 Guia de Decisão - Onde Colocar Cada Código/3.2.2. Sinais de Problemas na Arquitetura/3.2.2.1. Cinco Anti-padrões e Como Corrigi-los|Cinco Anti-padrões]]).

---

## 4. Estrutura Maven (visão macro)

```
shop/                                       ← raiz (aggregator)
│
├── pom.xml                                 ← POM PAI: BOM, versões, Enforcer, módulos
│
├── shared-kernel/                          ← kernel mínimo (depende de: NADA)
│
├── modules/
│   ├── pedidos/                            ← bounded context "Pedidos"
│   │   ├── pom.xml                         ← agregador do contexto (packaging pom)
│   │   ├── pedidos-api/
│   │   ├── pedidos-domain/
│   │   ├── pedidos-application/
│   │   └── pedidos-adapter/
│   │
│   ├── catalogo/                           ← bounded context "Catálogo"
│   │   ├── pom.xml
│   │   ├── catalogo-api/
│   │   ├── catalogo-domain/
│   │   ├── catalogo-application/
│   │   └── catalogo-adapter/
│   │
│   └── pagamentos/                         ← mesma estrutura (omitida)
│
├── shop-bootstrap/                         ← main() + composição (depende de: adapters)
│
├── architecture-tests/                     ← ArchUnit (depende de: tudo, só test)
│
└── docs/adr/                               ← decisões arquiteturais registradas
```

### 4.1 POM pai

```xml
<!-- shop/pom.xml -->
<project>
  <groupId>br.com.shop</groupId>
  <artifactId>shop</artifactId>
  <version>1.0.0</version>
  <packaging>pom</packaging>

  <modules>
    <module>shared-kernel</module>
    <module>modules/pedidos</module>
    <module>modules/catalogo</module>
    <module>modules/pagamentos</module>
    <module>shop-bootstrap</module>
    <module>architecture-tests</module>
  </modules>

  <properties>
    <java.version>21</java.version>
  </properties>

  <dependencyManagement>
    <dependencies>
      <!-- BOM do Spring Boot: versões das libs externas -->
      <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-dependencies</artifactId>
        <version>3.3.5</version>
        <type>pom</type>
        <scope>import</scope>
      </dependency>

      <!-- Módulos internos: versão em UM lugar só -->
      <dependency><groupId>br.com.shop</groupId><artifactId>shared-kernel</artifactId><version>${project.version}</version></dependency>
      <dependency><groupId>br.com.shop</groupId><artifactId>pedidos-api</artifactId><version>${project.version}</version></dependency>
      <dependency><groupId>br.com.shop</groupId><artifactId>pedidos-domain</artifactId><version>${project.version}</version></dependency>
      <dependency><groupId>br.com.shop</groupId><artifactId>pedidos-application</artifactId><version>${project.version}</version></dependency>
      <dependency><groupId>br.com.shop</groupId><artifactId>pedidos-adapter</artifactId><version>${project.version}</version></dependency>
      <dependency><groupId>br.com.shop</groupId><artifactId>catalogo-api</artifactId><version>${project.version}</version></dependency>
      <!-- ... idem para catalogo-domain, -application, -adapter ... -->
    </dependencies>
  </dependencyManagement>
</project>
```

### 4.2 POMs de cada artefato (o que cada um PODE depender)

```xml
<!-- pedidos-domain/pom.xml — o núcleo: quase vazio de propósito -->
<dependencies>
  <dependency><groupId>br.com.shop</groupId><artifactId>shared-kernel</artifactId></dependency>
  <dependency>
    <groupId>org.junit.jupiter</groupId><artifactId>junit-jupiter</artifactId><scope>test</scope>
  </dependency>
  <dependency>
    <groupId>org.assertj</groupId><artifactId>assertj-core</artifactId><scope>test</scope>
  </dependency>
</dependencies>

<build>
  <plugins>
    <!-- CAMADA 2 DE DEFESA: proíbe infraestrutura, inclusive transitiva -->
    <plugin>
      <artifactId>maven-enforcer-plugin</artifactId>
      <executions>
        <execution>
          <id>dominio-puro</id>
          <goals><goal>enforce</goal></goals>
          <configuration>
            <rules>
              <bannedDependencies>
                <excludes>
                  <exclude>org.springframework*:*</exclude>
                  <exclude>jakarta.*:*</exclude>
                  <exclude>org.hibernate*:*</exclude>
                  <exclude>com.fasterxml.jackson*:*</exclude>
                </excludes>
                <message>Domínio não pode depender de framework ou infraestrutura.</message>
              </bannedDependencies>
            </rules>
          </configuration>
        </execution>
      </executions>
    </plugin>
  </plugins>
</build>
```

```xml
<!-- pedidos-api/pom.xml — contrato público: só tipos simples -->
<dependencies>
  <dependency><groupId>br.com.shop</groupId><artifactId>shared-kernel</artifactId></dependency>
</dependencies>
<!-- Mesmo Enforcer do domain: o contrato público também não carrega framework -->
```

```xml
<!-- pedidos-application/pom.xml — portas + casos de uso -->
<dependencies>
  <dependency><groupId>br.com.shop</groupId><artifactId>pedidos-domain</artifactId></dependency>
  <dependency><groupId>br.com.shop</groupId><artifactId>pedidos-api</artifactId></dependency>

  <!-- Só o API de OUTRO contexto, nunca o domain/application dele -->
  <dependency><groupId>br.com.shop</groupId><artifactId>catalogo-api</artifactId></dependency>

  <!-- Exceção consciente: spring-tx só para @Transactional (ver seção 9) -->
  <dependency><groupId>org.springframework</groupId><artifactId>spring-tx</artifactId></dependency>
</dependencies>
<!-- Enforcer: banir jakarta.persistence, hibernate, spring-web, spring-boot-starter-* -->
```

```xml
<!-- pedidos-adapter/pom.xml — aqui os frameworks são bem-vindos -->
<dependencies>
  <dependency><groupId>br.com.shop</groupId><artifactId>pedidos-application</artifactId></dependency>
  <dependency><groupId>org.springframework.boot</groupId><artifactId>spring-boot-starter-web</artifactId></dependency>
  <dependency><groupId>org.springframework.boot</groupId><artifactId>spring-boot-starter-validation</artifactId></dependency>
  <dependency><groupId>org.springframework.boot</groupId><artifactId>spring-boot-starter-data-jpa</artifactId></dependency>
  <dependency><groupId>org.postgresql</groupId><artifactId>postgresql</artifactId><scope>runtime</scope></dependency>
  <dependency><groupId>org.flywaydb</groupId><artifactId>flyway-core</artifactId></dependency>
</dependencies>
```

```xml
<!-- shop-bootstrap/pom.xml — só junta os adapters e tem o main() -->
<dependencies>
  <dependency><groupId>br.com.shop</groupId><artifactId>pedidos-adapter</artifactId></dependency>
  <dependency><groupId>br.com.shop</groupId><artifactId>catalogo-adapter</artifactId></dependency>
  <dependency><groupId>br.com.shop</groupId><artifactId>pagamentos-adapter</artifactId></dependency>
</dependencies>
```

> [!note] Sem ciclos de módulo
> `pedidos-application → catalogo-api` e `catalogo-adapter → pedidos-api` **não formam ciclo**, porque os `-api` não dependem de nada além do kernel. O Maven recusa ciclos entre artefatos, e o `-api` é justamente o que permite dois contextos se conhecerem sem ciclo.

---

## 5. Fluxo de uma requisição (exemplo e-commerce, atravessando dois módulos)

```
┌────────────────────────────────────────────────────────────────┐
│  CLIENTE: POST /pedidos  { clienteId, itens[] }                 │
└─────────────────────────────┬──────────────────────────────────┘
                              ▼
┌────────────────────────────────────────────────────────────────┐
│  pedidos-adapter · in.web                                       │
│  PedidoController: valida formato (@Valid) → monta o Command    │
│  Chama a PORTA DE ENTRADA CriarPedidoUseCase                    │
└─────────────────────────────┬──────────────────────────────────┘
                              ▼
┌────────────────────────────────────────────────────────────────┐
│  pedidos-application                                            │
│  CriarPedidoService (implementa CriarPedidoUseCase)             │
│   1. consulta preço/estoque ──► PORTA DE SAÍDA CatalogoPort     │
│   2. Pedido.novo(...) / adicionarItem(...)   (regra no domínio) │
│   3. salva ──► PORTA DE SAÍDA PedidoRepository                  │
│   4. publica PedidoCriado ──► PORTA DE SAÍDA PublicadorEventos  │
└──────┬──────────────────────┬─────────────────────┬────────────┘
       ▼                      ▼                     ▼
┌─────────────┐   ┌────────────────────┐  ┌──────────────────────┐
│ pedidos-     │   │ pedidos-adapter    │  │ pedidos-adapter      │
│ domain       │   │ out.catalogo       │  │ out.persistence      │
│ Pedido,      │   │ CatalogoFacade-    │  │ PedidoRepositoryJpa  │
│ ItemPedido,  │   │ Adapter (ACL)      │  │ (JPA ↔ domínio)      │
│ Dinheiro...  │   └─────────┬──────────┘  └──────────┬───────────┘
└─────────────┘             │ usa só o contrato        ▼
                            ▼                    schema "pedidos"
                  ┌────────────────────┐
                  │ catalogo-api       │  ← Facade pública
                  │ CatalogoFacade     │
                  └─────────┬──────────┘
                            │ implementada em
                            ▼
                  catalogo-application (use cases do catálogo)
```

**Inversão de dependência aqui:** o `CriarPedidoService` chama `CatalogoPort` (interface que **ele mesmo** define). O `CatalogoFacadeAdapter` implementa essa porta traduzindo para o `CatalogoFacade` do outro módulo. Para o contexto `pedidos`, o catálogo é só mais um *serviço externo*, como Stripe ou um banco. Se amanhã o catálogo virar microsserviço, troca-se **um adapter**.

---

## 6. Estrutura de pastas e código por módulo

### 6.1 `shared-kernel` — o mínimo comum

```
shared-kernel/src/main/java/br/com/shop/shared/
├── Dinheiro.java            # record: BigDecimal valor + moeda (nunca double)
├── AggregateRoot.java       # base com a lista de eventos de domínio pendentes
├── DomainEvent.java         # interface: eventId, ocorridoEm
└── IntegrationEvent.java    # marker interface para eventos que cruzam módulos
```

> [!warning] Regra de ouro do kernel
> Só entra aqui o que é **estável, pequeno, sem framework e realmente compartilhado**. Se duas equipes discutem para mudar uma classe do kernel, ela provavelmente pertence a um contexto só. Kernel inchado é o caminho de volta ao big ball of mud.

```java
// shared-kernel
public abstract class AggregateRoot {
    private final List<DomainEvent> eventos = new ArrayList<>();

    protected void registrar(DomainEvent evento) { eventos.add(evento); }

    public List<DomainEvent> pullEvents() {          // entrega e limpa
        var copia = List.copyOf(eventos);
        eventos.clear();
        return copia;
    }
}
```

### 6.2 `pedidos-api` — o contrato público do módulo

```
pedidos-api/src/main/java/br/com/shop/pedidos/api/
├── PedidosFacade.java               # consultas/comandos que OUTROS módulos podem chamar
├── dto/
│   └── PedidoResumo.java            # record simples, sem regra
└── events/
    ├── PedidoCriado.java            # integration event
    └── PedidoConfirmado.java
```

```java
// pedidos-api — o que o catálogo "enxerga" do módulo pedidos
public record PedidoConfirmado(
        UUID pedidoId,
        Instant ocorridoEm,
        List<Item> itens) implements IntegrationEvent {

    public record Item(UUID produtoId, int quantidade) {}
}
```

**Regras do `-api`:** só records/interfaces/enums; **nunca** expõe entidade de domínio; mudanças aqui são **mudança de contrato** (versionar com cuidado); tudo o que está fora do `-api` é privado ao módulo.

### 6.3 `pedidos-domain` — o núcleo

```
pedidos-domain/src/main/java/br/com/shop/pedidos/domain/
├── model/
│   ├── Pedido.java              # AGGREGATE ROOT
│   ├── ItemPedido.java          # entidade filha (só o Pedido mexe nela)
│   ├── PedidoId.java            # value object (record)
│   ├── StatusPedido.java        # enum: RASCUNHO, CONFIRMADO, PAGO, CANCELADO
│   └── Cupom.java               # value object
├── service/
│   └── PoliticaDeDesconto.java  # Domain Service (regra que envolve vários objetos)
├── specification/
│   └── ClienteElegivelParaDesconto.java
├── event/
│   ├── PedidoCriadoDomainEvent.java
│   └── PedidoConfirmadoDomainEvent.java
└── exception/
    ├── DomainException.java
    ├── PedidoVazioException.java
    └── PedidoJaConfirmadoException.java
```

```java
// pedidos-domain — objeto rico: a regra mora aqui, ninguém usa setStatus()
public class Pedido extends AggregateRoot {

    private final PedidoId id;
    private final UUID clienteId;
    private final List<ItemPedido> itens = new ArrayList<>();
    private StatusPedido status = StatusPedido.RASCUNHO;

    private Pedido(PedidoId id, UUID clienteId) {
        this.id = id;
        this.clienteId = clienteId;
    }

    public static Pedido novo(UUID clienteId) {
        var pedido = new Pedido(PedidoId.novo(), clienteId);
        pedido.registrar(new PedidoCriadoDomainEvent(pedido.id));
        return pedido;
    }

    public void adicionarItem(UUID produtoId, int quantidade, Dinheiro precoUnitario) {
        garantirEditavel();
        if (quantidade <= 0) throw new IllegalArgumentException("Quantidade deve ser positiva");
        itens.add(new ItemPedido(produtoId, quantidade, precoUnitario));
    }

    public void confirmar() {                       // a regra "pedido vazio não confirma" é DAQUI
        garantirEditavel();
        if (itens.isEmpty()) throw new PedidoVazioException(id);
        this.status = StatusPedido.CONFIRMADO;
        registrar(new PedidoConfirmadoDomainEvent(id, itensSnapshot()));
    }

    public Dinheiro total() {
        return itens.stream().map(ItemPedido::subtotal).reduce(Dinheiro.ZERO, Dinheiro::somar);
    }

    private void garantirEditavel() {
        if (status != StatusPedido.RASCUNHO) throw new PedidoJaConfirmadoException(id);
    }
    // getters de leitura; sem setters públicos
}
```

**Teste de domínio (milissegundos, zero framework):**

```java
class PedidoTest {
    @Test
    void naoConfirmaPedidoVazio() {
        var pedido = Pedido.novo(UUID.randomUUID());
        assertThatThrownBy(pedido::confirmar).isInstanceOf(PedidoVazioException.class);
    }
}
```

### 6.4 `pedidos-application` — portas e casos de uso

```
pedidos-application/src/main/java/br/com/shop/pedidos/application/
├── port/
│   ├── in/                                  ← PORTAS DE ENTRADA (Primary/Driving)
│   │   ├── CriarPedidoUseCase.java
│   │   ├── ConfirmarPedidoUseCase.java
│   │   └── ConsultarPedidoQuery.java
│   └── out/                                 ← PORTAS DE SAÍDA (Secondary/Driven)
│       ├── PedidoRepository.java            # persistência
│       ├── CatalogoPort.java                # "o que eu preciso do catálogo"
│       └── PublicadorDeEventos.java         # publicação de eventos
├── service/                                 ← implementam as portas de entrada
│   ├── CriarPedidoService.java
│   └── ConfirmarPedidoService.java
├── command/
│   ├── CriarPedidoCommand.java              # record de entrada
│   └── ItemCommand.java
├── result/
│   └── PedidoCriadoResult.java              # record de saída
└── facade/
    └── PedidosFacadeService.java            # implementa PedidosFacade (do -api)
```

```java
// PORTA DE ENTRADA — vocabulário da aplicação, nada de HTTP
public interface CriarPedidoUseCase {
    PedidoCriadoResult executar(CriarPedidoCommand comando);
}

// PORTA DE SAÍDA — o que a aplicação EXIGE do mundo externo
public interface PedidoRepository {
    void salvar(Pedido pedido);
    Optional<Pedido> buscarPorId(PedidoId id);
}

// PORTA DE SAÍDA para outro módulo — modelo PRÓPRIO do contexto pedidos
public interface CatalogoPort {
    Optional<ProdutoParaVenda> buscarProduto(UUID produtoId);   // tipo definido em pedidos
    boolean temEstoque(UUID produtoId, int quantidade);
}
```

```java
// CASO DE USO — orquestra, sem regra de negócio, sem tecnologia
public class CriarPedidoService implements CriarPedidoUseCase {

    private final PedidoRepository pedidos;
    private final CatalogoPort catalogo;
    private final PublicadorDeEventos eventos;

    public CriarPedidoService(PedidoRepository pedidos, CatalogoPort catalogo,
                              PublicadorDeEventos eventos) {
        this.pedidos = pedidos;
        this.catalogo = catalogo;
        this.eventos = eventos;
    }

    @Transactional
    @Override
    public PedidoCriadoResult executar(CriarPedidoCommand cmd) {
        var pedido = Pedido.novo(cmd.clienteId());

        for (var item : cmd.itens()) {
            var produto = catalogo.buscarProduto(item.produtoId())
                    .orElseThrow(() -> new ProdutoNaoEncontradoException(item.produtoId()));
            if (!catalogo.temEstoque(item.produtoId(), item.quantidade())) {
                throw new EstoqueInsuficienteException(item.produtoId());
            }
            pedido.adicionarItem(produto.id(), item.quantidade(), produto.preco()); // regra: domínio
        }

        pedidos.salvar(pedido);
        eventos.publicar(pedido.pullEvents());           // eventos de domínio saem pela porta
        return new PedidoCriadoResult(pedido.id().valor(), pedido.total());
    }
}
```

> [!tip] Teste do caso de uso sem Spring
> `new CriarPedidoService(new PedidoRepositoryEmMemoria(), new CatalogoFake(), new PublicadorFake())` e pronto. Os fakes implementam as portas de saída. É o ganho central de testabilidade da Hexagonal.

**Facade do módulo** (a parte do `-api` implementada aqui dentro):

```java
// pedidos-application/facade — implementa o contrato público, delegando a use cases
public class PedidosFacadeService implements PedidosFacade {
    private final ConsultarPedidoQuery consulta;
    public PedidosFacadeService(ConsultarPedidoQuery consulta) { this.consulta = consulta; }

    @Override
    public Optional<PedidoResumo> buscarResumo(UUID pedidoId) {
        return consulta.buscar(pedidoId).map(p -> new PedidoResumo(p.id(), p.status(), p.total()));
    }
}
```

### 6.5 `pedidos-adapter` — tecnologia real (entrada e saída)

```
pedidos-adapter/src/main/java/br/com/shop/pedidos/adapter/
│
├── in/                                         ← ADAPTERS DE ENTRADA (Driving)
│   ├── web/
│   │   ├── PedidoController.java               # @RestController, fino
│   │   ├── dto/
│   │   │   ├── CriarPedidoRequest.java         # DTO HTTP (@Valid)
│   │   │   └── PedidoResponse.java
│   │   └── PedidosExceptionHandler.java        # @RestControllerAdvice
│   └── messaging/
│       └── (listeners de eventos de OUTROS módulos, se houver)
│
├── out/                                        ← ADAPTERS DE SAÍDA (Driven)
│   ├── persistence/
│   │   ├── PedidoJpaEntity.java                # @Entity (≠ domínio!)
│   │   ├── ItemPedidoJpaEntity.java
│   │   ├── PedidoSpringDataRepository.java     # interface Spring Data
│   │   ├── PedidoPersistenceMapper.java        # domínio ↔ JPA
│   │   └── PedidoRepositoryJpa.java            # IMPLEMENTA PedidoRepository
│   ├── catalogo/
│   │   └── CatalogoFacadeAdapter.java          # IMPLEMENTA CatalogoPort (ACL)
│   └── events/
│       └── SpringEventPublisher.java           # IMPLEMENTA PublicadorDeEventos
│
└── config/
    └── PedidosModuleConfig.java                # monta os beans DO MÓDULO

pedidos-adapter/src/main/resources/db/migration/pedidos/
└── V20250101_1__criar_tabelas_pedidos.sql
```

**Adapter de entrada: o controller só traduz**

```java
@RestController
@RequestMapping("/pedidos")
class PedidoController {

    private final CriarPedidoUseCase criarPedido;        // depende da PORTA, não do service

    PedidoController(CriarPedidoUseCase criarPedido) { this.criarPedido = criarPedido; }

    @PostMapping
    ResponseEntity<PedidoResponse> criar(@Valid @RequestBody CriarPedidoRequest request) {
        var cmd = new CriarPedidoCommand(request.clienteId(),
                request.itens().stream()
                        .map(i -> new ItemCommand(i.produtoId(), i.quantidade()))
                        .toList());
        var result = criarPedido.executar(cmd);
        return ResponseEntity.status(HttpStatus.CREATED)
                .body(new PedidoResponse(result.pedidoId(), result.total()));
    }
}
```

**Adapter de saída: persistência com mapper (duas representações do Pedido)**

```java
@Repository
class PedidoRepositoryJpa implements PedidoRepository {         // ← implementa a porta

    private final PedidoSpringDataRepository jpa;
    private final PedidoPersistenceMapper mapper;

    @Override
    public void salvar(Pedido pedido) {
        jpa.save(mapper.paraJpa(pedido));                       // domínio → JPA
    }

    @Override
    public Optional<Pedido> buscarPorId(PedidoId id) {
        return jpa.findById(id.valor()).map(mapper::paraDominio); // JPA → domínio
    }
}

@Entity
@Table(name = "pedido", schema = "pedidos")                      // schema do módulo
class PedidoJpaEntity { /* campos + anotações; sem comportamento */ }
```

**Adapter de saída para outro módulo (ACL: Anti-Corruption Layer):**

```java
@Component
class CatalogoFacadeAdapter implements CatalogoPort {

    private final CatalogoFacade catalogo;                       // vem do catalogo-api

    @Override
    public Optional<ProdutoParaVenda> buscarProduto(UUID produtoId) {
        return catalogo.buscarProduto(produtoId)                 // tipo do OUTRO contexto
                .map(p -> new ProdutoParaVenda(p.id(),           // traduzido p/ o modelo de pedidos
                        new Dinheiro(p.preco(), p.moeda())));
    }

    @Override
    public boolean temEstoque(UUID produtoId, int quantidade) {
        return catalogo.estoqueDisponivel(produtoId) >= quantidade;
    }
}
```

> [!important] Por que a tradução (ACL) importa
> "Produto" no catálogo (fotos, descrição, SEO) não é o "produto" de pedidos (id e preço no momento da compra). O adapter traduz de um modelo para o outro, e é isso que impede o vazamento da linguagem de um contexto para o outro (Ubiquitous Language por contexto).

**Configuração do módulo: a "cola" fica dentro do próprio módulo**

```java
@Configuration
@EnableJpaRepositories(basePackages = "br.com.shop.pedidos.adapter.out.persistence")
@EntityScan(basePackages = "br.com.shop.pedidos.adapter.out.persistence")
@ComponentScan(basePackages = {
        "br.com.shop.pedidos.adapter.in",
        "br.com.shop.pedidos.adapter.out"})
public class PedidosModuleConfig {

    @Bean
    CriarPedidoUseCase criarPedidoUseCase(PedidoRepository pedidos, CatalogoPort catalogo,
                                          PublicadorDeEventos eventos) {
        return new CriarPedidoService(pedidos, catalogo, eventos);   // application sem @Service
    }

    @Bean
    PedidosFacade pedidosFacade(ConsultarPedidoQuery consulta) {
        return new PedidosFacadeService(consulta);                   // expõe o contrato público
    }
}
```

### 6.6 `shop-bootstrap` — só compõe, não tem regra

```
shop-bootstrap/
└── src/main/
    ├── java/br/com/shop/bootstrap/
    │   ├── ShopApplication.java          # @SpringBootApplication + main()
    │   ├── ModulesConfig.java            # @Import dos ModuleConfig de cada contexto
    │   └── GlobalWebConfig.java          # CORS, Jackson, OpenAPI (transversal)
    └── resources/
        └── application.yml
```

```java
@SpringBootApplication(scanBasePackages = "br.com.shop.bootstrap")   // NÃO varre os módulos
@Import({PedidosModuleConfig.class, CatalogoModuleConfig.class, PagamentosModuleConfig.class})
public class ShopApplication {
    public static void main(String[] args) { SpringApplication.run(ShopApplication.class, args); }
}
```

> Adicionar um módulo ao monólito = criar o `-ModuleConfig` e **uma linha** no `@Import`. Remover = apagar a linha.

---

## 7. Comunicação entre módulos

```
┌───────────────────────────────────────────────────────────────────┐
│ SÍNCRONA (precisa de resposta agora)                               │
│   pedidos.application ─► CatalogoPort (porta de saída, de pedidos) │
│        └ implementada por CatalogoFacadeAdapter (ACL)               │
│             └ chama CatalogoFacade (catalogo-api)                   │
│                  └ implementada em catalogo-application             │
├───────────────────────────────────────────────────────────────────┤
│ ASSÍNCRONA (algo aconteceu, quem quiser reage)                      │
│   pedidos publica PedidoConfirmado (pedidos-api, integration event) │
│   catalogo-adapter.in.messaging escuta e chama ReduzirEstoqueUseCase│
└───────────────────────────────────────────────────────────────────┘
```

```java
// catalogo-adapter/in/messaging — adapter de ENTRADA acionado por evento de outro módulo
@Component
class PedidoConfirmadoListener {

    private final ReduzirEstoqueUseCase reduzirEstoque;       // porta de entrada do catálogo

    @TransactionalEventListener(phase = TransactionPhase.AFTER_COMMIT)
    void aoConfirmar(PedidoConfirmado evento) {                // tipo vem de pedidos-api
        evento.itens().forEach(i ->
                reduzirEstoque.executar(new ReduzirEstoqueCommand(i.produtoId(), i.quantidade())));
    }
}
```

**Quando usar cada uma:**

| Situação | Mecanismo |
|---|---|
| Preciso do dado/resultado para continuar (preço, estoque) | Facade síncrona + ACL |
| Quero avisar que algo aconteceu, sem esperar quem reage | Integration event |
| Preciso de consistência forte entre dois contextos | Sinal de que talvez sejam **o mesmo** contexto: reavalie a fronteira |
| Efeito colateral que **não pode ser perdido** | Padrão Outbox (evento gravado na mesma transação) |

**Proibido:**

```
❌ pedidos-application importando catalogo-domain ou catalogo-application
❌ JOIN ou FK entre o schema "pedidos" e o schema "catalogo"
❌ Um módulo lendo a tabela do outro "só pra consultar"
❌ Entidade de domínio trafegando dentro de integration event ou Facade
❌ Dois módulos compartilhando a mesma entidade JPA
```

---

## 8. Banco de dados e configuração

### Um schema por módulo

```
PostgreSQL (1 instância, 1 deploy)
├── schema pedidos      ← só pedidos-adapter lê e escreve
│   ├── pedido
│   └── item_pedido
├── schema catalogo     ← só catalogo-adapter lê e escreve
│   ├── produto
│   └── estoque
└── schema pagamentos
```

**Por que isso importa:** se o módulo for extraído para microsserviço, o schema vira o banco dele e **nenhuma query cruza a fronteira**. Sem FK entre schemas, referências entre contextos são só IDs (`UUID produtoId`) e a integridade é garantida pela aplicação.

### `application.yml` (no bootstrap)

```yaml
spring:
  application:
    name: shop
  datasource:
    url: jdbc:postgresql://localhost:5432/shop
    username: ${DB_USER:shop}
    password: ${DB_PASSWORD:shop}
  jpa:
    open-in-view: false            # nunca deixar a sessão JPA vazar para a camada web
    hibernate:
      ddl-auto: validate           # o schema é dono do Flyway, não do Hibernate
  flyway:
    schemas: pedidos,catalogo,pagamentos
    locations:
      - classpath:db/migration/pedidos
      - classpath:db/migration/catalogo
      - classpath:db/migration/pagamentos
    # versões com timestamp (V20250101_1__...) evitam colisão entre módulos

shop:
  modules:
    catalogo:
      cache-ttl: 5m
    pagamentos:
      gateway: stripe
```

> [!tip] Configuração por módulo
> Propriedades específicas de um módulo ficam sob um prefixo próprio (`shop.modules.<nome>`) e são lidas por um `@ConfigurationProperties` **dentro do `adapter` desse módulo**. Assim a configuração também respeita a fronteira.

### Esquema de migrations (cada módulo é dono das suas)

```sql
-- pedidos-adapter/src/main/resources/db/migration/pedidos/V20250101_1__criar_tabelas_pedidos.sql
CREATE SCHEMA IF NOT EXISTS pedidos;

CREATE TABLE pedidos.pedido (
    id          UUID PRIMARY KEY,
    cliente_id  UUID        NOT NULL,      -- só o ID: sem FK para outro schema
    status      VARCHAR(30) NOT NULL,
    criado_em   TIMESTAMPTZ NOT NULL
);
```

---

## 9. Convenções de organização

### 9.1 Nomenclatura

| Elemento | Convenção | Exemplo |
|---|---|---|
| Módulo Maven | `<contexto>-<tipo>` | `pedidos-domain` |
| Pacote base | `br.com.shop.<contexto>.<tipo>` | `br.com.shop.pedidos.application` |
| Porta de entrada | Verbo + `UseCase` / `Query` | `CriarPedidoUseCase`, `ConsultarPedidoQuery` |
| Porta de saída | Papel que o mundo externo cumpre (sem `I`) | `PedidoRepository`, `CatalogoPort`, `PublicadorDeEventos` |
| Implementação da porta de entrada | Verbo + `Service` | `CriarPedidoService` |
| Adapter de saída | Tecnologia + papel | `PedidoRepositoryJpa`, `CatalogoFacadeAdapter` |
| Entidade de persistência | Sufixo `JpaEntity` | `PedidoJpaEntity` |
| DTO HTTP | `Request` / `Response` | `CriarPedidoRequest` |
| Command / Result | Intenção do caso de uso | `CriarPedidoCommand`, `PedidoCriadoResult` |
| Domain Event | Passado + `DomainEvent` | `PedidoConfirmadoDomainEvent` |
| Integration Event | Passado, no `-api` | `PedidoConfirmado` |
| Migration | `V<timestamp>_<n>__<descrição>.sql` | `V20250101_1__criar_tabelas_pedidos.sql` |

### 9.2 Onde colocar cada tipo de código

Versão adaptada da tabela de [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Hexagonal/3. Funcionamento e Fluxo de Requisição/3.2 Guia de Decisão - Onde Colocar Cada Código/3.2.1. Mapeamento de Responsabilidades/3.2.1.1. Onde Colocar Cada Tipo de Código|Onde Colocar Cada Tipo de Código]] para os módulos Maven:

| Tipo de código                       | Módulo / pacote                    | Exemplo                                           |
| ------------------------------------ | ---------------------------------- | ------------------------------------------------- |
| Validação de formato                 | `adapter/in/web`                   | `@Email`, `@NotBlank` no Request                  |
| Validação e cálculo de negócio       | `domain/model` ou `domain/service` | `Pedido.confirmar()`                              |
| Regra reutilizável/combinável        | `domain/specification`             | `ClienteElegivelParaDesconto`                     |
| Orquestração                         | `application/service`              | `CriarPedidoService`                              |
| Transação                            | `application/service`              | `@Transactional`                                  |
| Autorização                          | `application/service`              | "este usuário pode cancelar?"                     |
| Autenticação (JWT)                   | `adapter/in/web`                   | filtro de segurança                               |
| Conversão JSON ↔ Command             | `adapter/in/web`                   | Controller                                        |
| Acesso a banco                       | `adapter/out/persistence`          | `PedidoRepositoryJpa`                             |
| Chamada a API externa / outro módulo | `adapter/out/<destino>`            | `StripePagamentoAdapter`, `CatalogoFacadeAdapter` |
| Cache                                | `adapter/out/cache`                | decorator Redis sobre o repositório               |
| Evento de negócio (ocorrido)         | `domain/event`                     | `PedidoConfirmadoDomainEvent`                     |
| Evento que cruza módulos             | `-api/events`                      | `PedidoConfirmado`                                |
| Publicação de evento                 | `adapter/out/events`               | `SpringEventPublisher`                            |
| Beans e wiring do módulo             | `adapter/config`                   | `PedidosModuleConfig`                             |
| `main()`, CORS, Jackson, OpenAPI     | `shop-bootstrap`                   | `ShopApplication`                                 |

> [!note] Sobre `@Transactional` na application
> A única dependência de framework permitida na `application` é o `spring-tx`, só para a anotação `@Transactional`. É um compromisso pragmático: ele traz pouco acoplamento e evita criar um decorator transacional em cada caso de uso. Se o time quiser rigor total, remova o `spring-tx` e aplique a transação com um decorator no `ModuleConfig` (o Enforcer passa a banir `org.springframework*` por inteiro).

---

## 10. Testes por camada e testes de arquitetura

```
              ▲ poucos, lentos
              │   Teste de aplicação completo (@SpringBootTest, Testcontainers)
              │   Teste de adapter (controller com MockMvc; JPA com Testcontainers)
              │   Teste de caso de uso (fakes das portas de saída, sem Spring)
              ▼ muitos, rápidos
              │   Teste de domínio puro (JUnit + AssertJ)
```

| Módulo | O que testar | Como |
|---|---|---|
| `domain` | Invariantes e regras de negócio | JUnit puro, sem mock |
| `application` | Orquestração, ordem de chamadas, tratamento de erro | Fakes das portas de saída, sem Spring |
| `adapter.in` | Mapeamento HTTP, validação de formato, códigos de status | `@WebMvcTest` com a porta de entrada mockada |
| `adapter.out` | Mapper, queries, contrato da porta | Testcontainers (PostgreSQL real) |
| `architecture-tests` | A arquitetura em si | ArchUnit |

### Testes de arquitetura (camada 3 de defesa)

```java
// architecture-tests/src/test/java/br/com/shop/architecture/HexagonalArchitectureTest.java
@AnalyzeClasses(packages = "br.com.shop", importOptions = ImportOption.DoNotIncludeTests.class)
class HexagonalArchitectureTest {

    @ArchTest
    static final ArchRule dominio_nao_depende_de_ninguem =
        noClasses().that().resideInAPackage("..domain..")
            .should().dependOnClassesThat().resideInAnyPackage(
                "..application..", "..adapter..", "org.springframework..", "jakarta..");

    @ArchTest
    static final ArchRule application_nao_conhece_adapters =
        noClasses().that().resideInAPackage("..application..")
            .should().dependOnClassesThat().resideInAPackage("..adapter..");

    @ArchTest
    static final ArchRule adapters_de_entrada_nao_chamam_adapters_de_saida =
        noClasses().that().resideInAPackage("..adapter.in..")
            .should().dependOnClassesThat().resideInAPackage("..adapter.out..");

    @ArchTest
    static final ArchRule pedidos_so_usa_a_api_do_catalogo =
        noClasses().that().resideInAPackage("br.com.shop.pedidos..")
            .should().dependOnClassesThat(
                resideInAPackage("br.com.shop.catalogo..")
                    .and(not(resideInAPackage("br.com.shop.catalogo.api.."))));

    @ArchTest
    static final ArchRule controller_so_chama_portas_de_entrada =
        noClasses().that().resideInAPackage("..adapter.in.web..")
            .should().dependOnClassesThat().resideInAPackage("..application.service..");
}
```

> Esta regra de módulo (`pedidos_so_usa_a_api_do_catalogo`) deve ser **repetida para cada par de contextos** ou gerada por um laço sobre a lista de módulos.

---

## 11. Checklist de conformidade arquitetural

```
✓ domain não importa nada de org.springframework.*, jakarta.* nem Jackson
✓ domain não tem interface técnica (as portas de saída ficam na application)
✓ Objetos de domínio ≠ entidades JPA (existe mapper em adapter/out/persistence)
✓ Aggregates não têm setters públicos; mudam estado por métodos de negócio
✓ Toda saída (banco, HTTP, fila, outro módulo) passa por uma porta de saída
✓ Toda entrada (REST, listener) chama uma porta de entrada, nunca o Service direto
✓ Controllers só traduzem: nenhum "if" de regra de negócio
✓ Application Service sem cálculo de negócio (sem percentuais, faixas, fórmulas)
✓ Adapters só traduzem/persistem: nunca decidem fluxo
✓ Outro módulo só é acessado via <ctx>-api (Facade ou integration event)
✓ Chamada a outro módulo passa por adapter de saída com ACL
✓ Cada módulo tem seu schema; nenhum JOIN/FK entre schemas
✓ ModuleConfig do módulo + uma linha no @Import do bootstrap
✓ Dinheiro usa BigDecimal, nunca double/float
✓ O build (Maven + Enforcer + ArchUnit) QUEBRA se alguém violar qualquer regra acima
```

---

## 12. Trade-offs honestos

```
✅ Vantagens:
  - Arquitetura garantida pelo build em 3 camadas, não pela disciplina
  - Domínio e casos de uso testáveis em milissegundos, sem banco nem Spring
  - Troca de tecnologia isolada em adapters (JPA → Mongo, Stripe → Pagar.me)
  - Múltiplas entradas para o mesmo caso de uso (REST, fila, CLI) sem duplicar regra
  - Fronteiras de módulo prontas para extração em microsserviços
  - Cada módulo é dono dos seus dados (schema próprio)

⚠️ Custos:
  - Muitos artefatos: 4 módulos Maven por contexto (3 contextos = 12 módulos + 3)
  - Boilerplate: mapper domínio↔JPA, Command/Result, DTO por camada, ACL por integração
  - Build multi-módulo é mais lento e mais complexo de configurar
  - Curva de aprendizado alta para quem vem de "controller → service → repository"
  - Risco de over-engineering em contextos que são CRUD puro

Quando NÃO usar:
  - CRUD sem regra de negócio relevante → monólito em camadas por pacote
  - MVP descartável → a velocidade importa mais que a estrutura
  - Time pequeno sem experiência com Ports & Adapters → comece pelo contexto mais rico
    do domínio e use o template só nele; os outros podem ser mais simples

Quando VALE muito a pena:
  - Domínio rico, com regras que mudam com frequência
  - Várias integrações externas voláteis (pagamento, ERP, e-mail, fila)
  - Várias equipes no mesmo código, precisando de fronteiras claras
  - Possível extração futura de módulos para microsserviços
```

### Evolução para microsserviços (extraindo o módulo `catalogo`)

```
Hoje (monólito modular)                    Depois (catalogo extraído)
───────────────────────                    ──────────────────────────
CatalogoFacadeAdapter                      CatalogoHttpAdapter            ← novo adapter
  └ chama CatalogoFacade (in-process)        └ chama a API REST do serviço
PedidoConfirmadoListener                   PedidoConfirmadoKafkaListener  ← novo adapter
  └ evento Spring in-process                 └ evento no Kafka
schema "catalogo" no mesmo banco           schema "catalogo" vira banco próprio

NÃO muda: pedidos-domain, pedidos-application, catalogo-domain, catalogo-application
```

Como a `application` de `pedidos` só conhece a porta `CatalogoPort`, a migração troca **um adapter de saída**. É a vantagem concreta de tratar outro módulo como "mais um serviço externo".

---

## 13. Comparativo com o template de Clean Architecture

| Aspecto | Template Clean | Template Hexagonal (este) |
|---|---|---|
| Módulos por contexto | `core`, `application`, `infrastructure`, `webapi` | `api`, `domain`, `application`, `adapter` |
| Onde ficam as interfaces de saída | `domain/gateways` (no core) | `application/port/out` |
| Entrada | Interactor chamado pelo controller | Porta de entrada explícita (`UseCase`) + Service |
| Vocabulário | Entities, Use Cases, Gateways, Frameworks & Drivers | Domain, Application, Ports, Adapters |
| Prefixo de interfaces | `IPedidoRepository` | `PedidoRepository` (papel, sem prefixo) |
| Fronteira entre contextos | Regra textual + eventos | Módulo `-api` + Maven impede o acesso a qualquer outra coisa |
| Integração entre contextos | Evento ou interface pública | Facade + ACL, ou integration event |
| Banco de dados | Não detalhado | Schema por módulo + Flyway por módulo |
| Enforcement | Maven | Maven + Enforcer + ArchUnit |
| Wiring | `BeanConfig` no webapi | `ModuleConfig` por módulo + `@Import` no bootstrap |

> **Resumo:** as duas arquiteturas protegem o domínio da mesma forma. A diferença prática deste template é o foco: **a Hexagonal enfatiza a simetria "entra por uma porta, sai por outra"**, o que combina bem com módulos que tratam uns aos outros como serviços externos.
>
> Para a comparação conceitual completa, ver [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Hexagonal/5. Relação com Outras Arquiteturas/5.1 Linha do Tempo e Evolução/5.1.2. Hexagonal vs Clean Architecture/5.1.2.1. Diferenças de Rigidez entre as Duas|Diferenças de Rigidez entre as Duas]].

---

## 14. Relação com outros conceitos

- **[[10. Arquitetura de Software e Design de Software/Padrões e Princípios/SOLID|SOLID]]:** o **D** (Inversão de Dependência) é a base das portas; o **I** (Segregação de Interfaces) pede portas de entrada pequenas e coesas (um `UseCase` por intenção, em vez de um `SistemaService` gigante).
- **Ports & Adapters (Cockburn):** é a base do template: portas de entrada e saída, adapters nas bordas.
- **Domain-Driven Design:** aggregates, value objects, domain events, specifications, **bounded contexts** (cada módulo) e **Anti-Corruption Layer** (o adapter que traduz outro contexto).
- **Clean Architecture:** mesma regra de dependência; ver a seção 13.
- **Monolito Modular vs Microsserviços:** este template é o ponto intermediário, com fronteiras de microsserviço sem o custo de rede.

---

## 🧩 Quiz de Fixação

1. Um desenvolvedor adiciona `spring-boot-starter-data-jpa` ao `pom.xml` do `pedidos-domain` "só para usar `@Entity` direto no `Pedido`". O que acontece no `mvn verify`, e quais das três camadas de defesa o impedem?

2. Por que a interface `PedidoRepository` fica em `pedidos-application/port/out` e não em `pedidos-domain`? E por que o `CriarPedidoController` depende de `CriarPedidoUseCase` e não de `CriarPedidoService`?

3. O contexto `pedidos` precisa saber o preço atual de um produto do `catalogo`. Descreva o caminho correto (módulos, interfaces e adapter) e explique o papel do ACL. Por que importar `catalogo-domain` direto em `pedidos-application` seria um erro?

4. A equipe decide extrair `catalogo` para um microsserviço. Liste o que **muda** e o que **não muda**, e explique por que a troca é pequena.

**Respostas:**

1) **O build falha.** A camada 2 (Maven Enforcer) tem a regra `bannedDependencies` no `pedidos-domain`, que proíbe `org.springframework*`, `jakarta.*` e `org.hibernate*`, inclusive transitivamente. Se alguém tentasse burlar removendo o Enforcer, a camada 3 (ArchUnit) reprovaria qualquer classe em `..domain..` que dependa de `jakarta..` ou `org.springframework..`. A camada 1 (classpath) funciona em sentido contrário: sem a dependência declarada, o `@Entity` nem compila. As três juntas fazem a arquitetura deixar de depender da boa vontade do dev. O caminho certo é uma `PedidoJpaEntity` no `pedidos-adapter` com um mapper.

2) **A porta de saída é uma necessidade da aplicação:** "preciso salvar e buscar pedidos". Quem decide *como* persistir é o adapter. Colocá-la na `application` mantém o domínio sem nenhuma interface técnica, só regra de negócio. **O controller depende da porta de entrada** porque é o contrato oferecido pela aplicação (inversão de dependência): dá para trocar a implementação, mockar a porta em `@WebMvcTest` e chamar o mesmo caso de uso a partir de um listener de fila ou de um CLI, sem duplicar nada. Depender do `Service` concreto acoplaria o adapter à implementação.

3) **Caminho correto:** `pedidos-application` define a porta de saída `CatalogoPort` (com o tipo `ProdutoParaVenda`, do modelo de pedidos). O `pedidos-adapter` (`out/catalogo`) tem o `CatalogoFacadeAdapter`, que implementa a porta chamando o `CatalogoFacade` do **`catalogo-api`**. A implementação do Facade mora em `catalogo-application`, e o `bootstrap` junta as duas pontas. **O ACL** traduz o modelo do catálogo para o de pedidos, evitando que a linguagem de um contexto vaze para o outro. **Importar `catalogo-domain`** seria um erro porque: (a) o `pom.xml` de `pedidos-application` não declara essa dependência, então não compila (camada 1); (b) acopla os dois contextos, de modo que qualquer mudança interna no catálogo quebra pedidos; (c) impede a extração futura do catálogo.

4) **Muda:** só os adapters de borda: o `CatalogoFacadeAdapter` vira um cliente HTTP/gRPC (`CatalogoHttpAdapter`), o listener de evento in-process vira um listener Kafka/RabbitMQ, o schema `catalogo` vira um banco próprio e o deploy do catálogo passa a ser separado. **Não muda:** `pedidos-domain`, `pedidos-application`, `catalogo-domain` e `catalogo-application`. A troca é pequena porque `pedidos` sempre tratou o catálogo como um serviço externo atrás de uma porta, e o catálogo sempre falou com o mundo por `-api` + eventos, sem FK nem JOIN entre schemas.

---
> **Glossário Pai:** [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Hexagonal/0 Hexagonal (Glossário )|Arquitetura Hexagonal (Glossário)]]
>
> **Links Relacionados:**
> [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Hexagonal/Plano - Template Monolítico Modular Hexagonal|Plano deste template]]
> [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Clean architecture/Template Monolítico Modular (Multi-Module Clean Architecture)|Template Monolítico Modular (Clean Architecture)]]
> [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Monolítico Modular vs Microsserviços|Monolítico Modular vs Microsserviços]]
> [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Domain Diven Design DDD/0 Domain Diven Design DDD (Glossário )|Domain-Driven Design (DDD)]]
