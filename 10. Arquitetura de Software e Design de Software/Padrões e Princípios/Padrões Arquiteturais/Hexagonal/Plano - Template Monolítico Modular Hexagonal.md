# 🗺️ Plano: Template Monolítico Modular (Multi-Module Hexagonal Architecture)
#arquitetura #hexagonal #ports-and-adapters #monolito-modular #plano

> [!info] Objetivo
> Criar, dentro da pasta **Hexagonal**, um template de implementação e organização equivalente ao que já existe em Clean Architecture ([[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Clean architecture/Template Monolítico Modular (Multi-Module Clean Architecture)|Template Monolítico Modular (Multi-Module Clean Architecture)]]), mas usando o vocabulário de **Ports & Adapters** e uma versão de monólito modular **mais limpa**: fronteiras entre módulos garantidas pelo build, e não só entre camadas.

---

## 1. Diagnóstico do material existente

### O que já temos (Glossário Hexagonal)
- Os 5 domínios (Fundamentos, Anatomia, Fluxo, Trade-offs, Relação com outras arquiteturas) estão **todos concluídos** (`[x]`).
- Vocabulário já fixado: **Primary/Driving Ports** (casos de uso oferecidos), **Secondary/Driven Ports** (o que a aplicação exige), **Adapters de entrada e de saída**, Application Service, Commands/Queries/DTOs.
- Já existe um guia de decisão (3.2.1.1 "Onde Colocar Cada Tipo de Código") e cinco anti-padrões com correção (3.2.2.1). O template deve **reaproveitar** esses dois, não repetir.

### O que o template de Clean faz e vale manter
- Exemplo único de e-commerce (`shop`) atravessando todas as camadas.
- Argumento central: **o compilador como guardião** (multi-módulo Maven).
- Estrutura: visão macro → POMs → fluxo → pastas por módulo → bounded contexts → checklist → trade-offs → relação com outros conceitos → quiz com respostas.

### Lacunas a corrigir na versão Hexagonal
| Ponto | Template Clean | Decisão no template Hexagonal |
|---|---|---|
| Onde ficam as portas de saída | `domain/gateways` (dentro do core) | **`application`** (portas de entrada e de saída lado a lado). O domínio fica sem nenhuma interface técnica |
| Portas de entrada | Interactors chamados direto | **Interfaces explícitas** (`CriarPedidoUseCase`), que o adapter de entrada chama |
| Prefixo de interface | `IPedidoRepository` (estilo C#) | Sem prefixo: `PedidoRepository`, `CatalogoPort` (nome pelo papel) |
| Fronteira entre bounded contexts | Regra textual ("não importar o core do outro") | Módulo **`-api`** público por contexto: o único artefato que outro módulo pode declarar como dependência |
| Adapters | Pacote `infrastructure` único | Pacotes `adapter.in` e `adapter.out`, proibidos de se enxergarem (ArchUnit) |
| Banco de dados | Não tratado | **Um schema por módulo**, migrations por módulo, sem FK entre schemas |
| Enforcement | Só Maven | **3 camadas**: Maven (classpath) → Enforcer (dependências banidas) → ArchUnit (pacotes) |
| Configuração/DI | `BeanConfig` central no webapi | Cada módulo expõe seu `ModuleConfig`; o `bootstrap` só lista os módulos |

---

## 2. Decisões de arquitetura do template

1. **Stack:** Java 21 + Spring Boot 3 + Maven multi-módulo (mesma do template Clean, para comparação direta).
2. **Cinco tipos de artefato** por bounded context: `-api`, `-domain`, `-application`, `-adapter` + o `bootstrap` global.
3. **Duas regras de dependência**, ambas verificadas no build:
   - *Intra-módulo:* `adapter → application → domain` (domínio não conhece ninguém).
   - *Inter-módulo:* um contexto só pode depender do **`-api`** de outro.
4. **Comunicação entre módulos:** síncrona via Facade (do `-api`) consumida por um **adapter de saída com ACL**; assíncrona via **integration events** in-process.
5. **Exemplo:** e-commerce com dois contextos completos (`pedidos`, `catalogo`) e um terceiro só mencionado (`pagamentos`).
6. **Variante de rigor:** `adapter` único com pacotes `in/out` (padrão) ou dividido em `adapter-in` e `adapter-out` (rigor máximo).

---

## 3. Estrutura do documento a produzir

- [x] 1. O que é Monólito Modular Hexagonal (e por que um hexágono por módulo)
- [x] 2. As duas regras inegociáveis e as 3 camadas de defesa
- [x] 3. Os 5 tipos de artefato e suas responsabilidades
- [x] 4. Estrutura Maven macro + POMs (parent, domain, application, adapter, bootstrap)
- [x] 5. Diagrama de fluxo de uma requisição atravessando dois módulos
- [x] 6. Estrutura de pastas e código por módulo (api, domain, application, adapter, bootstrap)
- [x] 7. Comunicação entre módulos (Facade + ACL, eventos, o que é proibido)
- [x] 8. Banco de dados e configuração (schemas, Flyway, `application.yml`)
- [x] 9. Convenções de organização (nomes, pacotes, onde colocar cada código)
- [x] 10. Testes por camada + testes de arquitetura (ArchUnit)
- [x] 11. Checklist de conformidade
- [x] 12. Trade-offs e caminho de evolução para microsserviços
- [x] 13. Comparativo direto com o template Clean
- [x] 14. Quiz de fixação com respostas

---

## 4. Roteiro para aplicar o template em um projeto real

### Fase 0: Decisão (½ dia)
- [ ] Confirmar que o domínio justifica Hexagonal (ver [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Hexagonal/4. Trade-offs e Critérios de Adoção/4.2 Quando Usar e Quando Evitar/4.2.1. Cenários Favoráveis/4.2.1.1. Quando Usar Arquitetura Hexagonal|Quando Usar]])
- [ ] Listar os bounded contexts candidatos (Event Storming ou conversa com o negócio)
- [ ] Registrar a decisão num ADR (`docs/adr/0001-monolito-modular-hexagonal.md`)

### Fase 1: Esqueleto (1 dia)
- [ ] Criar o POM pai, `shared-kernel` e `bootstrap`
- [ ] Criar **um** módulo de negócio com os 4 submódulos vazios
- [ ] Configurar Enforcer (dependências banidas) e o módulo `architecture-tests`
- [ ] Pipeline de CI rodando `mvn verify` (o build quebra se a arquitetura for violada)

### Fase 2: Fatia vertical (2 a 3 dias)
- [ ] Implementar **um caso de uso completo** ponta a ponta (controller → use case → domínio → repositório)
- [ ] Escrever o teste de domínio puro, o teste do use case com fake e o teste do adapter com Testcontainers
- [ ] Validar com o time: o esqueleto é compreensível? O build barra as violações de propósito?

### Fase 3: Segundo módulo e integração (2 dias)
- [ ] Criar o segundo contexto e o `-api` do primeiro
- [ ] Implementar a chamada síncrona (Facade + adapter com ACL) e um evento assíncrono
- [ ] Criar schemas separados e migrations por módulo

### Fase 4: Escala (contínuo)
- [ ] Adicionar módulos novos copiando o esqueleto
- [ ] Revisar o checklist de conformidade a cada Pull Request
- [ ] A cada trimestre, reavaliar se algum módulo merece virar microsserviço

---

## 5. Critérios de aceite do template

- Um dev novo consegue responder "onde coloco este código?" só com a tabela da seção 9.
- Tentar importar `jakarta.persistence` no domínio **quebra o build**.
- Tentar importar uma classe interna de outro módulo **quebra o build**.
- Dá para trocar o adapter de persistência de um módulo sem tocar em `domain` nem `application`.
- O documento segue o mesmo formato do template Clean (callout, diagramas ASCII, tags, quiz com respostas).

---

> **Gerado a partir de:** [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Hexagonal/0 Hexagonal (Glossário )|Glossário Hexagonal]]
>
> **Resultado:** [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Hexagonal/Template Monolítico Modular (Multi-Module Hexagonal Architecture)|Template Monolítico Modular (Multi-Module Hexagonal Architecture)]]
