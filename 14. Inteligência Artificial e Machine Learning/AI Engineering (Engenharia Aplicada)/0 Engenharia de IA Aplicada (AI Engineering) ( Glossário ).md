# 📚 Guia de Estudos: Engenharia de IA Aplicada (AI Engineering)

#ia #agentes #rag #llmops #arquitetura #finetuning #embedding #cache #retrieval

> [!info] Visão Geral
> A Engenharia de IA Aplicada (AI Engineering) não foca em treinar modelos do zero, mas na orquestração, integração e otimização de sistemas que consomem Modelos de Linguagem (LLMs) em produção. Este guia mapeia desde o domínio do contexto (prompting, RAG) até fluxos agênticos autônomos e a infraestrutura para monitorar essas decisões (LLMOps). É o complemento **prático** do guia [[14. Inteligência Artificial e Machine Learning/Como LLMs Funcionam/0 Como LLMs Funcionam (Glossário )|Como LLMs Funcionam]], que cobre o lado **teórico**.

---

## 0 Domínio: Guia de Orientação — "O Que Faz Cada Coisa?"

### 0.1 O Mapa Mental do Sistema RAG
- **0.1.1. Visão Geral do Pipeline de 7 Responsabilidades**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/0. Guia de Orientação/0.1 O Mapa Mental do Sistema RAG/0.1.1. Visão Geral do Pipeline de 7 Responsabilidades/0.1.1.1. O Diagrama das 7 Responsabilidades de um Sistema RAG|0.1.1.1. O Diagrama das 7 Responsabilidades de um Sistema RAG]]

### 0.2 As 7 Categorias de Ferramentas
- **0.2.1. LLMs (Os Cérebros)**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/0. Guia de Orientação/0.2 As 7 Categorias de Ferramentas/0.2.1. LLMs (Os Cérebros)/0.2.1.1. Comparativo de LLMs e Quando Usar Cada Um|0.2.1.1. Comparativo de LLMs e Quando Usar Cada Um]]
- **0.2.2. Frameworks de Orquestração**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/0. Guia de Orientação/0.2 As 7 Categorias de Ferramentas/0.2.2. Frameworks de Orquestração/0.2.2.1. Comparativo de Frameworks e Quando Usar Cada Um|0.2.2.1. Comparativo de Frameworks e Quando Usar Cada Um]]
- **0.2.3. Bancos Vetoriais**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/0. Guia de Orientação/0.2 As 7 Categorias de Ferramentas/0.2.3. Bancos Vetoriais/0.2.3.1. Comparativo de Bancos Vetoriais e Quando Usar Cada Um|0.2.3.1. Comparativo de Bancos Vetoriais e Quando Usar Cada Um]]
- **0.2.4. Extração de Dados**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/0. Guia de Orientação/0.2 As 7 Categorias de Ferramentas/0.2.4. Extração de Dados/0.2.4.1. Comparativo de Ferramentas de Extração e Quando Usar Cada Uma|0.2.4.1. Comparativo de Ferramentas de Extração e Quando Usar Cada Uma]]
- **0.2.5. Acesso a LLMs Open-Source**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/0. Guia de Orientação/0.2 As 7 Categorias de Ferramentas/0.2.5. Acesso a LLMs Open-Source/0.2.5.1. Comparativo de Plataformas e Quando Usar Cada Uma|0.2.5.1. Comparativo de Plataformas e Quando Usar Cada Uma]]
- **0.2.6. Text Embeddings**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/0. Guia de Orientação/0.2 As 7 Categorias de Ferramentas/0.2.6. Text Embeddings/0.2.6.1. Comparativo de Modelos de Embedding e Quando Usar Cada Um|0.2.6.1. Comparativo de Modelos de Embedding e Quando Usar Cada Um]]
- **0.2.7. Avaliação**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/0. Guia de Orientação/0.2 As 7 Categorias de Ferramentas/0.2.7. Avaliação/0.2.7.1. Comparativo de Ferramentas de Avaliação e Quando Usar Cada Uma|0.2.7.1. Comparativo de Ferramentas de Avaliação e Quando Usar Cada Uma]]

### 0.3 Como as Categorias se Conectam na Prática
- **0.3.1. Exemplo de Pipeline Completo**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/0. Guia de Orientação/0.3 Como as Categorias se Conectam na Prática/0.3.1. Exemplo de Pipeline Completo/0.3.1.1. Construindo um Chatbot de Contratos — As 7 Categorias em um Único Pipeline|0.3.1.1. Construindo um Chatbot de Contratos — As 7 Categorias em um Único Pipeline]]

---

## 1 Domínio: Fundamentos de LLM e Unidades de Controle

### 1.1 Contexto, Tokens e Inferência
- **1.1.1. Gestão de Context Window**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/1. Fundamentos de LLM e Unidades de Controle/1.1 Contexto, Tokens e Inferência/1.1.1. Gestão de Context Window/1.1.1.1. Gestão de Context Window — Tokens, Custo, Long Context e Prompt Caching|1.1.1.1. Gestão de Context Window — Tokens, Custo, Long Context e Prompt Caching]]
- **1.1.2. Tuning de Parâmetros de API**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/1. Fundamentos de LLM e Unidades de Controle/1.1 Contexto, Tokens e Inferência/1.1.2. Tuning de Parâmetros de API/1.1.2.1. Temperature, Top-P e Semantic Caching|1.1.2.1. Temperature, Top-P e Semantic Caching]]
- **1.1.3. Modelos de Raciocínio (Thinking Models)**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/1. Fundamentos de LLM e Unidades de Controle/1.1 Contexto, Tokens e Inferência/1.1.3. Modelos de Raciocínio (Thinking Models)/1.1.3.1. Modelos de Raciocínio — Extended Thinking, o1-o3 e Budget de Tokens|1.1.3.1. Modelos de Raciocínio — Extended Thinking, o1-o3 e Budget de Tokens]]

### 1.2 Engenharia de Prompts Avançada
- **1.2.1. Técnicas de Raciocínio (Reasoning)**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/1. Fundamentos de LLM e Unidades de Controle/1.2 Engenharia de Prompts Avançada/1.2.1. Técnicas de Raciocínio (Reasoning)/1.2.1.1. Few-shot, Chain-of-Thought e Self-Consistency|1.2.1.1. Few-shot, Chain-of-Thought e Self-Consistency]]
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/1. Fundamentos de LLM e Unidades de Controle/1.2 Engenharia de Prompts Avançada/1.2.1. Técnicas de Raciocínio (Reasoning)/1.2.1.2. Tree of Thought e Meta-Prompting|1.2.1.2. Tree of Thought e Meta-Prompting]]
- **1.2.2. Structured Outputs**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/1. Fundamentos de LLM e Unidades de Controle/1.2 Engenharia de Prompts Avançada/1.2.2. Structured Outputs/1.2.2.1. Structured Outputs — JSON Estrito, Pydantic-Zod e Constrained Decoding|1.2.2.1. Structured Outputs — JSON Estrito, Pydantic-Zod e Constrained Decoding]]

---

## 2 Domínio: Retrieval-Augmented Generation (RAG) Avançado

### 2.1 Ingestão e Processamento (Pipeline de Dados)
- **2.1.1. Chunking Strategies**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/2. Retrieval-Augmented Generation (RAG) Avançado/2.1 Ingestão e Processamento (Pipeline de Dados)/2.1.1. Chunking Strategies/2.1.1.1. Chunking — Fixed-size, Recursive, Semantic e Late Chunking|2.1.1.1. Chunking — Fixed-size, Recursive, Semantic e Late Chunking]]
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/2. Retrieval-Augmented Generation (RAG) Avançado/2.1 Ingestão e Processamento (Pipeline de Dados)/2.1.1. Chunking Strategies/2.1.1.2. Chunking Avançado — Propositional, Parent-Child e Indexação de Metadados|2.1.1.2. Chunking Avançado — Propositional, Parent-Child e Indexação de Metadados]]
- **2.1.2. Embeddings e Bancos Vetoriais**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/2. Retrieval-Augmented Generation (RAG) Avançado/2.1 Ingestão e Processamento (Pipeline de Dados)/2.1.2. Embeddings e Bancos Vetoriais/2.1.2.1. Modelos de Embedding Modernos e Matryoshka|2.1.2.1. Modelos de Embedding Modernos e Matryoshka]]
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/2. Retrieval-Augmented Generation (RAG) Avançado/2.1 Ingestão e Processamento (Pipeline de Dados)/2.1.2. Embeddings e Bancos Vetoriais/2.1.2.2. Embeddings Multimodais (CLIP) e Bancos Vetoriais|2.1.2.2. Embeddings Multimodais (CLIP) e Bancos Vetoriais]]
- **2.1.3. Algoritmos de Busca Aproximada (ANN)**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/2. Retrieval-Augmented Generation (RAG) Avançado/2.1 Ingestão e Processamento (Pipeline de Dados)/2.1.3. Algoritmos de Busca Aproximada (ANN)/2.1.3.1. HNSW, IVF e Product Quantization|2.1.3.1. HNSW, IVF e Product Quantization]]

### 2.2 RAG de Próxima Geração (Retrieval Otimizado)
- **2.2.1. Técnicas de Busca e Refinamento**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/2. Retrieval-Augmented Generation (RAG) Avançado/2.2 RAG de Próxima Geração (Retrieval Otimizado)/2.2.1. Técnicas de Busca e Refinamento/2.2.1.1. Hybrid Search (BM25 + Vetorial com RRF) e Self-Querying|2.2.1.1. Hybrid Search (BM25 + Vetorial com RRF) e Self-Querying]]
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/2. Retrieval-Augmented Generation (RAG) Avançado/2.2 RAG de Próxima Geração (Retrieval Otimizado)/2.2.1. Técnicas de Busca e Refinamento/2.2.1.2. Reranking com Cross-Encoder, GraphRAG e Small-to-Big Retrieval|2.2.1.2. Reranking com Cross-Encoder, GraphRAG e Small-to-Big Retrieval]]
- **2.2.2. Query Transformation**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/2. Retrieval-Augmented Generation (RAG) Avançado/2.2 RAG de Próxima Geração (Retrieval Otimizado)/2.2.2. Query Transformation/2.2.2.1. HyDE, Multi-Query Retrieval e Step-Back Prompting|2.2.2.1. HyDE, Multi-Query Retrieval e Step-Back Prompting]]

### 2.3 Extração de Dados — Ferramentas Detalhadas
- **2.3.1. Web Crawling e Scraping para RAG**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/2. Retrieval-Augmented Generation (RAG) Avançado/2.3 Extração de Dados — Ferramentas Detalhadas/2.3.1. Web Crawling e Scraping para RAG/2.3.1.1. Crawl4AI, FireCrawl e Scrape GraphAI|2.3.1.1. Crawl4AI, FireCrawl e Scrape GraphAI]]
- **2.3.2. Parsers de Documentos para RAG**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/2. Retrieval-Augmented Generation (RAG) Avançado/2.3 Extração de Dados — Ferramentas Detalhadas/2.3.2. Parsers de Documentos para RAG/2.3.2.1. MegaParser, Docling, LlamaParse e Extract Thinker|2.3.2.1. MegaParser, Docling, LlamaParse e Extract Thinker]]
- **2.3.3. Comparativo de Ferramentas de Extração**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/2. Retrieval-Augmented Generation (RAG) Avançado/2.3 Extração de Dados — Ferramentas Detalhadas/2.3.3. Comparativo de Ferramentas de Extração/2.3.3.1. Tabela de Decisão Consolidada — Qual Ferramenta de Extração Usar|2.3.3.1. Tabela de Decisão Consolidada — Qual Ferramenta de Extração Usar]]

---

## 3 Domínio: Embeddings — Tópicos Avançados

### 3.1 Estratégias de Embedding para Produção
- **3.1.1. Modelos e Benchmarks**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/3. Embeddings — Tópicos Avançados/3.1 Estratégias de Embedding para Produção/3.1.1. Modelos e Benchmarks/3.1.1.1. MTEB, Modelos Soberanos-Locais e Embeddings por Domínio|3.1.1.1. MTEB, Modelos Soberanos-Locais e Embeddings por Domínio]]
- **3.1.2. Estratégias de Fine-tuning de Embeddings**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/3. Embeddings — Tópicos Avançados/3.1 Estratégias de Embedding para Produção/3.1.2. Estratégias de Fine-tuning de Embeddings/3.1.2.1. Fine-tuning de Embeddings — Pares Sintéticos, Contrastive Learning e Asymmetric Embedding|3.1.2.1. Fine-tuning de Embeddings — Pares Sintéticos, Contrastive Learning e Asymmetric Embedding]]
- **3.1.3. Embedding de Dados Estruturados**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/3. Embeddings — Tópicos Avançados/3.1 Estratégias de Embedding para Produção/3.1.3. Embedding de Dados Estruturados/3.1.3.1. Embeddings de Tabelas, SQL e Código-Fonte|3.1.3.1. Embeddings de Tabelas, SQL e Código-Fonte]]

---

## 4 Domínio: Orquestração e Frameworks de Agentes

### 4.1 Padrões de Autonomia (Agentic Workflows)
- **4.1.1. Raciocínio e Planejamento**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/4. Orquestração e Frameworks de Agentes/4.1 Padrões de Autonomia (Agentic Workflows)/4.1.1. Raciocínio e Planejamento/4.1.1.1. ReAct, Plan-and-Execute e LATS|4.1.1.1. ReAct, Plan-and-Execute e LATS]]
- **4.1.2. Protocolos de Comunicação de Agentes**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/4. Orquestração e Frameworks de Agentes/4.1 Padrões de Autonomia (Agentic Workflows)/4.1.2. Protocolos de Comunicação de Agentes/4.1.2.1. MCP, A2A e OpenAI Responses API|4.1.2.1. MCP, A2A e OpenAI Responses API]]

### 4.2 Frameworks, Estado e Memória
- **4.2.1. Frameworks de Mercado**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/4. Orquestração e Frameworks de Agentes/4.2 Frameworks, Estado e Memória/4.2.1. Frameworks de Mercado/4.2.1.1. LangChain, LlamaIndex e LangGraph|4.2.1.1. LangChain, LlamaIndex e LangGraph]]
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/4. Orquestração e Frameworks de Agentes/4.2 Frameworks, Estado e Memória/4.2.1. Frameworks de Mercado/4.2.1.2. CrewAI, AutoGen, smolagents e Pydantic AI|4.2.1.2. CrewAI, AutoGen, smolagents e Pydantic AI]]
- **4.2.2. Gestão de Memória e Human-in-the-Loop**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/4. Orquestração e Frameworks de Agentes/4.2 Frameworks, Estado e Memória/4.2.2. Gestão de Memória e Human-in-the-Loop/4.2.2.1. Memória de Agentes, HITL e MemoryOS|4.2.2.1. Memória de Agentes, HITL e MemoryOS]]

### 4.3 Loop Engineering — Do Prompt ao Sistema Autônomo
- **4.3.1. Definição e Motivação**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/4. Orquestração e Frameworks de Agentes/4.3 Loop Engineering — Do Prompt ao Sistema Autônomo/4.3.1. Definição e Motivação/4.3.1.1. O Que É Loop Engineering e Por Que Emergiu|4.3.1.1. O Que É Loop Engineering e Por Que Emergiu]]
- **4.3.2. Os Quatro Componentes de um Loop Confiável**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/4. Orquestração e Frameworks de Agentes/4.3 Loop Engineering — Do Prompt ao Sistema Autônomo/4.3.2. Os Quatro Componentes de um Loop Confiável/4.3.2.1. Trigger, Goal Verificável, Verifier e Stop Rules|4.3.2.1. Trigger, Goal Verificável, Verifier e Stop Rules]]
- **4.3.3. Blocos de Construção de Loops em Produção**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/4. Orquestração e Frameworks de Agentes/4.3 Loop Engineering — Do Prompt ao Sistema Autônomo/4.3.3. Blocos de Construção de Loops em Produção/4.3.3.1. Automations, Worktrees, Skills, Plugins e Sub-agentes|4.3.3.1. Automations, Worktrees, Skills, Plugins e Sub-agentes]]

### 4.4 Graph Engineering — A Topologia da Orquestração Multi-Agente
- **4.4.1. Definição e Motivação**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/4. Orquestração e Frameworks de Agentes/4.4 Graph Engineering — A Topologia da Orquestração Multi-Agente/4.4.1. Definição e Motivação/4.4.1.1. O Que É Graph Engineering e a Diferença para Knowledge Graphs|4.4.1.1. O Que É Graph Engineering e a Diferença para Knowledge Graphs]]
- **4.4.2. Componentes de um Grafo de Agentes**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/4. Orquestração e Frameworks de Agentes/4.4 Graph Engineering — A Topologia da Orquestração Multi-Agente/4.4.2. Componentes de um Grafo de Agentes/4.4.2.1. Nodes, Edges, State e Conditional Routing|4.4.2.1. Nodes, Edges, State e Conditional Routing]]
- **4.4.3. Padrão Prático — Ciclo Avaliador-Otimizador**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/4. Orquestração e Frameworks de Agentes/4.4 Graph Engineering — A Topologia da Orquestração Multi-Agente/4.4.3. Padrão Prático — Ciclo Avaliador-Otimizador/4.4.3.1. O Fluxo Planner, Researcher, Writer e Evaluator com Loop de Revisão|4.4.3.1. O Fluxo Planner, Researcher, Writer e Evaluator com Loop de Revisão]]
- **4.4.4. Governança, Custo e Observabilidade em Produção**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/4. Orquestração e Frameworks de Agentes/4.4 Graph Engineering — A Topologia da Orquestração Multi-Agente/4.4.4. Governança, Custo e Observabilidade em Produção/4.4.4.1. Identidade por Nó, Controle de Custo e Observabilidade de Topologia|4.4.4.1. Identidade por Nó, Controle de Custo e Observabilidade de Topologia]]
- **4.4.5. Loop Engineering vs Graph Engineering**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/4. Orquestração e Frameworks de Agentes/4.4 Graph Engineering — A Topologia da Orquestração Multi-Agente/4.4.5. Loop Engineering vs Graph Engineering/4.4.5.1. Comparativo Loop Engineering e Graph Engineering — Camadas Complementares|4.4.5.1. Comparativo Loop Engineering e Graph Engineering — Camadas Complementares]]

---

## 5 Domínio: Ferramentas (Tool Calling) e Interação com o Mundo

### 5.1 Invocações e Segurança
- **5.1.1. Function Calling**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/5. Ferramentas (Tool Calling) e Interação com o Mundo/5.1 Invocações e Segurança/5.1.1. Function Calling/5.1.1.1. Function Calling — Como o LLM Invoca Ferramentas e Parallel Tool Calling|5.1.1.1. Function Calling — Como o LLM Invoca Ferramentas e Parallel Tool Calling]]
- **5.1.2. Computer Use e Multimodal Agents**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/5. Ferramentas (Tool Calling) e Interação com o Mundo/5.1 Invocações e Segurança/5.1.2. Computer Use e Multimodal Agents/5.1.2.1. Computer Use, Browser Use e Voice Agents|5.1.2.1. Computer Use, Browser Use e Voice Agents]]
- **5.1.3. Sandboxing e Execução de Código**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/5. Ferramentas (Tool Calling) e Interação com o Mundo/5.1 Invocações e Segurança/5.1.3. Sandboxing e Execução de Código/5.1.3.1. Sandboxing e Execução de Código — Riscos de RCE e Isolamento|5.1.3.1. Sandboxing e Execução de Código — Riscos de RCE e Isolamento]]

---

## 6 Domínio: Fine-Tuning e Adaptação de Modelos

### 6.1 Técnicas de Fine-Tuning
- **6.1.1. Full Fine-Tuning vs Parameter-Efficient**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/6. Fine-Tuning e Adaptação de Modelos/6.1 Técnicas de Fine-Tuning/6.1.1. Full Fine-Tuning vs Parameter-Efficient/6.1.1.1. Full Fine-Tuning, LoRA, QLoRA e DoRA|6.1.1.1. Full Fine-Tuning, LoRA, QLoRA e DoRA]]
- **6.1.2. Alinhamento e RLHF**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/6. Fine-Tuning e Adaptação de Modelos/6.1 Técnicas de Fine-Tuning/6.1.2. Alinhamento e RLHF/6.1.2.1. RLHF Clássico, DPO e as Variantes ORPO e SimPO|6.1.2.1. RLHF Clássico, DPO e as Variantes ORPO e SimPO]]
- **6.1.3. Dados para Fine-Tuning**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/6. Fine-Tuning e Adaptação de Modelos/6.1 Técnicas de Fine-Tuning/6.1.3. Dados para Fine-Tuning/6.1.3.1. Dados Sintéticos, Curadoria vs Volume e Quando NÃO Usar Fine-Tuning|6.1.3.1. Dados Sintéticos, Curadoria vs Volume e Quando NÃO Usar Fine-Tuning]]

---

## 7 Domínio: LLMOps, Observabilidade e Governança

### 7.1 Operacionalizando IA no Back-end
- **7.1.1. Observabilidade (Rastreio e Custos)**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/7. LLMOps, Observabilidade e Governança/7.1 Operacionalizando IA no Back-end/7.1.1. Observabilidade (Rastreio e Custos)/7.1.1.1. Observabilidade de LLMs — Caixa Preta, Tracing e OpenTelemetry|7.1.1.1. Observabilidade de LLMs — Caixa Preta, Tracing e OpenTelemetry]]
- **7.1.2. Evaluation Harness (Avaliação Sistemática)**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/7. LLMOps, Observabilidade e Governança/7.1 Operacionalizando IA no Back-end/7.1.2. Evaluation Harness (Avaliação Sistemática)/7.1.2.1. Eval Harness — Conceito e Ferramentas Ragas, DeepEval e Giskard|7.1.2.1. Eval Harness — Conceito e Ferramentas Ragas, DeepEval e Giskard]]
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/7. LLMOps, Observabilidade e Governança/7.1 Operacionalizando IA no Back-end/7.1.2. Evaluation Harness (Avaliação Sistemática)/7.1.2.2. inspect_ai, PromptFoo, LLM-as-a-Judge e Golden Dataset|7.1.2.2. inspect_ai, PromptFoo, LLM-as-a-Judge e Golden Dataset]]
- **7.1.3. LLM Routing e Cascading**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/7. LLMOps, Observabilidade e Governança/7.1 Operacionalizando IA no Back-end/7.1.3. LLM Routing e Cascading/7.1.3.1. LLM Routing e Cascading de Modelos|7.1.3.1. LLM Routing e Cascading de Modelos]]
- **7.1.4. AI Guardrails**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/7. LLMOps, Observabilidade e Governança/7.1 Operacionalizando IA no Back-end/7.1.4. AI Guardrails/7.1.4.1. AI Guardrails — NeMo Guardrails, Llama Guard e Prompt Injection|7.1.4.1. AI Guardrails — NeMo Guardrails, Llama Guard e Prompt Injection]]

### 7.2 Infraestrutura de Inferência
- **7.2.1. Serving e Otimização**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/7. LLMOps, Observabilidade e Governança/7.2 Infraestrutura de Inferência/7.2.1. Serving e Otimização/7.2.1.1. Serving e Otimização — vLLM, Speculative Decoding, Quantização e Deploy Local|7.2.1.1. Serving e Otimização — vLLM, Speculative Decoding, Quantização e Deploy Local]]

---

## 8 Domínio: Projeto Prático "Nexus Architect"

### 8.1 Especificação do Sistema Multi-Agente
- **8.1.1. O Desafio**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/8. Projeto Prático Nexus Architect/8.1 Especificação do Sistema Multi-Agente/8.1.1. O Desafio/8.1.1.1. A Especificação do Sistema — API de Orquestração do Requisito ao MVP|8.1.1.1. A Especificação do Sistema — API de Orquestração do Requisito ao MVP]]
- **8.1.2. A Topologia do CrewAI/LangGraph**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/8. Projeto Prático Nexus Architect/8.1 Especificação do Sistema Multi-Agente/8.1.2. A Topologia do CrewAI-LangGraph/8.1.2.1. Agente Analista (Supervisor) e Agente de Infra (DB Specialist)|8.1.2.1. Agente Analista (Supervisor) e Agente de Infra (DB Specialist)]]
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/8. Projeto Prático Nexus Architect/8.1 Especificação do Sistema Multi-Agente/8.1.2. A Topologia do CrewAI-LangGraph/8.1.2.2. Agentes de Backend e Frontend e o Eval Harness do Projeto|8.1.2.2. Agentes de Backend e Frontend e o Eval Harness do Projeto]]

---

## 9 Domínio: Fronteiras e Tópicos Emergentes

### 9.1 Multimodalidade e Novos Paradigmas
- **9.1.1. RAG Multimodal**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/9. Fronteiras e Tópicos Emergentes/9.1 Multimodalidade e Novos Paradigmas/9.1.1. RAG Multimodal/9.1.1.1. RAG Multimodal — Imagens, Tabelas, Áudio e Vídeo sem OCR|9.1.1.1. RAG Multimodal — Imagens, Tabelas, Áudio e Vídeo sem OCR]]
- **9.1.2. Mixture of Experts (MoE)**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/9. Fronteiras e Tópicos Emergentes/9.1 Multimodalidade e Novos Paradigmas/9.1.2. Mixture of Experts (MoE)/9.1.2.1. Mixture of Experts — Roteamento de Especialistas e Custo de Inferência|9.1.2.1. Mixture of Experts — Roteamento de Especialistas e Custo de Inferência]]
- **9.1.3. Small Language Models (SLMs) para Edge**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/9. Fronteiras e Tópicos Emergentes/9.1 Multimodalidade e Novos Paradigmas/9.1.3. Small Language Models (SLMs) para Edge/9.1.3.1. Small Language Models — Phi, Gemma e Llama como Alternativa às APIs|9.1.3.1. Small Language Models — Phi, Gemma e Llama como Alternativa às APIs]]
- **9.1.4. Model Distillation**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/9. Fronteiras e Tópicos Emergentes/9.1 Multimodalidade e Novos Paradigmas/9.1.4. Model Distillation/9.1.4.1. Model Distillation — Como um Student Aprende a Imitar um Teacher|9.1.4.1. Model Distillation — Como um Student Aprende a Imitar um Teacher]]

### 9.2 Segurança e Alinhamento
- **9.2.1. Prompt Injection**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/9. Fronteiras e Tópicos Emergentes/9.2 Segurança e Alinhamento/9.2.1. Prompt Injection/9.2.1.1. Prompt Injection — Como Conteúdo Externo Injeta Instruções e a Defesa por Separação de Canais|9.2.1.1. Prompt Injection — Como Conteúdo Externo Injeta Instruções e a Defesa por Separação de Canais]]
- **9.2.2. Constitutional AI**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/9. Fronteiras e Tópicos Emergentes/9.2 Segurança e Alinhamento/9.2.2. Constitutional AI/9.2.2.1. Constitutional AI — Auto-revisão por Princípios e RLAIF|9.2.2.1. Constitutional AI — Auto-revisão por Princípios e RLAIF]]
- **9.2.3. Red Teaming Automatizado**
  - [x] [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/9. Fronteiras e Tópicos Emergentes/9.2 Segurança e Alinhamento/9.2.3. Red Teaming Automatizado/9.2.3.1. Red Teaming Automatizado — garak e Ferramentas de Teste de Jailbreak|9.2.3.1. Red Teaming Automatizado — garak e Ferramentas de Teste de Jailbreak]]

---

> **Glossário Pai:** [[0 Glossário/Glossário|Base de Conhecimento Tecnológico]]
>
> **Links Relacionados:**
> [[14. Inteligência Artificial e Machine Learning/Como LLMs Funcionam/0 Como LLMs Funcionam (Glossário )|Como LLMs Funcionam — o lado teórico]]
