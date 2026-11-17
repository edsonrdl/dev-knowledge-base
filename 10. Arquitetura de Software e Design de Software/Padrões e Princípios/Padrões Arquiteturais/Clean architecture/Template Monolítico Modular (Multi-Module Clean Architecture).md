# 🏛 Template Monolítico Modular (Multi-Module Clean Architecture)
#arquitetura #clean-architecture #ddd #monolito-modular #template

> [!info] Visão Geral
> Este é o **template** da Clean Architecture para **monólito modular** ou **serviço único**. Ele descreve **a estrutura, a responsabilidade de cada anel e onde fica cada tipo de código**, sem depender de linguagem, framework ou ferramenta de build. Use-o como ponto de partida para montar um projeto novo, estender um existente ou revisar a aderência de um repositório.
>
> Para ver a estrutura **aplicada em uma tecnologia concreta** (Java, Spring e Maven, com código), veja o [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Clean architecture/Exemplo de Implementação - Monólito Modular Clean Architecture (Java, Spring e Maven)|Exemplo de Implementação (Java, Spring e Maven)]].

---

## 1. A ideia central: anéis concêntricos

A arquitetura é uma **cadeia de anéis**. Cada anel só conhece o anel de dentro dele. O anel mais interno não conhece ninguém.

```
   webapi  ──►  infrastructure  ──►  application  ──►  domain
 (anel 4)         (anel 3)           (anel 2)          (anel 1)
 entrada e        tecnologia         casos de uso      regras de negócio
 montagem         e adapters                           e contratos (gateways)
```

A seta significa "conhece". **A dependência de código sempre aponta para dentro.** O fluxo de execução faz o caminho contrário: a requisição entra pelo `webapi`, chega ao caso de uso, o caso de uso pede dados por um contrato do `domain`, e a `infrastructure` o atende. A **inversão de dependência** reconcilia os dois sentidos.

| Anel | Pasta | Papel | Conhece |
|---|---|---|---|
| 1 | `domain` | regras de negócio da empresa e os **gateways** (contratos) que o negócio exige do mundo | ninguém |
| 2 | `application` | casos de uso: orquestram o domínio por meio dos gateways | só o `domain` |
| 3 | `infrastructure` | implementa os gateways com tecnologia real (banco, fila, APIs, outros módulos) e reage a eventos chamando casos de uso | `application` e `domain` |
| 4 | `webapi` | ponto de entrada: controllers, DTOs de request e response, tratamento de erros, inicialização e montagem | `infrastructure`, `application` e `domain` |

**Relação com os círculos de Robert C. Martin:** Entities = `domain`; Use Cases = `application`; Interface Adapters e Frameworks & Drivers = `infrastructure` e `webapi`. Na prática de mercado (soluções .NET como Core, Infrastructure e Presentation; projetos Java multi-módulo com um módulo `webapi`), o círculo externo é separado em dois anéis como este, e o `webapi` é a camada de apresentação.

**Regra de ouro de cada anel:**
- `webapi` **só traduz**: converte HTTP em chamada de caso de uso, e a resposta de volta em HTTP. Não contém regra de negócio.
- `infrastructure` **só implementa**: executa o que o contrato pede, com a tecnologia escolhida. Não decide fluxo de negócio.
- `application` **só orquestra**: chama o domínio na ordem certa. Não calcula regra de negócio.
- `domain` **decide**: toda regra de negócio mora aqui.

---

## 2. As regras inegociáveis

1. **Regra da dependência:** nenhum anel interno importa um anel externo. `domain` e `application` nunca importam `infrastructure` nem `webapi`.
2. **Dentro do `webapi`:** controllers, DTOs e handlers dependem só da `application`. Só o `webapi/entrypoint` conhece todos os anéis, porque é ele que liga as peças.
3. **Entre módulos:** um módulo só usa a pasta `api/` do outro. Nunca as camadas internas do vizinho.
4. **Dados que cruzam fronteiras** são sempre dados simples e isolados (input, output, request, response). Nunca uma entity nem uma linha de banco.

### Como garantir

Uma regra que depende da boa vontade do time acaba violada. O template exige **três camadas de defesa**, adaptadas à ferramenta da stack:

1. **Isolamento de build:** cada módulo declara do que depende, e uma dependência não declarada falha na compilação (quando a stack permite).
2. **Dependências banidas:** `domain` e `application` não aceitam, nem indiretamente, bibliotecas de tecnologia.
3. **Teste de arquitetura:** verificação automática de dependências entre pastas ou pacotes, no pipeline. **Sem ela verde, não há merge.**

> [!tip] Prova de proteção
> Uma regra só vale se a violação realmente falha. Ao criar o projeto, introduza temporariamente uma violação (biblioteca no domínio; `infrastructure` dentro de `application`; controller importando a `infrastructure`; import entre módulos fora do `api/`), confirme que a verificação falha e remova.

---

## 3. Quando usar e quando não usar

**Use** quando há: domínio rico, regras que mudam, vários times, crescimento previsto, possível extração futura de módulos.

**Não use** para: CRUD sem regra, MVP descartável. Uma API simples em camadas basta.

Prefira esta arquitetura quando o time já pensa em anéis, Use Cases e Entities, e quer o domínio com seus gateways juntos.

---

## 4. O que definir antes de montar

| Item | O que é | Exemplo |
|---|---|---|
| Nome do serviço | identifica o repo e os logs | `shop` |
| Módulos | um por contexto de negócio (bounded context) | `catalog`, `orders` |
| Topologia | monólito modular (vários módulos) ou serviço único (um módulo) | monólito modular |
| Framework HTTP, acesso a dados, logger, testes | ferramentas padrão do projeto | definidas no plano do projeto |

Nomes de módulo: minúsculas, em inglês, substantivo do negócio. Em serviço único, existe **um** módulo.

---

## 5. Estrutura de pastas

```
<nome-do-servico>/
├── src/
│   ├── shared-kernel/                  ← mínimo e estável; sem framework
│   │   ├── domain/                     ← tipos base: raiz de agregado, evento de domínio,
│   │   │                                 erro de domínio, dinheiro
│   │   ├── application/                ← contrato de transação (unit of work)
│   │   ├── events/                     ← contrato do barramento de eventos
│   │   ├── observability/              ← contrato do logger
│   │   └── persistence/                ← contrato mínimo de acesso ao banco
│   │
│   ├── modules/
│   │   └── <modulo>/                   ← UM contexto de negócio
│   │       ├── api/                    ← CONTRATO PÚBLICO: única porta de saída do módulo
│   │       │   ├── interface pública   ← o que outros módulos podem chamar
│   │       │   └── eventos             ← eventos de integração publicados
│   │       │
│   │       ├── domain/                 ← ANEL 1: regras de negócio
│   │       │   ├── entities/           ← agregados e entidades
│   │       │   ├── value-objects/      ← objetos de valor
│   │       │   ├── services/           ← regras que envolvem mais de um agregado
│   │       │   ├── events/             ← eventos de domínio
│   │       │   ├── gateways/           ← CONTRATOS que o domínio exige do mundo
│   │       │   └── errors/             ← erros de regra de negócio
│   │       │
│   │       ├── application/            ← ANEL 2: casos de uso
│   │       │   ├── use-cases/<caso>/   ← por caso de uso: interactor + input + output
│   │       │   └── facade/             ← implementa a interface pública de api/
│   │       │
│   │       ├── infrastructure/         ← ANEL 3: tecnologia e adapters
│   │       │   ├── persistence/        ← repositórios (implementam gateways), mapeadores, migrations
│   │       │   ├── messaging/          ← publicação de eventos e listeners
│   │       │   │                         (listeners recebem evento e chamam um caso de uso)
│   │       │   ├── <outro-modulo>/     ← anticorruption layer (usa só o api/ do outro)
│   │       │   └── <integração>/       ← pagamento, e-mail, cache, estoque… um adapter por serviço
│   │       │
│   │       └── webapi/                 ← ANEL 4: ponto de entrada
│   │           ├── controllers/        ← traduzem HTTP em chamada de caso de uso
│   │           ├── dtos/               ← request e response HTTP (com validação de formato)
│   │           ├── handlers/           ← tradução de erros de domínio em resposta HTTP
│   │           └── entrypoint/         ← ponto de partida do módulo: inicialização e
│   │                                     composição (liga casos de uso e adapters)
│   │
│   └── bootstrap/                      ← só compõe os módulos: nenhuma regra de negócio
│       ├── ponto de entrada            ← inicia a aplicação
│       ├── configuração                ← único lugar que lê variáveis de ambiente
│       ├── health check · barramento de eventos
│       └── montagem da aplicação       ← instancia os módulos na ordem das dependências
│
├── tests/
│   ├── integration/                    ← infraestrutura com banco/serviço real ou container
│   └── e2e/                            ← fluxos completos pela borda HTTP
├── sdd/                                ← quando existir
├── configuração da ferramenta de arquitetura (regras de dependência)
└── README, .env.example, .gitignore
```

> [!note] Em build multi-módulo
> Quando a stack permite, cada anel vira um **módulo de build** próprio (`<ctx>-domain`, `<ctx>-application`, `<ctx>-infrastructure`, `<ctx>-webapi`), e a regra da dependência passa a ser imposta pelo compilador. Veja o exemplo com Maven no documento de implementação.

---

## 6. Responsabilidade de cada pasta

| Pasta | Responsabilidade | Pode depender de | Não pode depender de |
|---|---|---|---|
| `shared-kernel` | tipos base e contratos técnicos mínimos | nada | módulos, bootstrap, bibliotecas externas |
| `<m>/api` | contrato público do módulo | `shared-kernel` | domain, application, infrastructure, webapi, bibliotecas externas |
| `<m>/domain` | entities, objetos de valor, gateways e regra de negócio | `shared-kernel` e o próprio domain | application, infrastructure, webapi, outros módulos, bibliotecas externas |
| `<m>/application` | use cases (interactors), input e output | o próprio domain, `api` de outros módulos, `shared-kernel` | infrastructure, webapi, bibliotecas externas |
| `<m>/infrastructure` | implementa gateways; listeners de evento; integrações | `application`, `domain`, `api` de outros módulos, bibliotecas de tecnologia | webapi |
| `<m>/webapi/controllers`, `dtos`, `handlers` | entrada HTTP: traduz request em input e output em response | `application` (use cases, input, output), bibliotecas de HTTP | infrastructure, domain direto |
| `<m>/webapi/entrypoint` | inicialização e composição do módulo | todas as camadas do próprio módulo, `api` de outros | — |
| `bootstrap` | liga módulos, configuração e inicialização | `webapi/entrypoint` dos módulos, `shared-kernel` | camadas internas dos módulos |

---

## 7. Onde colocar cada tipo de código

| O que é | Onde fica |
|---|---|
| Validação de **formato** (obrigatório, tamanho, e-mail) | `webapi/dtos` |
| Validação e cálculo de **negócio** | `domain` (entity ou domain service) |
| Orquestração, transação, autorização | interactor em `application/use-cases` |
| JSON ↔ input/output | `webapi/controllers` e `webapi/dtos` |
| Erro de domínio → resposta HTTP | `webapi/handlers` |
| Autenticação (token, sessão) | `webapi` (middleware) |
| Banco, cache, API externa | `infrastructure` |
| Chamada a outro módulo | `infrastructure/<modulo>` com anticorruption layer |
| Receber evento de outro módulo | listener em `infrastructure/messaging`, que chama um caso de uso |
| Evento de negócio (algo ocorreu) | `domain/events` |
| Evento que cruza módulos | eventos em `api/` |
| Montagem de dependências do módulo | `webapi/entrypoint` |
| Variáveis de ambiente | **somente** a configuração do `bootstrap` |

**Regra de triagem:** a decisão depende de conhecimento de negócio ou é só execução técnica? Negócio vai para o `domain`; técnica vai para `infrastructure` (saída) ou `webapi` (entrada). O use case apenas **chama** a decisão que a entity tomou.

---

## 8. Papel de cada peça

### 8.1 shared-kernel
Só o que todos os módulos realmente compartilham e quase nunca muda: raiz de agregado, evento de domínio, erro de domínio (com código e tipo), dinheiro (valor inteiro da menor unidade, nunca decimal flutuante) e os contratos técnicos mínimos (transação, barramento de eventos, logger, acesso ao banco). Se um item é usado por um módulo só, ele não é do kernel.

### 8.2 domain (anel 1)
- A **entity** (agregado) é a raiz de consistência: guarda as invariantes e muda de estado **só por métodos de negócio**. Entity rica tem comportamento; entity que só tem getters e setters é **anêmica** e é um defeito.
- **Objetos de valor** são imutáveis e comparados pelo valor.
- **Domain services** ficam com regras que envolvem mais de um agregado.
- **Eventos de domínio** registram o que aconteceu; a entity os acumula e quem persiste decide quando publicá-los.
- **Gateways:** contratos que o domínio exige do mundo (repositório, consulta a outro módulo, publicação de evento). Ficam **no domínio**, em tipos próprios do módulo; a implementação mora na `infrastructure`.
- **Sem I/O, sem biblioteca externa e sem relógio solto.**

### 8.3 application (anel 2)
- **Interactor:** uma pasta por caso de uso, com o interactor, o **input** e o **output**. Carrega o necessário pelos gateways, chama a entity, abre a transação, persiste e publica eventos. **Não decide regra de negócio e não conhece tecnologia.**
- **Input e output:** dados simples; nunca a entity.
- **Facade:** implementa a interface pública de `api/` para os outros módulos, devolvendo dados simples.

### 8.4 api (contrato público)
Só contratos, dados simples e constantes de eventos. **Nunca** expõe entity. Mudar algo aqui é mudar contrato: afeta todos os consumidores, então muda com cuidado e com versão de evento.

### 8.5 infrastructure (anel 3)
Tudo que o sistema **usa** do mundo: o use case pede por um gateway, e a infraestrutura o implementa com a tecnologia real. Todo o SQL e o código do driver ficam confinados aqui.
- **Repositório:** implementa o gateway de persistência e converte entre entity e modelo do banco por um **mapeador**. A entity **nunca é** o modelo de persistência: são duas representações.
- **Anticorruption layer:** implementa o gateway que fala com outro módulo, usando só o `api/` dele, e traduz o modelo alheio para o modelo próprio.
- **Integrações externas:** um adapter por serviço (pagamento, e-mail, cache, estoque), cada um implementando um gateway.
- **Publicador de eventos** e **listeners:** o listener recebe o evento de outro módulo (usando só o `api/` dele) e chama um caso de uso. É o único caso em que a infraestrutura chama a `application`.
- A infraestrutura **não decide fluxo de negócio**.

### 8.6 webapi (anel 4)
O ponto de entrada. Recebe o mundo e o entrega ao caso de uso.
- **Controller:** fino. Converte o request em input, chama o caso de uso e converte o output em response. Depende só da `application`.
- **DTOs:** o formato HTTP de entrada e de saída, com a validação de **formato** (não de negócio).
- **Handlers de erro:** convertem erro de domínio em resposta HTTP; erro inesperado vira 500 genérico, sem vazar detalhe interno.
- **Entrypoint:** o ponto de partida do módulo, com a inicialização e a composição. É o **único lugar do módulo que conhece todos os anéis**: instancia as implementações da infraestrutura e as entrega aos casos de uso (injeção de dependência).

### 8.7 bootstrap
Liga os módulos entre si. Lê a configuração de ambiente (único leitor), cria o barramento de eventos e o health check, e instancia os módulos **na ordem das dependências**. Adicionar um módulo é registrar uma linha aqui; remover é apagá-la.

---

## 9. Comunicação entre módulos

| Situação | Mecanismo |
|---|---|
| Preciso do dado agora (preço, estoque) | `api/` do outro módulo, consumido por gateway com anticorruption layer |
| Aviso de que algo aconteceu | evento de integração no barramento (contrato em `api/`) |
| Efeito que **não pode ser perdido** | outbox: grava o evento na mesma transação e publica depois |
| Preciso de consistência forte entre dois contextos | reavalie: provavelmente são o mesmo contexto |

**Proibido:** importar camadas internas de outro módulo; JOIN ou chave estrangeira entre dados de módulos; ler a tabela do vizinho; entity dentro de evento ou `api`; dois módulos compartilhando o mesmo modelo de persistência.

---

## 10. Banco de dados

- Cada módulo só toca nos **seus** dados.
- Com banco que suporta schema: **um schema por módulo**. Sem suporte: prefixo no nome da tabela.
- Referência a outro módulo é só o **identificador**, sem chave estrangeira.
- Migrations versionadas, automatizadas no pipeline e **nunca editadas** depois de aplicadas em produção. Ficam dentro do módulo, na persistência, com nome que inclui data e hora.
- Em serviço único, o serviço é dono do seu banco.

---

## 11. Tratamento de erros

- Regra de negócio violada → erro de domínio (com código e tipo) → handler do `webapi` → envelope de erro padrão.
- Erro de formato → 400 com detalhe por campo, no `webapi`.
- Erro inesperado → 500 genérico; log com a causa técnica e **sem dados do payload**.
- Nível de erro no log apenas para falha que exige atenção humana.

---

## 12. Testes por anel

| Anel | O que testar | Como |
|---|---|---|
| `domain` | invariantes e regras | puro, sem mock |
| `application` | orquestração, ordem, erros | gateways falsos, sem framework |
| `infrastructure` | mapeador, consultas, contrato do gateway, listeners | integração com banco real ou container |
| `webapi` | formato, status HTTP, tradução de erros | controller com o use case simulado |
| arquitetura | regra da dependência | verificação automática + prova de proteção |

---

## 13. Checklist de conformidade

```
✓ domain sem biblioteca externa ou framework
✓ domain não importa application, infrastructure, webapi nem outro módulo
✓ application só conhece o domain
✓ nenhum anel interno importa um anel externo
✓ controllers, DTOs e handlers só dependem da application; só webapi/entrypoint conhece todos os anéis
✓ módulo só importa o api/ de outro
✓ sem ciclos de dependência
✓ gateways vivem em domain/gateways; a implementação só em infrastructure
✓ entity é diferente do modelo de persistência (existe mapeador)
✓ controller sem regra de negócio nem mutação direta de entity
✓ interactor sem cálculo de negócio
✓ infraestrutura não decide fluxo de negócio
✓ entities ricas, não anêmicas
✓ dinheiro não é decimal flutuante
✓ schema ou prefixo por módulo; sem chave estrangeira entre módulos
✓ variáveis de ambiente só na configuração do bootstrap
✓ a verificação de arquitetura roda no pipeline e a prova de proteção foi feita
```

---

## 14. Anti-padrões e como corrigir

| Anti-padrão | Correção |
|---|---|
| Over-engineering em CRUD | usar camadas simples |
| Entity anêmica | mover a regra do service para a entity |
| Framework vazando para o domain | classe de domínio pura + mapeador na infraestrutura |
| Controller com regra de negócio | mover para a entity; o controller só traduz e chama o use case |
| Interactor "faz-tudo" | dividir em use cases coesos, um por intenção |
| Módulo usando internals do vizinho | `api/` + anticorruption layer |
| Infraestrutura decidindo fluxo | a decisão sobe para o use case; a infraestrutura só executa |
| Controller instanciando adapter da infraestrutura | a montagem fica só em `webapi/entrypoint` |

---

## 15. Trade-offs

```
✅ Vantagens
  - Domínio testável em milissegundos, sem banco nem framework
  - Troca de tecnologia isolada na infraestrutura
  - Fronteiras prontas para extração futura em microsserviços
  - Cada anel com responsabilidade óbvia

⚠️ Custos
  - Mais código de tradução: mapeadores e dados simples em cada fronteira
  - Curva de aprendizado para quem está acostumado a "tudo num projeto"
  - Excesso de cerimônia em CRUD simples
```

---

## 16. Evolução para microsserviço

Para extrair um módulo (por exemplo `catalog`): o gateway do consumidor passa a chamar HTTP em vez do `api/` em memória; o listener troca o barramento em memória pela fila; o schema vira banco próprio. **Não mudam** `domain` nem `application`.

---

## 17. Relação com outros conceitos

- **Clean Architecture (Robert C. Martin):** é a base do template: anéis concêntricos com a regra da dependência apontando para dentro.
- **Arquitetura Hexagonal:** protege o domínio do mesmo jeito, com portas e adapters lado a lado em vez de anéis. Veja o [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Hexagonal/Template Monolítico Modular (Multi-Module Hexagonal Architecture)|Template Hexagonal]].
- **Domain-Driven Design:** agregados, objetos de valor, eventos de domínio e bounded contexts.
- **SOLID:** especialmente a inversão de dependência: o núcleo define o contrato e a borda o obedece.
- **Exemplo de implementação:** [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Clean architecture/Exemplo de Implementação - Monólito Modular Clean Architecture (Java, Spring e Maven)|Java, Spring e Maven]].
