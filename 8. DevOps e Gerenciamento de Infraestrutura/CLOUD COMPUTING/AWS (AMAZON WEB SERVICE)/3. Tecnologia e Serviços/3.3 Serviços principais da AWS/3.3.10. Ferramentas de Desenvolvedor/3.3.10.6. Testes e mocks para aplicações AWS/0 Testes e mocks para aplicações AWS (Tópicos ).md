# 📚 Guia de Estudos: Testes e mocks para aplicações AWS
#tag #aws #cloud #devtools #testes #mocks #moto #sam #localstack #api-gateway #ci

> [!info] Visão Geral
> Testar aplicações AWS exige uma estratégia em camadas: testes unitários com stubs/mocks/fakes (Boto3 Stubber, Moto, aws-sdk-client-mock, Mockito, injeção de dependência), integração local com emuladores e eventos de teste (SAM CLI, LocalStack, DynamoDB Local, generate-event, aws lambda invoke), APIs mock (integração MOCK do API Gateway, Prism, WireMock, contratos), segurança e governança de ambientes de teste (contas separadas, OIDC, dados sintéticos, custos, limpeza) e qualidade contínua no CI (CodeBuild reports, cobertura, flaky, CodeDeploy hooks).

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Estratégia de testes em nuvem**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.6. Testes e mocks para aplicações AWS/1. Fundamentos/1.1 Visão geral/1.1.1. Estratégia de testes em nuvem/1.1.1.1. Estratégia de testes para aplicações AWS — pirâmide de testes, stubs, mocks, fakes, emuladores e serviços reais, o que testar onde e custo versus confiança|1.1.1.1. Estratégia de testes para aplicações AWS — pirâmide de testes, stubs, mocks, fakes, emuladores e serviços reais, o que testar onde e custo versus confiança]]

---

## 2 Domínio: Mocks em código

### 2.1 Moto, Stubber, SDK mocks e injeção
- **2.1.1. Testes unitários**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.6. Testes e mocks para aplicações AWS/2. Mocks em código/2.1 Moto, Stubber, SDK mocks e injeção/2.1.1. Testes unitários/2.1.1.1. Mocks do SDK em código — Moto, Boto3 Stubber, aws-sdk-client-mock, Mockito e injeção de dependência para testes unitários de Lambda, DynamoDB e S3|2.1.1.1. Mocks do SDK em código — Moto, Boto3 Stubber, aws-sdk-client-mock, Mockito e injeção de dependência para testes unitários de Lambda, DynamoDB e S3]]

---

## 3 Domínio: Emuladores e eventos de teste

### 3.1 SAM local, LocalStack e eventos
- **3.1.1. Execução local**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.6. Testes e mocks para aplicações AWS/3. Emuladores e eventos de teste/3.1 SAM local, LocalStack e eventos/3.1.1. Execução local/3.1.1.1. Execução local e eventos de teste — SAM CLI local invoke e start-api, generate-event, LocalStack, DynamoDB Local, eventos de teste do console Lambda e aws lambda invoke|3.1.1.1. Execução local e eventos de teste — SAM CLI local invoke e start-api, generate-event, LocalStack, DynamoDB Local, eventos de teste do console Lambda e aws lambda invoke]]

---

## 4 Domínio: APIs mock

### 4.1 API Gateway MOCK, OpenAPI e contratos
- **4.1.1. Simulação de dependências**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.6. Testes e mocks para aplicações AWS/4. APIs mock/4.1 API Gateway MOCK, OpenAPI e contratos/4.1.1. Simulação de dependências/4.1.1.1. APIs mock — integração MOCK do API Gateway, mapping templates, OpenAPI, Prism, WireMock, testes de contrato e simulação de dependências externas|4.1.1.1. APIs mock — integração MOCK do API Gateway, mapping templates, OpenAPI, Prism, WireMock, testes de contrato e simulação de dependências externas]]

---

## 5 Domínio: Segurança e governança

### 5.1 Dados de teste, contas e credenciais
- **5.1.1. Controle e conformidade**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.6. Testes e mocks para aplicações AWS/5. Segurança e governança/5.1 Dados de teste, contas e credenciais/5.1.1. Controle e conformidade/5.1.1.1. Segurança e governança em testes AWS — dados de teste, contas separadas, credenciais e OIDC no CI, IAM de teste, isolamento, custos, limpeza e conformidade|5.1.1.1. Segurança e governança em testes AWS — dados de teste, contas separadas, credenciais e OIDC no CI, IAM de teste, isolamento, custos, limpeza e conformidade]]

---

## 6 Domínio: Operação e CI

### 6.1 Pipelines, cobertura e troubleshooting
- **6.1.1. Qualidade contínua**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.6. Testes e mocks para aplicações AWS/6. Operação e CI/6.1 Pipelines, cobertura e troubleshooting/6.1.1. Qualidade contínua/6.1.1.1. Testes no pipeline de CI — CodeBuild, relatórios de teste e cobertura, estágios, testes flaky, troubleshooting de testes e checklist de qualidade|6.1.1.1. Testes no pipeline de CI — CodeBuild, relatórios de teste e cobertura, estágios, testes flaky, troubleshooting de testes e checklist de qualidade]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.5. AWS SDKs, CLI e SigV4/0 AWS SDKs, CLI e SigV4 (Tópicos )|AWS SDKs, CLI e SigV4]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.5. Amazon API Gateway/0 Amazon API Gateway (Tópicos )|Amazon API Gateway]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.2. Amazon DynamoDB/0 Amazon DynamoDB (Tópicos )|Amazon DynamoDB]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.1. Amazon S3/0 Amazon S3 (Tópicos )|Amazon S3]]
