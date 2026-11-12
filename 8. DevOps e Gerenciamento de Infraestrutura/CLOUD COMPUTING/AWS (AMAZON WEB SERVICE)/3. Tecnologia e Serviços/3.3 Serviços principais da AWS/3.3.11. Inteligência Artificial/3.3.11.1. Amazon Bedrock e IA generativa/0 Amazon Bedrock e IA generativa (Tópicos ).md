# 📚 Guia de Estudos: Amazon Bedrock e IA generativa
#tag #aws #cloud #ia #bedrock #llm #rag #agentes #guardrails #agentcore

> [!info] Visão Geral
> O Amazon Bedrock oferece modelos fundacionais de vários provedores por uma API gerenciada, com recursos para RAG (Knowledge Bases), agentes (Agents e AgentCore), guardrails, avaliação e personalização. Este guia cobre fundamentos (tokens, contexto, modos de consumo, Bedrock x SageMaker x serviços de IA prontos), uso via API (Converse, InvokeModel, streaming, tool use, embeddings), Knowledge Bases e agentes, arquiteturas de produção, segurança e governança (Guardrails, prompt injection, IAM, privacidade) e operação (exceções, cotas, métricas, avaliação, custos).

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. IA generativa gerenciada**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.11. Inteligência Artificial/3.3.11.1. Amazon Bedrock e IA generativa/1. Fundamentos/1.1 Visão geral/1.1.1. IA generativa gerenciada/1.1.1.1. O que é o Amazon Bedrock — modelos fundacionais via API, tokens e janela de contexto, on-demand versus provisioned, serviços de IA gerenciados e quando usar Bedrock, SageMaker ou serviços prontos|1.1.1.1. O que é o Amazon Bedrock — modelos fundacionais via API, tokens e janela de contexto, on-demand versus provisioned, serviços de IA gerenciados e quando usar Bedrock, SageMaker ou serviços prontos]]

---

## 2 Domínio: Uso via API

### 2.1 Converse, InvokeModel, streaming e tool use
- **2.1.1. Chamadas ao modelo**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.11. Inteligência Artificial/3.3.11.1. Amazon Bedrock e IA generativa/2. Uso via API/2.1 Converse, InvokeModel, streaming e tool use/2.1.1. Chamadas ao modelo/2.1.1.1. Chamando modelos pelo SDK — Converse e InvokeModel, streaming, parâmetros de inferência, tool use, saída estruturada, embeddings, multimodal e tratamento de erros|2.1.1.1. Chamando modelos pelo SDK — Converse e InvokeModel, streaming, parâmetros de inferência, tool use, saída estruturada, embeddings, multimodal e tratamento de erros]]

---

## 3 Domínio: Knowledge Bases e agentes

### 3.1 RAG, agentes e AgentCore
- **3.1.1. Aplicações com contexto e ações**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.11. Inteligência Artificial/3.3.11.1. Amazon Bedrock e IA generativa/3. Knowledge Bases e agentes/3.1 RAG, agentes e AgentCore/3.1.1. Aplicações com contexto e ações/3.1.1.1. Knowledge Bases, agentes e AgentCore — RAG gerenciado, chunking e vetores, Retrieve e RetrieveAndGenerate, Agents com action groups, AgentCore e MCP, memória e orquestração|3.1.1.1. Knowledge Bases, agentes e AgentCore — RAG gerenciado, chunking e vetores, Retrieve e RetrieveAndGenerate, Agents com action groups, AgentCore e MCP, memória e orquestração]]

---

## 4 Domínio: Arquitetura e integração

### 4.1 Lambda, API Gateway, custos e redes
- **4.1.1. Padrões de aplicação**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.11. Inteligência Artificial/3.3.11.1. Amazon Bedrock e IA generativa/4. Arquitetura e integração/4.1 Lambda, API Gateway, custos e redes/4.1.1. Padrões de aplicação/4.1.1.1. Arquiteturas com Bedrock — Lambda e API Gateway, streaming, filas e batch, Step Functions, VPC endpoints, cross-region, caching, controle de custos e padrões de produção|4.1.1.1. Arquiteturas com Bedrock — Lambda e API Gateway, streaming, filas e batch, Step Functions, VPC endpoints, cross-region, caching, controle de custos e padrões de produção]]

---

## 5 Domínio: Segurança e governança

### 5.1 Guardrails, IAM, privacidade e agentes
- **5.1.1. Controle e conformidade**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.11. Inteligência Artificial/3.3.11.1. Amazon Bedrock e IA generativa/5. Segurança e governança/5.1 Guardrails, IAM, privacidade e agentes/5.1.1. Controle e conformidade/5.1.1.1. Segurança em IA generativa — Guardrails, prompt injection, vazamento de dados, IAM de modelos e agentes, privacidade, auditoria, riscos de agentes e conformidade|5.1.1.1. Segurança em IA generativa — Guardrails, prompt injection, vazamento de dados, IAM de modelos e agentes, privacidade, auditoria, riscos de agentes e conformidade]]

---

## 6 Domínio: Operação e troubleshooting

### 6.1 Erros, métricas e avaliação
- **6.1.1. Observabilidade e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.11. Inteligência Artificial/3.3.11.1. Amazon Bedrock e IA generativa/6. Operação e troubleshooting/6.1 Erros, métricas e avaliação/6.1.1. Observabilidade e troubleshooting/6.1.1.1. Operação do Bedrock — exceções e cotas, métricas do CloudWatch, logs de invocação, avaliação de modelos e RAG, custos, troubleshooting e checklist de produção|6.1.1.1. Operação do Bedrock — exceções e cotas, métricas do CloudWatch, logs de invocação, avaliação de modelos e RAG, custos, troubleshooting e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.5. AWS SDKs, CLI e SigV4/0 AWS SDKs, CLI e SigV4 (Tópicos )|AWS SDKs, CLI e SigV4]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.5. Amazon API Gateway/0 Amazon API Gateway (Tópicos )|Amazon API Gateway]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.6. Amazon OpenSearch Service/0 Amazon OpenSearch Service (Tópicos )|Amazon OpenSearch Service]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.2. Amazon Macie/0 Amazon Macie (Tópicos )|Amazon Macie]]
