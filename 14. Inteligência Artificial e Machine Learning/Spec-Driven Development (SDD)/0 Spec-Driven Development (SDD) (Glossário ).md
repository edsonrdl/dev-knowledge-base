# 📚 Guia de Estudos: Spec-Driven Development (SDD)
#ia #desenvolvimento #sdd #agentes #engenharia-de-software

> [!info] Visão Geral
> Spec-Driven Development (SDD) é a metodologia de desenvolvimento assistido por IA em que a **especificação formal** — e não o código — é o artefato central: primeiro se define *o quê* e *por quê*, depois *como*, e só então agentes de código geram a implementação. Este guia cobre o problema que o SDD resolve (vibe coding), a anatomia de uma boa spec, o fluxo de trabalho, as ferramentas (GitHub Spec Kit, Kiro, Tessl, OpenSpec, BMAD) e a prática de adoção, incluindo trade-offs e projetos existentes (brownfield).

---

## 1 Domínio: Fundamentos de SDD

### 1.1 O Problema que o SDD Resolve
- **1.1.1. Vibe Coding e o Custo da Ambiguidade**
  - [x] [[14. Inteligência Artificial e Machine Learning/Spec-Driven Development (SDD)/1. Fundamentos de SDD/1.1 O Problema que o SDD Resolve/1.1.1. Vibe Coding e o Custo da Ambiguidade/1.1.1.1. Do Vibe Coding ao Código Frágil — Por que Prompts Soltos Não Escalam|1.1.1.1. Do Vibe Coding ao Código Frágil — Por que Prompts Soltos Não Escalam]]
- **1.1.2. A Ideia Central do SDD**
  - [x] [[14. Inteligência Artificial e Machine Learning/Spec-Driven Development (SDD)/1. Fundamentos de SDD/1.1 O Problema que o SDD Resolve/1.1.2. A Ideia Central do SDD/1.1.2.1. O que é Spec-Driven Development e Spec como Fonte da Verdade|1.1.2.1. O que é Spec-Driven Development e Spec como Fonte da Verdade]]

### 1.2 SDD no Mapa das Metodologias
- **1.2.1. SDD vs TDD, BDD e Design-First**
  - [x] [[14. Inteligência Artificial e Machine Learning/Spec-Driven Development (SDD)/1. Fundamentos de SDD/1.2 SDD no Mapa das Metodologias/1.2.1. SDD vs TDD, BDD e Design-First/1.2.1.1. SDD vs TDD, BDD e Design-First — Semelhanças e Diferenças|1.2.1.1. SDD vs TDD, BDD e Design-First — Semelhanças e Diferenças]]
- **1.2.2. Os Três Níveis de Adoção**
  - [x] [[14. Inteligência Artificial e Machine Learning/Spec-Driven Development (SDD)/1. Fundamentos de SDD/1.2 SDD no Mapa das Metodologias/1.2.2. Os Três Níveis de Adoção/1.2.2.1. Spec-First, Spec-Anchored e Spec-as-Source|1.2.2.1. Spec-First, Spec-Anchored e Spec-as-Source]]

---

## 2 Domínio: Anatomia de uma Especificação

### 2.1 Os Artefatos do SDD
- **2.1.1. Constitution**
  - [x] [[14. Inteligência Artificial e Machine Learning/Spec-Driven Development (SDD)/2. Anatomia de uma Especificação/2.1 Os Artefatos do SDD/2.1.1. Constitution/2.1.1.1. Constitution — Os Princípios Inegociáveis do Projeto|2.1.1.1. Constitution — Os Princípios Inegociáveis do Projeto]]
- **2.1.2. Spec Funcional**
  - [x] [[14. Inteligência Artificial e Machine Learning/Spec-Driven Development (SDD)/2. Anatomia de uma Especificação/2.1 Os Artefatos do SDD/2.1.2. Spec Funcional/2.1.2.1. Spec Funcional — O Quê e o Porquê (User Stories e Requisitos)|2.1.2.1. Spec Funcional — O Quê e o Porquê (User Stories e Requisitos)]]
- **2.1.3. Plano Técnico**
  - [x] [[14. Inteligência Artificial e Machine Learning/Spec-Driven Development (SDD)/2. Anatomia de uma Especificação/2.1 Os Artefatos do SDD/2.1.3. Plano Técnico/2.1.3.1. Plano Técnico — O Como (Arquitetura, Stack e Contratos)|2.1.3.1. Plano Técnico — O Como (Arquitetura, Stack e Contratos)]]
- **2.1.4. Tasks**
  - [x] [[14. Inteligência Artificial e Machine Learning/Spec-Driven Development (SDD)/2. Anatomia de uma Especificação/2.1 Os Artefatos do SDD/2.1.4. Tasks/2.1.4.1. Tasks — Quebrando o Plano em Unidades Executáveis por Agentes|2.1.4.1. Tasks — Quebrando o Plano em Unidades Executáveis por Agentes]]

### 2.2 Escrevendo Specs que Funcionam
- **2.2.1. Requisitos Testáveis**
  - [x] [[14. Inteligência Artificial e Machine Learning/Spec-Driven Development (SDD)/2. Anatomia de uma Especificação/2.2 Escrevendo Specs que Funcionam/2.2.1. Requisitos Testáveis/2.2.1.1. Critérios de Aceite — Given-When-Then e EARS|2.2.1.1. Critérios de Aceite — Given-When-Then e EARS]]
- **2.2.2. Eliminando Ambiguidade**
  - [x] [[14. Inteligência Artificial e Machine Learning/Spec-Driven Development (SDD)/2. Anatomia de uma Especificação/2.2 Escrevendo Specs que Funcionam/2.2.2. Eliminando Ambiguidade/2.2.2.1. Non-Goals, Edge Cases e Marcadores de Clarificação|2.2.2.1. Non-Goals, Edge Cases e Marcadores de Clarificação]]

---

## 3 Domínio: O Fluxo de Trabalho SDD

### 3.1 O Ciclo Specify, Plan, Tasks, Implement
- **3.1.1. Fases do Ciclo**
  - [x] [[14. Inteligência Artificial e Machine Learning/Spec-Driven Development (SDD)/3. O Fluxo de Trabalho SDD/3.1 O Ciclo Specify, Plan, Tasks, Implement/3.1.1. Fases do Ciclo/3.1.1.1. As Fases do Ciclo SDD e os Portões de Revisão Humana|3.1.1.1. As Fases do Ciclo SDD e os Portões de Revisão Humana]]

### 3.2 Validação e Consistência
- **3.2.1. Clarify, Analyze e Checklists**
  - [x] [[14. Inteligência Artificial e Machine Learning/Spec-Driven Development (SDD)/3. O Fluxo de Trabalho SDD/3.2 Validação e Consistência/3.2.1. Clarify, Analyze e Checklists/3.2.1.1. Clarify, Analyze e Checklists — Validando a Spec Antes do Código|3.2.1.1. Clarify, Analyze e Checklists — Validando a Spec Antes do Código]]
- **3.2.2. Evitando Spec Drift**
  - [x] [[14. Inteligência Artificial e Machine Learning/Spec-Driven Development (SDD)/3. O Fluxo de Trabalho SDD/3.2 Validação e Consistência/3.2.2. Evitando Spec Drift/3.2.2.1. Spec Drift — Mantendo Spec e Código Sincronizados|3.2.2.1. Spec Drift — Mantendo Spec e Código Sincronizados]]

---

## 4 Domínio: Ferramentas e Ecossistema

### 4.1 GitHub Spec Kit
- **4.1.1. Spec Kit na Prática**
  - [x] [[14. Inteligência Artificial e Machine Learning/Spec-Driven Development (SDD)/4. Ferramentas e Ecossistema/4.1 GitHub Spec Kit/4.1.1. Spec Kit na Prática/4.1.1.1. GitHub Spec Kit — Comandos specify, plan e tasks|4.1.1.1. GitHub Spec Kit — Comandos specify, plan e tasks]]

### 4.2 Kiro e Outras Ferramentas
- **4.2.1. Kiro (AWS)**
  - [x] [[14. Inteligência Artificial e Machine Learning/Spec-Driven Development (SDD)/4. Ferramentas e Ecossistema/4.2 Kiro e Outras Ferramentas/4.2.1. Kiro (AWS)/4.2.1.1. Kiro — IDE Agêntica com Requirements, Design e Tasks|4.2.1.1. Kiro — IDE Agêntica com Requirements, Design e Tasks]]
- **4.2.2. Tessl, OpenSpec e BMAD**
  - [x] [[14. Inteligência Artificial e Machine Learning/Spec-Driven Development (SDD)/4. Ferramentas e Ecossistema/4.2 Kiro e Outras Ferramentas/4.2.2. Tessl, OpenSpec e BMAD/4.2.2.1. Comparativo de Ferramentas SDD e Quando Usar Cada Uma|4.2.2.1. Comparativo de Ferramentas SDD e Quando Usar Cada Uma]]

### 4.3 SDD com Agentes de Código
- **4.3.1. Contexto Persistente para Agentes**
  - [x] [[14. Inteligência Artificial e Machine Learning/Spec-Driven Development (SDD)/4. Ferramentas e Ecossistema/4.3 SDD com Agentes de Código/4.3.1. Contexto Persistente para Agentes/4.3.1.1. CLAUDE.md, AGENTS.md e Steering Files como Ponte entre Spec e Agente|4.3.1.1. CLAUDE.md, AGENTS.md e Steering Files como Ponte entre Spec e Agente]]

---

## 5 Domínio: Prática e Adoção

### 5.1 Exemplo Ponta a Ponta
- **5.1.1. Do Zero à Feature**
  - [x] [[14. Inteligência Artificial e Machine Learning/Spec-Driven Development (SDD)/5. Prática e Adoção/5.1 Exemplo Ponta a Ponta/5.1.1. Do Zero à Feature/5.1.1.1. Exemplo Completo — Implementando uma Feature com SDD|5.1.1.1. Exemplo Completo — Implementando uma Feature com SDD]]

### 5.2 Quando e Como Adotar SDD
- **5.2.1. Trade-offs e Limitações**
  - [x] [[14. Inteligência Artificial e Machine Learning/Spec-Driven Development (SDD)/5. Prática e Adoção/5.2 Quando e Como Adotar SDD/5.2.1. Trade-offs e Limitações/5.2.1.1. Quando Usar, Quando Evitar e Limitações do SDD|5.2.1.1. Quando Usar, Quando Evitar e Limitações do SDD]]
- **5.2.2. Brownfield e Times**
  - [x] [[14. Inteligência Artificial e Machine Learning/Spec-Driven Development (SDD)/5. Prática e Adoção/5.2 Quando e Como Adotar SDD/5.2.2. Brownfield e Times/5.2.2.1. SDD em Projetos Existentes (Brownfield) e em Equipe|5.2.2.1. SDD em Projetos Existentes (Brownfield) e em Equipe]]

---

> **Links Relacionados:**
> [[14. Inteligência Artificial e Machine Learning/Agentic Workflows e Orquestração/0 Agentic Workflows e Orquestração (Glossário )|Agentic Workflows e Orquestração]]
> [[14. Inteligência Artificial e Machine Learning/Harness — Runtime de Controle de Agentes/0 Harness — Runtime de Controle de Agentes (Glossário )|Harness — Runtime de Controle de Agentes]]
> [[14. Inteligência Artificial e Machine Learning/Protocolos de Agentes — MCP e A2A/0 Protocolos de Agentes — MCP e A2A (Glossário )|Protocolos de Agentes — MCP e A2A]]

> **Glossário Pai:** [[0 Glossário/Glossário|Base de Conhecimento Tecnológico]]
