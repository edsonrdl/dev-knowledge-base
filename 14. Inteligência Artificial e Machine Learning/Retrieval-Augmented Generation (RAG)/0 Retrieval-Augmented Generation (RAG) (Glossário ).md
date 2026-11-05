# 📚 Guia de Estudos: Retrieval-Augmented Generation (RAG)
#ia #rag #llm #arquitetura

> [!info] Visão Geral
> RAG é o padrão que combina **busca de informação externa** com **geração de texto por LLM**: em vez de confiar só no que o modelo memorizou no treino, o sistema recupera trechos relevantes de uma base de conhecimento e os injeta no prompt. Este guia trata o assunto de forma **conceitual e de ponta a ponta** — fundamentos, pipeline, arquiteturas, evolução, avaliação, produção e decisões — e usa links para o guia [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/0 Engenharia de IA Aplicada (AI Engineering) ( Glossário )|Engenharia de IA Aplicada (AI Engineering)]] quando a técnica já é coberta em detalhe lá (chunking, embeddings, ANN, hybrid search, reranking, GraphRAG, parsers, Ragas/DeepEval).

---

## 1 Domínio: Fundamentos do RAG

### 1.1 O Problema e a Ideia
- **1.1.1. Por que o RAG existe**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/1. Fundamentos do RAG/1.1 O Problema e a Ideia/1.1.1. Por que o RAG existe/1.1.1.1. Limitações dos LLMs — corte de conhecimento, alucinação, dados privados e falta de fontes|1.1.1.1. Limitações dos LLMs — corte de conhecimento, alucinação, dados privados e falta de fontes]]
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/1. Fundamentos do RAG/1.1 O Problema e a Ideia/1.1.1. Por que o RAG existe/1.1.1.2. O que é RAG — a ideia central, o artigo original (Lewis et al., 2020) e a analogia da prova com consulta|1.1.1.2. O que é RAG — a ideia central, o artigo original (Lewis et al., 2020) e a analogia da prova com consulta]]

### 1.2 Anatomia de um Sistema RAG
- **1.2.1. O pipeline de ponta a ponta**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/1. Fundamentos do RAG/1.2 Anatomia de um Sistema RAG/1.2.1. O pipeline de ponta a ponta/1.2.1.1. Fase offline (indexação) vs fase online (consulta) — o mapa completo do pipeline|1.2.1.1. Fase offline (indexação) vs fase online (consulta) — o mapa completo do pipeline]]
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/1. Fundamentos do RAG/1.2 Anatomia de um Sistema RAG/1.2.1. O pipeline de ponta a ponta/1.2.1.2. Prompt aumentado e grounding — como o contexto recuperado vira resposta fundamentada|1.2.1.2. Prompt aumentado e grounding — como o contexto recuperado vira resposta fundamentada]]
- **1.2.2. RAG frente às alternativas**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/1. Fundamentos do RAG/1.2 Anatomia de um Sistema RAG/1.2.2. RAG frente às alternativas/1.2.2.1. RAG vs prompt longo vs fine-tuning vs busca clássica — tabela de decisão|1.2.2.1. RAG vs prompt longo vs fine-tuning vs busca clássica — tabela de decisão]]

---

## 2 Domínio: Indexação — Preparando o Conhecimento

### 2.1 Fontes e Ingestão
- **2.1.1. Qualidade e atualização dos dados**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/2. Indexação — Preparando o Conhecimento/2.1 Fontes e Ingestão/2.1.1. Qualidade e atualização dos dados/2.1.1.1. Tipos de fonte e qualidade de dados — lixo entra, lixo sai no RAG|2.1.1.1. Tipos de fonte e qualidade de dados — lixo entra, lixo sai no RAG]]
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/2. Indexação — Preparando o Conhecimento/2.1 Fontes e Ingestão/2.1.1. Qualidade e atualização dos dados/2.1.1.2. Sincronização, deduplicação, versionamento e deleção de documentos|2.1.1.2. Sincronização, deduplicação, versionamento e deleção de documentos]]
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/2. Indexação — Preparando o Conhecimento/2.1 Fontes e Ingestão/2.1.1. Qualidade e atualização dos dados/2.1.1.3. Metadados e controle de acesso (ACL) já na indexação|2.1.1.3. Metadados e controle de acesso (ACL) já na indexação]]

### 2.2 Do Texto ao Índice
- **2.2.1. Chunking como decisão de projeto**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/2. Indexação — Preparando o Conhecimento/2.2 Do Texto ao Índice/2.2.1. Chunking como decisão de projeto/2.2.1.1. Como o tamanho e o corte dos chunks afetam o retrieval (visão conceitual)|2.2.1.1. Como o tamanho e o corte dos chunks afetam o retrieval (visão conceitual)]]
- **2.2.2. Embeddings e similaridade**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/2. Indexação — Preparando o Conhecimento/2.2 Do Texto ao Índice/2.2.2. Embeddings e similaridade/2.2.2.1. Do texto ao vetor — intuição de embeddings, similaridade de cosseno e escolha do modelo|2.2.2.1. Do texto ao vetor — intuição de embeddings, similaridade de cosseno e escolha do modelo]]
- **2.2.3. Armazenamento e índices**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/2. Indexação — Preparando o Conhecimento/2.2 Do Texto ao Índice/2.2.3. Armazenamento e índices/2.2.3.1. Bancos vetoriais e índices aproximados — como decidir entre pgvector, dedicado e busca híbrida nativa|2.2.3.1. Bancos vetoriais e índices aproximados — como decidir entre pgvector, dedicado e busca híbrida nativa]]

---

## 3 Domínio: Recuperação (Retrieval)

### 3.1 Estratégias de Busca
- **3.1.1. Lexical, semântica e híbrida**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/3. Recuperação (Retrieval)/3.1 Estratégias de Busca/3.1.1. Lexical, semântica e híbrida/3.1.1.1. Busca lexical vs semântica vs híbrida — onde cada uma acerta e onde falha|3.1.1.1. Busca lexical vs semântica vs híbrida — onde cada uma acerta e onde falha]]
- **3.1.2. Parâmetros de recuperação**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/3. Recuperação (Retrieval)/3.1 Estratégias de Busca/3.1.2. Parâmetros de recuperação/3.1.2.1. Top-k, limiar de score, filtros de metadados e diversidade (MMR)|3.1.2.1. Top-k, limiar de score, filtros de metadados e diversidade (MMR)]]

### 3.2 Refinamento da Recuperação
- **3.2.1. Antes da busca**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/3. Recuperação (Retrieval)/3.2 Refinamento da Recuperação/3.2.1. Antes da busca/3.2.1.1. Reescrita, expansão e decomposição de consultas — mapa de técnicas|3.2.1.1. Reescrita, expansão e decomposição de consultas — mapa de técnicas]]
- **3.2.2. Depois da busca**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/3. Recuperação (Retrieval)/3.2 Refinamento da Recuperação/3.2.2. Depois da busca/3.2.2.1. Reranking, compressão de contexto e seleção final dos trechos|3.2.2.1. Reranking, compressão de contexto e seleção final dos trechos]]

---

## 4 Domínio: Geração (Generation)

### 4.1 Montagem do Contexto
- **4.1.1. Prompt e orçamento de contexto**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/4. Geração (Generation)/4.1 Montagem do Contexto/4.1.1. Prompt e orçamento de contexto/4.1.1.1. Template de prompt RAG e instruções de grounding|4.1.1.1. Template de prompt RAG e instruções de grounding]]
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/4. Geração (Generation)/4.1 Montagem do Contexto/4.1.1. Prompt e orçamento de contexto/4.1.1.2. Orçamento de contexto e ordenação dos trechos — o problema do lost in the middle|4.1.1.2. Orçamento de contexto e ordenação dos trechos — o problema do lost in the middle]]

### 4.2 Qualidade da Resposta
- **4.2.1. Confiabilidade**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/4. Geração (Generation)/4.2 Qualidade da Resposta/4.2.1. Confiabilidade/4.2.1.1. Citações e atribuição de fontes|4.2.1.1. Citações e atribuição de fontes]]
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/4. Geração (Generation)/4.2 Qualidade da Resposta/4.2.1. Confiabilidade/4.2.1.2. Resposta não sei, conflito entre fontes e informação desatualizada|4.2.1.2. Resposta não sei, conflito entre fontes e informação desatualizada]]

---

## 5 Domínio: Arquiteturas e Evolução do RAG

### 5.1 Da Versão Ingênua à Modular
- **5.1.1. Gerações de arquitetura**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/5. Arquiteturas e Evolução do RAG/5.1 Da Versão Ingênua à Modular/5.1.1. Gerações de arquitetura/5.1.1.1. Naive RAG e suas falhas típicas|5.1.1.1. Naive RAG e suas falhas típicas]]
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/5. Arquiteturas e Evolução do RAG/5.1 Da Versão Ingênua à Modular/5.1.1. Gerações de arquitetura/5.1.1.2. Advanced RAG — otimizações antes e depois do retrieval|5.1.1.2. Advanced RAG — otimizações antes e depois do retrieval]]
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/5. Arquiteturas e Evolução do RAG/5.1 Da Versão Ingênua à Modular/5.1.1. Gerações de arquitetura/5.1.1.3. Modular RAG — roteamento, módulos e padrões compostos|5.1.1.3. Modular RAG — roteamento, módulos e padrões compostos]]

### 5.2 Variações e Padrões Modernos
- **5.2.1. RAG com autocrítica e decisão**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/5. Arquiteturas e Evolução do RAG/5.2 Variações e Padrões Modernos/5.2.1. RAG com autocrítica e decisão/5.2.1.1. Self-RAG, CRAG e Adaptive RAG — recuperar só quando e como for preciso|5.2.1.1. Self-RAG, CRAG e Adaptive RAG — recuperar só quando e como for preciso]]
- **5.2.2. RAG sobre estruturas e agentes**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/5. Arquiteturas e Evolução do RAG/5.2 Variações e Padrões Modernos/5.2.2. RAG sobre estruturas e agentes/5.2.2.1. GraphRAG e RAG sobre dados estruturados — visão conceitual e quando compensa|5.2.2.1. GraphRAG e RAG sobre dados estruturados — visão conceitual e quando compensa]]
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/5. Arquiteturas e Evolução do RAG/5.2 Variações e Padrões Modernos/5.2.2. RAG sobre estruturas e agentes/5.2.2.2. Agentic RAG — o agente como orquestrador da recuperação|5.2.2.2. Agentic RAG — o agente como orquestrador da recuperação]]
- **5.2.3. RAG e contexto longo**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/5. Arquiteturas e Evolução do RAG/5.2 Variações e Padrões Modernos/5.2.3. RAG e contexto longo/5.2.3.1. Long context, Cache-Augmented Generation (CAG) e RAG multimodal — onde cada um se encaixa|5.2.3.1. Long context, Cache-Augmented Generation (CAG) e RAG multimodal — onde cada um se encaixa]]

---

## 6 Domínio: Avaliação e Diagnóstico

### 6.1 Medindo o Sistema
- **6.1.1. Retrieval e geração separadamente**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/6. Avaliação e Diagnóstico/6.1 Medindo o Sistema/6.1.1. Retrieval e geração separadamente/6.1.1.1. Métricas de retrieval — recall@k, precision@k, MRR e nDCG|6.1.1.1. Métricas de retrieval — recall@k, precision@k, MRR e nDCG]]
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/6. Avaliação e Diagnóstico/6.1 Medindo o Sistema/6.1.1. Retrieval e geração separadamente/6.1.1.2. Métricas de geração — faithfulness, relevância e o RAG Triad|6.1.1.2. Métricas de geração — faithfulness, relevância e o RAG Triad]]
- **6.1.2. Dataset de avaliação**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/6. Avaliação e Diagnóstico/6.1 Medindo o Sistema/6.1.2. Dataset de avaliação/6.1.2.1. Construindo um conjunto de perguntas de teste para RAG (golden set e dados sintéticos)|6.1.2.1. Construindo um conjunto de perguntas de teste para RAG (golden set e dados sintéticos)]]

### 6.2 Depuração
- **6.2.1. Onde o RAG quebra**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/6. Avaliação e Diagnóstico/6.2 Depuração/6.2.1. Onde o RAG quebra/6.2.1.1. Taxonomia de falhas e checklist de diagnóstico (indexação, retrieval ou geração)|6.2.1.1. Taxonomia de falhas e checklist de diagnóstico (indexação, retrieval ou geração)]]

---

## 7 Domínio: RAG em Produção

### 7.1 Desempenho, Custo e Segurança
- **7.1.1. Latência e custo**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/7. RAG em Produção/7.1 Desempenho, Custo e Segurança/7.1.1. Latência e custo/7.1.1.1. Onde o tempo e o dinheiro vão — cache semântico, prompt caching, streaming e modelos menores|7.1.1.1. Onde o tempo e o dinheiro vão — cache semântico, prompt caching, streaming e modelos menores]]
- **7.1.2. Segurança e privacidade**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/7. RAG em Produção/7.1 Desempenho, Custo e Segurança/7.1.2. Segurança e privacidade/7.1.2.1. Prompt injection indireta, vazamento entre usuários e proteção de dados pessoais (PII)|7.1.2.1. Prompt injection indireta, vazamento entre usuários e proteção de dados pessoais (PII)]]

### 7.2 Operação Contínua
- **7.2.1. Observabilidade e melhoria**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/7. RAG em Produção/7.2 Operação Contínua/7.2.1. Observabilidade e melhoria/7.2.1.1. Rastreamento, feedback do usuário e ciclo de melhoria contínua|7.2.1.1. Rastreamento, feedback do usuário e ciclo de melhoria contínua]]
- **7.2.2. Escala e multi-tenancy**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/7. RAG em Produção/7.2 Operação Contínua/7.2.2. Escala e multi-tenancy/7.2.2.1. Isolamento por tenant, crescimento do índice e estratégias de reindexação|7.2.2.1. Isolamento por tenant, crescimento do índice e estratégias de reindexação]]

---

## 8 Domínio: Síntese e Projeto

### 8.1 Juntando Tudo
- **8.1.1. Estudo de caso**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/8. Síntese e Projeto/8.1 Juntando Tudo/8.1.1. Estudo de caso/8.1.1.1. Projetando um RAG de ponta a ponta — assistente de suporte sobre documentação interna|8.1.1.1. Projetando um RAG de ponta a ponta — assistente de suporte sobre documentação interna]]
- **8.1.2. Guia de decisão**
  - [x] [[14. Inteligência Artificial e Machine Learning/Retrieval-Augmented Generation (RAG)/8. Síntese e Projeto/8.1 Juntando Tudo/8.1.2. Guia de decisão/8.1.2.1. Checklist de decisão — que arquitetura de RAG escolher para cada cenário|8.1.2.1. Checklist de decisão — que arquitetura de RAG escolher para cada cenário]]

---

> **Links Relacionados:**
> [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/0 Engenharia de IA Aplicada (AI Engineering) ( Glossário )|Engenharia de IA Aplicada (AI Engineering)]]

> **Glossário Pai:** [[0 Glossário/Glossário|Base de Conhecimento Tecnológico]]
