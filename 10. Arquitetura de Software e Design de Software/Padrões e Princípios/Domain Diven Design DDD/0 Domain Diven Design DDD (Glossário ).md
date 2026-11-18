# 📚 Guia de Estudos: Domain-Driven Design (DDD)
#arquitetura #ddd #domain-driven-design #design-estrategico #design-tatico

> [!info] Visão Geral
> O Domain-Driven Design (DDD), idealizado por Eric Evans, é uma abordagem de desenvolvimento de software cujo propósito primário é alinhar a implementação técnica do código diretamente com as regras e realidades do negócio. Ele não é uma arquitetura de software (como MVC ou Clean), mas sim um conjunto de práticas e padrões que visa modelar domínios complexos, garantindo que desenvolvedores e especialistas de negócio falem exatamente a mesma língua.

---

## 1 Domínio: Pilares Fundamentais do DDD

### 1.1 Alicerces da Modelagem
- **1.1.1. O Domínio e os Domain Experts**
  - [x] [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Domain Diven Design DDD/1. Pilares Fundamentais do DDD/1.1 Alicerces da Modelagem/1.1.1. O Domínio e os Domain Experts/1.1.1.1. O que é DDD, o Domínio e os Domain Experts|1.1.1.1. O que é DDD, o Domínio e os Domain Experts]]
- **1.1.2. Linguagem Ubíqua (Ubiquitous Language)**
  - [x] [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Domain Diven Design DDD/1. Pilares Fundamentais do DDD/1.1 Alicerces da Modelagem/1.1.2. Linguagem Ubíqua/1.1.2.1. Linguagem Ubíqua e seu reflexo exato no código|1.1.2.1. Linguagem Ubíqua e seu reflexo exato no código]]
- **1.1.3. Separação de Preocupações (Estratégico vs Tático)**
  - [x] [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Domain Diven Design DDD/1. Pilares Fundamentais do DDD/1.1 Alicerces da Modelagem/1.1.3. Separação de Preocupações/1.1.3.1. Design Estratégico (o quê e onde) vs Design Tático (como)|1.1.3.1. Design Estratégico (o quê e onde) vs Design Tático (como)]]

---

## 2 Domínio: Design Estratégico (Espaço do Problema)

### 2.1 Subdomínios (Subdomains)
- **2.1.1. Core Domain (Domínio Principal)**
  - [x] [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Domain Diven Design DDD/2. Design Estratégico/2.1 Subdomínios/2.1.1. Core Domain/2.1.1.1. Core Domain — o diferencial competitivo|2.1.1.1. Core Domain — o diferencial competitivo]]
- **2.1.2. Supporting Subdomain (Domínio de Suporte)**
  - [x] [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Domain Diven Design DDD/2. Design Estratégico/2.1 Subdomínios/2.1.2. Supporting Subdomain/2.1.2.1. Supporting Subdomain — necessário, mas não diferencial|2.1.2.1. Supporting Subdomain — necessário, mas não diferencial]]
- **2.1.3. Generic Subdomain (Domínio Genérico)**
  - [ ] 2.1.3.1. Generic Subdomain — comprar pronto ou usar Open Source

### 2.2 Bounded Contexts (Contextos Delimitados)
- **2.2.1. Fronteiras de Escopo**
  - [x] [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Domain Diven Design DDD/2. Design Estratégico/2.2 Bounded Contexts/2.2.1. Fronteiras de Escopo/2.2.1.1. Bounded Context — a fronteira do modelo|2.2.1.1. Bounded Context — a fronteira do modelo]]
- **2.2.2. Autonomia**
  - [ ] 2.2.2.1. Mesmo termo, modelos diferentes em cada contexto

### 2.3 Context Mapping (Mapeamento de Contexto)
- **2.3.1. Padrões de Integração entre Bounded Contexts**
  - [ ] 2.3.1.1. Shared Kernel
  - [ ] 2.3.1.2. Customer-Supplier (Upstream e Downstream)
  - [ ] 2.3.1.3. Anticorruption Layer (ACL)

---

## 3 Domínio: Design Tático (Espaço da Solução)

### 3.1 Entidades e Objetos de Valor
- **3.1.1. Entidades (Entities)**
  - [ ] 3.1.1.1. Entities — identidade única e ciclo de vida
- **3.1.2. Objetos de Valor (Value Objects)**
  - [ ] 3.1.2.1. Value Objects — sem identidade e imutáveis

### 3.2 Agregados e Repositórios
- **3.2.1. Agregados e Raízes de Agregação**
  - [x] [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Domain Diven Design DDD/3. Design Tático/3.2 Agregados e Repositórios/3.2.1. Agregados e Raízes de Agregação/3.2.1.1. Aggregates e Aggregate Root — conceito e implementação|3.2.1.1. Aggregates e Aggregate Root — conceito e implementação]]
- **3.2.2. Repositórios (Repositories)**
  - [ ] 3.2.2.1. Repositories — coleção em memória e a regra de ouro das raízes

### 3.3 Serviços e Eventos
- **3.3.1. Serviços de Domínio (Domain Services)**
  - [ ] 3.3.1.1. Domain Services — lógica que não pertence a uma entidade
- **3.3.2. Eventos de Domínio**
  - [x] [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Domain Diven Design DDD/3. Design Tático/3.3 Serviços e Eventos/3.3.2. Eventos de Domínio/3.3.2.1. Domain Events — conceito e implementação|3.3.2.1. Domain Events — conceito e implementação]]
  - [x] [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Domain Diven Design DDD/3. Design Tático/3.3 Serviços e Eventos/3.3.2. Eventos de Domínio/3.3.2.2. Publicando e reagindo a Domain Events (Spring, Kafka e Outbox)|3.3.2.2. Publicando e reagindo a Domain Events (Spring, Kafka e Outbox)]]

---

## 4 Domínio: Decisões Arquiteturais e Trade-offs

### 4.1 Vantagens e Desvantagens
- **4.1.1. Otimizações e Ganhos**
  - [ ] 4.1.1.1. Manutenibilidade e alinhamento com o negócio
- **4.1.2. Custos Computacionais e Operacionais**
  - [ ] 4.1.2.1. Curva de aprendizado e complexidade inicial

### 4.2 Critérios de Adoção
- **4.2.1. Quando Usar**
  - [ ] 4.2.1.1. Domínios complexos e base para microsserviços
- **4.2.2. Quando Evitar**
  - [ ] 4.2.2.1. Aplicações CRUD e sistemas data-driven

---

## 5 Domínio: Relacionamento com Outros Padrões e Exemplos

### 5.1 Relacionamento com Arquiteturas Modernas
- **5.1.1. DDD vs Arquitetura Hexagonal (Ports and Adapters)**
  - [ ] 5.1.1.1. DDD e Hexagonal — o modelo rico blindado por portas
- **5.1.2. DDD vs Clean Architecture**
  - [ ] 5.1.2.1. DDD e Clean Architecture — camadas para o design tático
- **5.1.3. DDD e Microsserviços**
  - [ ] 5.1.3.1. Bounded Contexts como fronteira de microsserviços

### 5.2 Exemplos Práticos de Modelagem
- **5.2.1. Modelagem Multi-Contexto (Produto)**
  - [ ] 5.2.1.1. Produto em Vendas vs Produto em Estoque e Logística
- **5.2.2. Organização Típica de Pastas**
  - [ ] 5.2.2.1. Agrupar por negócio e não por camada técnica

---

> **Links Relacionados:**
> [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Hexagonal/0 Hexagonal (Glossário )|Arquitetura Hexagonal]]
> [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Clean architecture/0 Clean Architecture (Glossário )|Clean Architecture]]
> [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Microservices/0 Microservices (Glossário )|Microservices]]
> [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/🏛️ Clean Architecture vs Hexagonal Architecture - Análise Completa|Clean Architecture vs Hexagonal]]
> CQRS e Event-Driven Architecture (ainda sem glossário próprio; veja o Glossário geral)
