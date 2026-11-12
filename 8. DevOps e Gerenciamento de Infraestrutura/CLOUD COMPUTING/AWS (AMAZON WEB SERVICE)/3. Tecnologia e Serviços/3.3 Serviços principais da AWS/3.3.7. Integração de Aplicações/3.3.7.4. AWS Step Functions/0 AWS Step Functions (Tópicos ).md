# 📚 Guia de Estudos: AWS Step Functions
#tag #aws #cloud #integracao #stepfunctions #orquestracao #workflows #serverless

> [!info] Visão Geral
> O AWS Step Functions é o serviço de orquestração de fluxos de trabalho serverless da AWS: descreve o fluxo como uma máquina de estados (Amazon States Language), com decisões, paralelismo, esperas, retentativas e compensações, chamando mais de 200 serviços AWS sem código de cola. Este guia cobre os fundamentos (Standard vs Express e comparação com Lambda encadeada, SQS e Airflow), a ASL (estados, entrada e saída, variáveis, JSONata), as integrações de serviço (sync, callback, SDK), o tratamento de erros (Retry, Catch, sagas, redrive), os padrões e escala (Distributed Map, versões, testes) e a segurança e operação.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Orquestração de fluxos serverless**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.4. AWS Step Functions/1. Fundamentos/1.1 Visão geral/1.1.1. Orquestração de fluxos serverless/1.1.1.1. O que é AWS Step Functions — máquinas de estado, Amazon States Language, Standard vs Express, integrações e quando usar em vez de Lambda encadeada, SQS ou Airflow|1.1.1.1. O que é AWS Step Functions — máquinas de estado, Amazon States Language, Standard vs Express, integrações e quando usar em vez de Lambda encadeada, SQS ou Airflow]]

---

## 2 Domínio: Linguagem ASL e estados

### 2.1 Tipos de estado e fluxo de dados
- **2.1.1. Estados, entrada e saída, variáveis e JSONata**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.4. AWS Step Functions/2. Linguagem ASL e estados/2.1 Tipos de estado e fluxo de dados/2.1.1. Estados, entrada e saída, variáveis e JSONata/2.1.1.1. Amazon States Language em profundidade — tipos de estado, processamento de entrada e saída, variáveis, funções intrínsecas e JSONata|2.1.1.1. Amazon States Language em profundidade — tipos de estado, processamento de entrada e saída, variáveis, funções intrínsecas e JSONata]]

---

## 3 Domínio: Integrações de serviço

### 3.1 Padrões de integração e callbacks
- **3.1.1. Integrações otimizadas, SDK, sync e callback**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.4. AWS Step Functions/3. Integrações de serviço/3.1 Padrões de integração e callbacks/3.1.1. Integrações otimizadas, SDK, sync e callback/3.1.1.1. Integrações de serviço no Step Functions — padrões request response, sync e waitForTaskToken, integrações otimizadas e do SDK, HTTP Task, activities e aprovação humana|3.1.1.1. Integrações de serviço no Step Functions — padrões request response, sync e waitForTaskToken, integrações otimizadas e do SDK, HTTP Task, activities e aprovação humana]]

---

## 4 Domínio: Erros e confiabilidade

### 4.1 Retry, Catch, sagas e redrive
- **4.1.1. Tratamento de erros, compensação e semântica de execução**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.4. AWS Step Functions/4. Erros e confiabilidade/4.1 Retry, Catch, sagas e redrive/4.1.1. Tratamento de erros, compensação e semântica de execução/4.1.1.1. Erros e confiabilidade no Step Functions — Retry e Catch, nomes de erro, timeouts, heartbeats, sagas com compensação, redrive de execuções e semântica Standard vs Express|4.1.1.1. Erros e confiabilidade no Step Functions — Retry e Catch, nomes de erro, timeouts, heartbeats, sagas com compensação, redrive de execuções e semântica Standard vs Express]]

---

## 5 Domínio: Padrões e escala

### 5.1 Map distribuído, aninhamento e implantação
- **5.1.1. Padrões de workflow, escala massiva, versões e testes**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.4. AWS Step Functions/5. Padrões e escala/5.1 Map distribuído, aninhamento e implantação/5.1.1. Padrões de workflow, escala massiva, versões e testes/5.1.1.1. Padrões de workflow e escala no Step Functions — Distributed Map, paralelismo, aninhamento, Express síncrono, versões e aliases, implantação gradual, testes e ferramentas de autoria|5.1.1.1. Padrões de workflow e escala no Step Functions — Distributed Map, paralelismo, aninhamento, Express síncrono, versões e aliases, implantação gradual, testes e ferramentas de autoria]]

---

## 6 Domínio: Segurança e operação

### 6.1 Acesso, observabilidade, quotas e custo
- **6.1.1. IAM, logs, métricas, custos e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.4. AWS Step Functions/6. Segurança e operação/6.1 Acesso, observabilidade, quotas e custo/6.1.1. IAM, logs, métricas, custos e troubleshooting/6.1.1.1. Segurança e operação do Step Functions — IAM e roles de execução, criptografia, logs e X-Ray, métricas e alarmes, quotas, custos, IaC e checklist de produção|6.1.1.1. Segurança e operação do Step Functions — IAM e roles de execução, criptografia, logs e X-Ray, métricas e alarmes, quotas, custos, IaC e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.3. Amazon EventBridge/0 Amazon EventBridge (Tópicos )|Amazon EventBridge]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.1. Amazon SQS/0 Amazon SQS (Tópicos )|Amazon SQS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.2. Amazon SNS/0 Amazon SNS (Tópicos )|Amazon SNS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.4. AWS Glue/0 AWS Glue (Tópicos )|AWS Glue]]
