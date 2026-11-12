# 📚 Guia de Estudos: AWS X-Ray
#tag #aws #cloud #observabilidade #xray #tracing #opentelemetry

> [!info] Visão Geral
> O AWS X-Ray é o serviço de rastreamento distribuído da AWS: reúne os segmentos gerados por cada serviço em um único trace por requisição, desenha o service map e permite filtrar, agrupar e analisar latência e erros. Este guia cobre fundamentos (trace, segment, subsegment, annotations), instrumentação (SDK, daemon, ADOT/OpenTelemetry), análise (filter expressions, grupos, Analytics), sampling e integrações, segurança (IAM, KMS, VPC endpoints, dados sensíveis) e operação (Insights, alarmes, custos, migração para OpenTelemetry).

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Rastreamento distribuído**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.8. AWS X-Ray/1. Fundamentos/1.1 Visão geral/1.1.1. Rastreamento distribuído/1.1.1.1. O que é AWS X-Ray — traces, segments, subsegments, service map, anotações e metadados e quando usar X-Ray em vez de logs e métricas|1.1.1.1. O que é AWS X-Ray — traces, segments, subsegments, service map, anotações e metadados e quando usar X-Ray em vez de logs e métricas]]

---

## 2 Domínio: Instrumentação

### 2.1 SDKs, daemon e OpenTelemetry
- **2.1.1. Coleta de traces**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.8. AWS X-Ray/2. Instrumentação/2.1 SDKs, daemon e OpenTelemetry/2.1.1. Coleta de traces/2.1.1.1. Instrumentação com X-Ray — X-Ray SDK, daemon, ADOT e OpenTelemetry, Lambda, ECS, EKS e EC2, propagação do trace header e anotações|2.1.1.1. Instrumentação com X-Ray — X-Ray SDK, daemon, ADOT e OpenTelemetry, Lambda, ECS, EKS e EC2, propagação do trace header e anotações]]

---

## 3 Domínio: Análise de traces

### 3.1 Service map e consultas
- **3.1.1. Visualização e filtros**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.8. AWS X-Ray/3. Análise de traces/3.1 Service map e consultas/3.1.1. Visualização e filtros/3.1.1.1. Análise de traces no X-Ray — service map, filtros e expressões, grupos, anotações, análise de latência e erros e Trace Map|3.1.1.1. Análise de traces no X-Ray — service map, filtros e expressões, grupos, anotações, análise de latência e erros e Trace Map]]

---

## 4 Domínio: Sampling e integrações

### 4.1 Regras e serviços AWS
- **4.1.1. Amostragem e integrações**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.8. AWS X-Ray/4. Sampling e integrações/4.1 Regras e serviços AWS/4.1.1. Amostragem e integrações/4.1.1.1. Sampling e integrações do X-Ray — regras de amostragem, API Gateway, Lambda, SNS e SQS, ALB, Step Functions e CloudWatch|4.1.1.1. Sampling e integrações do X-Ray — regras de amostragem, API Gateway, Lambda, SNS e SQS, ALB, Step Functions e CloudWatch]]

---

## 5 Domínio: Segurança e governança

### 5.1 IAM, criptografia e dados
- **5.1.1. Controle de acesso e dados sensíveis**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.8. AWS X-Ray/5. Segurança e governança/5.1 IAM, criptografia e dados/5.1.1. Controle de acesso e dados sensíveis/5.1.1.1. Segurança do X-Ray — IAM para aplicação e consulta, criptografia com KMS, dados sensíveis em anotações, VPC endpoints e governança de acesso|5.1.1.1. Segurança do X-Ray — IAM para aplicação e consulta, criptografia com KMS, dados sensíveis em anotações, VPC endpoints e governança de acesso]]

---

## 6 Domínio: Operação e custos

### 6.1 Insights, alarmes e custos
- **6.1.1. Observabilidade e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.8. AWS X-Ray/6. Operação e custos/6.1 Insights, alarmes e custos/6.1.1. Observabilidade e troubleshooting/6.1.1.1. Operação do X-Ray — Insights, alarmes por grupo, quotas, custos de traces gravados e recuperados, troubleshooting e migração para OpenTelemetry|6.1.1.1. Operação do X-Ray — Insights, alarmes por grupo, quotas, custos de traces gravados e recuperados, troubleshooting e migração para OpenTelemetry]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.1. AWS CloudWatch/0 AWS CloudWatch (Tópicos )|AWS CloudWatch]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.2. AWS Lambda/0 AWS Lambda (Tópicos )|AWS Lambda]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.5. Amazon API Gateway/0 Amazon API Gateway (Tópicos )|Amazon API Gateway]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.3. Amazon ECS/0 Amazon ECS (Tópicos )|Amazon ECS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.3. Amazon EventBridge/0 Amazon EventBridge (Tópicos )|Amazon EventBridge]]
