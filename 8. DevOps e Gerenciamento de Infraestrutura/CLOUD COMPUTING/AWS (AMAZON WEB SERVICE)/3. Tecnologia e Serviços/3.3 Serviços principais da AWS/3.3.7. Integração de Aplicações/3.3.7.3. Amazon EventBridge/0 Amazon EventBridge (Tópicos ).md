# 📚 Guia de Estudos: Amazon EventBridge
#tag #aws #cloud #integracao #eventbridge #eventos #serverless #eda

> [!info] Visão Geral
> O Amazon EventBridge é o barramento de eventos serverless da AWS: recebe eventos de serviços AWS, de suas aplicações e de parceiros SaaS, avalia regras com padrões de evento e entrega aos alvos certos. Também reúne Pipes (ponto a ponto com filtro e enriquecimento), Scheduler (agendamentos em escala), Archive e Replay, Schema Registry, API Destinations e Global Endpoints. Este guia cobre os fundamentos, as regras e padrões de evento, os alvos e a entrega, os recursos Pipes, Scheduler, Archive e Schema Registry, os padrões de arquitetura orientada a eventos e a segurança e operação.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Barramento de eventos serverless**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.3. Amazon EventBridge/1. Fundamentos/1.1 Visão geral/1.1.1. Barramento de eventos serverless/1.1.1.1. O que é Amazon EventBridge — arquitetura orientada a eventos, barramentos, eventos, regras, alvos, família de recursos e quando usar em vez de SNS ou SQS|1.1.1.1. O que é Amazon EventBridge — arquitetura orientada a eventos, barramentos, eventos, regras, alvos, família de recursos e quando usar em vez de SNS ou SQS]]

---

## 2 Domínio: Eventos e regras

### 2.1 Padrões de evento e regras
- **2.1.1. Event patterns, operadores e transformação**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.3. Amazon EventBridge/2. Eventos e regras/2.1 Padrões de evento e regras/2.1.1. Event patterns, operadores e transformação/2.1.1.1. Regras e padrões de evento no EventBridge — estrutura do evento, operadores de correspondência, regras por padrão e por agendamento, input transformers e testes|2.1.1.1. Regras e padrões de evento no EventBridge — estrutura do evento, operadores de correspondência, regras por padrão e por agendamento, input transformers e testes]]

---

## 3 Domínio: Alvos e entrega

### 3.1 Targets, permissões e API destinations
- **3.1.1. Entrega, retentativas, DLQ e acesso entre contas**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.3. Amazon EventBridge/3. Alvos e entrega/3.1 Targets, permissões e API destinations/3.1.1. Entrega, retentativas, DLQ e acesso entre contas/3.1.1.1. Alvos e entrega no EventBridge — tipos de alvo, permissões, retentativas e DLQ, API destinations, barramentos entre contas e regiões e políticas de recurso|3.1.1.1. Alvos e entrega no EventBridge — tipos de alvo, permissões, retentativas e DLQ, API destinations, barramentos entre contas e regiões e políticas de recurso]]

---

## 4 Domínio: Pipes, Scheduler e schemas

### 4.1 Pipes, Scheduler, Archive e Schema Registry
- **4.1.1. Integração ponto a ponto, agendamentos e contratos de evento**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.3. Amazon EventBridge/4. Pipes, Scheduler e schemas/4.1 Pipes, Scheduler, Archive e Schema Registry/4.1.1. Integração ponto a ponto, agendamentos e contratos de evento/4.1.1.1. Pipes, Scheduler, Archive e Schema Registry — fontes e enriquecimento, agendamentos em escala, replay de eventos, descoberta de schemas e geração de código|4.1.1.1. Pipes, Scheduler, Archive e Schema Registry — fontes e enriquecimento, agendamentos em escala, replay de eventos, descoberta de schemas e geração de código]]

---

## 5 Domínio: Padrões de arquitetura

### 5.1 Arquiteturas orientadas a eventos
- **5.1.1. Coreografia, SaaS, multi-conta e design de eventos**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.3. Amazon EventBridge/5. Padrões de arquitetura/5.1 Arquiteturas orientadas a eventos/5.1.1. Coreografia, SaaS, multi-conta e design de eventos/5.1.1.1. Arquiteturas orientadas a eventos com EventBridge — coreografia e orquestração, integração com SaaS, hub multi-conta, design e versionamento de eventos, consistência e idempotência|5.1.1.1. Arquiteturas orientadas a eventos com EventBridge — coreografia e orquestração, integração com SaaS, hub multi-conta, design e versionamento de eventos, consistência e idempotência]]

---

## 6 Domínio: Segurança e operação

### 6.1 Acesso, criptografia, monitoramento e custo
- **6.1.1. IAM, KMS, VPC, métricas, quotas e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.3. Amazon EventBridge/6. Segurança e operação/6.1 Acesso, criptografia, monitoramento e custo/6.1.1. IAM, KMS, VPC, métricas, quotas e troubleshooting/6.1.1.1. Segurança e operação do EventBridge — IAM, políticas de barramento, criptografia, VPC, auditoria, métricas, quotas, custos, IaC e checklist de produção|6.1.1.1. Segurança e operação do EventBridge — IAM, políticas de barramento, criptografia, VPC, auditoria, métricas, quotas, custos, IaC e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.1. Amazon SQS/0 Amazon SQS (Tópicos )|Amazon SQS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.2. Amazon SNS/0 Amazon SNS (Tópicos )|Amazon SNS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.2. AWS CloudTrail/0 AWS CloudTrail (Tópicos )|AWS CloudTrail]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.2. Amazon Kinesis/0 Amazon Kinesis (Tópicos )|Amazon Kinesis]]
