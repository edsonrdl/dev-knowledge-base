# 📚 Guia de Estudos: IA Aplicada ao Desenvolvimento de Software
#ia #desenvolvimento #agentes #produtividade

> [!info] Visão Geral
> Como a IA entra no dia a dia de quem desenvolve software: dos assistentes de autocomplete aos agentes de código, passando por cada etapa do ciclo de vida (especificação, implementação, testes, revisão, operação), pelas práticas para trabalhar bem com agentes (contexto, fluxos, ferramentas), pelo **controle de custo e de tokens** e pelos riscos de qualidade e adoção em equipe. É a visão do **usuário-desenvolvedor**; a construção de sistemas com LLMs está em [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/0 Engenharia de IA Aplicada (AI Engineering) ( Glossário )|Engenharia de IA Aplicada (AI Engineering)]].

---

## 1 Domínio: Panorama e Modos de Uso

### 1.1 Do Autocomplete aos Agentes
- **1.1.1. Níveis de autonomia**
  - [ ] 1.1.1.1. Autocomplete e chat — o assistente que sugere
  - [ ] 1.1.1.2. Agentes de código — do pedido ao pull request
  - [ ] 1.1.1.3. Equipes de agentes especializados

### 1.2 Vibe Coding vs Engenharia Assistida por IA
- **1.2.1. Estilos de trabalho**
  - [ ] 1.2.1.1. O que é vibe coding e quando é aceitável
  - [ ] 1.2.1.2. Engenharia assistida — o humano no controle

---

## 2 Domínio: IA no Ciclo de Vida do Software

### 2.1 Planejamento e Projeto
- **2.1.1. Requisitos e especificações**
  - [ ] 2.1.1.1. Da ideia à especificação com IA (ligação com SDD)
- **2.1.2. Arquitetura e decisões**
  - [ ] 2.1.2.1. IA como parceira de design — ADRs, trade-offs e revisão de arquitetura

### 2.2 Implementação
- **2.2.1. Geração e transformação de código**
  - [ ] 2.2.1.1. Geração de código, refatoração e migração de código legado
- **2.2.2. Aprendizado de bases desconhecidas**
  - [ ] 2.2.2.1. Explorar e entender um repositório novo com IA

### 2.3 Qualidade
- **2.3.1. Testes**
  - [ ] 2.3.1.1. Geração de testes — o que funciona e o que revisar
- **2.3.2. Revisão e depuração**
  - [ ] 2.3.2.1. Revisão de código por IA — risco por nível de criticidade
  - [ ] 2.3.2.2. Depuração e análise de logs e erros

### 2.4 Operação e Documentação
- **2.4.1. DevOps e documentação**
  - [ ] 2.4.1.1. IA em infraestrutura como código, pipelines e resposta a incidentes
  - [ ] 2.4.1.2. Documentação viva — READMEs, ADRs e changelogs gerados e mantidos

---

## 3 Domínio: Trabalhando com Agentes de Código

### 3.1 Contexto e Instruções
- **3.1.1. Arquivos de instruções**
  - [ ] 3.1.1.1. CLAUDE.md, AGENTS.md e regras de projeto — o que escrever e o que evitar
- **3.1.2. Engenharia de contexto**
  - [ ] 3.1.2.1. Context engineering — dar ao agente só o contexto certo
- **3.1.3. Ferramentas**
  - [ ] 3.1.3.1. MCP e ferramentas externas — ampliar o que o agente alcança

### 3.2 Fluxos de Trabalho
- **3.2.1. Ciclo de trabalho**
  - [ ] 3.2.1.1. Planejar, implementar e verificar — o ciclo com agentes
- **3.2.2. Paralelismo e automação**
  - [ ] 3.2.2.1. Subagentes, tarefas em paralelo e agentes em segundo plano
  - [ ] 3.2.2.2. Hooks, skills e automações de rotina

---

## 4 Domínio: Custo e Otimização de Tokens

### 4.1 Entendendo o Custo
- **4.1.1. Onde os tokens vão**
  - [ ] 4.1.1.1. Anatomia do consumo — contexto, saída, ferramentas e histórico
- **4.1.2. Medição**
  - [ ] 4.1.2.1. Medir antes de otimizar — logs, painéis e orçamentos

### 4.2 Técnicas de Economia
- **4.2.1. Cache e estrutura do prompt**
  - [ ] 4.2.1.1. Prompt caching e a ordem do prompt (fixo no início, variável no fim)
- **4.2.2. Escolha do modelo**
  - [ ] 4.2.2.1. Roteamento de modelos — modelo pequeno para o simples, grande para o difícil
- **4.2.3. Contexto enxuto**
  - [ ] 4.2.3.1. Limpar e compactar o contexto, leitura direcionada e arquivos de instruções curtos
- **4.2.4. Processamento em lote**
  - [ ] 4.2.4.1. API em lote, cache semântico e consolidação de chamadas

---

## 5 Domínio: Riscos, Qualidade e Adoção

### 5.1 Riscos
- **5.1.1. Revisão e qualidade**
  - [ ] 5.1.1.1. O gargalo da revisão — mais código gerado, mais código a revisar
  - [ ] 5.1.1.2. Drift — quando o resultado parece certo e resolve o problema errado
- **5.1.2. Segurança**
  - [ ] 5.1.2.1. Segurança do código gerado, dependências e segredos

### 5.2 Adoção em Equipe
- **5.2.1. Introdução gradual**
  - [ ] 5.2.1.1. Pilotos, métricas de valor e custo-benefício
- **5.2.2. Políticas**
  - [ ] 5.2.2.1. Privacidade, dados da empresa e uso responsável

---

> **Links Relacionados:**
> [[14. Inteligência Artificial e Machine Learning/Spec-Driven Development (SDD)/0 Spec-Driven Development (SDD) (Glossário )|Spec-Driven Development (SDD)]]
> [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/0 Engenharia de IA Aplicada (AI Engineering) ( Glossário )|Engenharia de IA Aplicada (AI Engineering)]]
> [[14. Inteligência Artificial e Machine Learning/Agentic Workflows e Orquestração/0 Agentic Workflows e Orquestração (Glossário )|Agentic Workflows e Orquestração]]
> [[14. Inteligência Artificial e Machine Learning/Protocolos de Agentes — MCP e A2A/0 Protocolos de Agentes — MCP e A2A (Glossário )|Protocolos de Agentes — MCP e A2A]]

> **Glossário Pai:** [[0 Glossário/Glossário|Base de Conhecimento Tecnológico]]
