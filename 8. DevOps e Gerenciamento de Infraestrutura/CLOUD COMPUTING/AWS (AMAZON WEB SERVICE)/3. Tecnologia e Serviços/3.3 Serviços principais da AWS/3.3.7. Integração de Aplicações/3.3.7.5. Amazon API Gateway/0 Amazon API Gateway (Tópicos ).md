# 📚 Guia de Estudos: Amazon API Gateway
#tag #aws #cloud #integracao #apigateway #api #serverless #rest #http #websocket

> [!info] Visão Geral
> O Amazon API Gateway é o serviço gerenciado para criar, publicar, proteger, monitorar e escalar APIs: REST APIs (mais recursos), HTTP APIs (mais baratas e simples) e WebSocket APIs (tempo real). Cuida de autenticação e autorização, throttling, cache, validação, estágios e domínios, e integra-se a Lambda, HTTP/ALB/NLB e serviços AWS. Este guia cobre fundamentos, tipos de API e integrações, segurança e autorização, stages e implantação, desempenho e resiliência, e operação.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. APIs gerenciadas na AWS**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.5. Amazon API Gateway/1. Fundamentos/1.1 Visão geral/1.1.1. APIs gerenciadas na AWS/1.1.1.1. O que é Amazon API Gateway — REST, HTTP e WebSocket APIs, tipos de endpoint, integrações e quando usar em vez de ALB, Function URLs ou AppSync|1.1.1.1. O que é Amazon API Gateway — REST, HTTP e WebSocket APIs, tipos de endpoint, integrações e quando usar em vez de ALB, Function URLs ou AppSync]]

---

## 2 Domínio: Tipos de API e integrações

### 2.1 REST e HTTP APIs
- **2.1.1. Recursos, métodos e integrações**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.5. Amazon API Gateway/2. Tipos de API e integrações/2.1 REST e HTTP APIs/2.1.1. Recursos, métodos e integrações/2.1.1.1. REST APIs e HTTP APIs em profundidade — recursos e rotas, integrações proxy e não proxy, mapping templates, validação, VPC link, CORS e comparativo REST vs HTTP|2.1.1.1. REST APIs e HTTP APIs em profundidade — recursos e rotas, integrações proxy e não proxy, mapping templates, validação, VPC link, CORS e comparativo REST vs HTTP]]

---

## 3 Domínio: Segurança e autorização

### 3.1 Autenticação e proteção
- **3.1.1. IAM, Cognito, Lambda authorizers e JWT**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.5. Amazon API Gateway/3. Segurança e autorização/3.1 Autenticação e proteção/3.1.1. IAM, Cognito, Lambda authorizers e JWT/3.1.1.1. Autorização no API Gateway — IAM SigV4, Cognito, JWT authorizer, Lambda authorizer, API keys e usage plans, mTLS, resource policies, WAF e endpoints privados|3.1.1.1. Autorização no API Gateway — IAM SigV4, Cognito, JWT authorizer, Lambda authorizer, API keys e usage plans, mTLS, resource policies, WAF e endpoints privados]]

---

## 4 Domínio: Stages, deploy e versões

### 4.1 Estágios e implantação
- **4.1.1. Stages, variáveis, canary e domínios**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.5. Amazon API Gateway/4. Stages, deploy e versões/4.1 Estágios e implantação/4.1.1. Stages, variáveis, canary e domínios/4.1.1.1. Stages e implantação no API Gateway — deployments, variáveis de stage, canary release, domínios custom com ACM, OpenAPI, SAM e CDK, CORS e versionamento de APIs|4.1.1.1. Stages e implantação no API Gateway — deployments, variáveis de stage, canary release, domínios custom com ACM, OpenAPI, SAM e CDK, CORS e versionamento de APIs]]

---

## 5 Domínio: Desempenho e resiliência

### 5.1 Throttling, cache e limites
- **5.1.1. Throttling, cache, timeouts e WebSocket**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.5. Amazon API Gateway/5. Desempenho e resiliência/5.1 Throttling, cache e limites/5.1.1. Throttling, cache, timeouts e WebSocket/5.1.1.1. Desempenho e resiliência no API Gateway — throttling e quotas, cache, timeouts e padrões assíncronos, WebSocket APIs e como lidar com picos e falhas do backend|5.1.1.1. Desempenho e resiliência no API Gateway — throttling e quotas, cache, timeouts e padrões assíncronos, WebSocket APIs e como lidar com picos e falhas do backend]]

---

## 6 Domínio: Segurança e operação

### 6.1 Observabilidade, custo e troubleshooting
- **6.1.1. Logs, métricas, X-Ray, custos e erros comuns**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.5. Amazon API Gateway/6. Segurança e operação/6.1 Observabilidade, custo e troubleshooting/6.1.1. Logs, métricas, X-Ray, custos e erros comuns/6.1.1.1. Operação do API Gateway — logs de acesso e execução, métricas e alarmes, X-Ray, custos, quotas, erros 4xx e 5xx, IaC e checklist de produção|6.1.1.1. Operação do API Gateway — logs de acesso e execução, métricas e alarmes, X-Ray, custos, quotas, erros 4xx e 5xx, IaC e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.2. AWS Lambda/0 AWS Lambda (Tópicos )|AWS Lambda]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.6. Amazon CloudFront/0 Amazon CloudFront (Tópicos )|Amazon CloudFront]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.1. Amazon SQS/0 Amazon SQS (Tópicos )|Amazon SQS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.4. AWS Step Functions/0 AWS Step Functions (Tópicos )|AWS Step Functions]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/2. Segurança e Conformidade/2.3 Capacidades de gerenciamento de acesso da AWS/2.3.2. Serviços de segurança/2.3.2.3. AWS WAF|AWS WAF]]
