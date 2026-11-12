# 📚 Guia de Estudos: AWS SDKs, CLI e SigV4
#tag #aws #cloud #devtools #sdk #cli #sigv4 #retries #credenciais #serializacao

> [!info] Visão Geral
> Tudo na AWS é uma API HTTPS; os SDKs e a CLI são os clientes que resolvem credenciais, região e endpoint, serializam e assinam (SigV4) as requisições, tentam de novo com backoff e jitter, paginam resultados e interpretam erros. Este guia cobre fundamentos de acesso programático, credential provider chain e SigV4, chamadas resilientes (retries, timeouts, idempotência, paginação, throttling), padrões de uso (clientes, waiters, serialização e desserialização), segurança de credenciais e depuração/operação.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Acesso programático à AWS**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.5. AWS SDKs, CLI e SigV4/1. Fundamentos/1.1 Visão geral/1.1.1. Acesso programático à AWS/1.1.1.1. O que são os AWS SDKs, a CLI e a API da AWS — como uma chamada vira uma requisição HTTP, endpoints regionais, SDKs por linguagem e quando usar CLI, SDK, CloudFormation ou console|1.1.1.1. O que são os AWS SDKs, a CLI e a API da AWS — como uma chamada vira uma requisição HTTP, endpoints regionais, SDKs por linguagem e quando usar CLI, SDK, CloudFormation ou console]]

---

## 2 Domínio: Credenciais e assinatura

### 2.1 Credential provider chain, perfis e SigV4
- **2.1.1. Identidade e assinatura de requisições**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.5. AWS SDKs, CLI e SigV4/2. Credenciais e assinatura/2.1 Credential provider chain, perfis e SigV4/2.1.1. Identidade e assinatura de requisições/2.1.1.1. Credenciais e SigV4 — credential provider chain, perfis, SSO, roles e AssumeRole, credenciais temporárias, assinatura Signature Version 4 e erros de autenticação|2.1.1.1. Credenciais e SigV4 — credential provider chain, perfis, SSO, roles e AssumeRole, credenciais temporárias, assinatura Signature Version 4 e erros de autenticação]]

---

## 3 Domínio: Resiliência das chamadas

### 3.1 Retries, backoff, timeouts e paginação
- **3.1.1. Chamadas robustas**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.5. AWS SDKs, CLI e SigV4/3. Resiliência das chamadas/3.1 Retries, backoff, timeouts e paginação/3.1.1. Chamadas robustas/3.1.1.1. Chamadas resilientes — retries, modos standard e adaptive, backoff exponencial com jitter, timeouts, idempotência, throttling e paginação|3.1.1.1. Chamadas resilientes — retries, modos standard e adaptive, backoff exponencial com jitter, timeouts, idempotência, throttling e paginação]]

---

## 4 Domínio: Padrões de uso

### 4.1 Clientes, waiters, serialização e boas práticas
- **4.1.1. Uso eficiente dos SDKs**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.5. AWS SDKs, CLI e SigV4/4. Padrões de uso/4.1 Clientes, waiters, serialização e boas práticas/4.1.1. Uso eficiente dos SDKs/4.1.1.1. Padrões de uso dos SDKs — clientes e resources, waiters, serialização e desserialização (JSON, DynamoDB, base64), reuso de conexões e boas práticas por linguagem|4.1.1.1. Padrões de uso dos SDKs — clientes e resources, waiters, serialização e desserialização (JSON, DynamoDB, base64), reuso de conexões e boas práticas por linguagem]]

---

## 5 Domínio: Segurança e governança

### 5.1 Credenciais, menor privilégio e auditoria
- **5.1.1. Controle e conformidade**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.5. AWS SDKs, CLI e SigV4/5. Segurança e governança/5.1 Credenciais, menor privilégio e auditoria/5.1.1. Controle e conformidade/5.1.1.1. Segurança no uso dos SDKs — gestão de credenciais, menor privilégio, roles em vez de chaves, IMDSv2, segredos, auditoria e rotação|5.1.1.1. Segurança no uso dos SDKs — gestão de credenciais, menor privilégio, roles em vez de chaves, IMDSv2, segredos, auditoria e rotação]]

---

## 6 Domínio: Operação e troubleshooting

### 6.1 Logs, métricas e erros comuns
- **6.1.1. Depuração e observabilidade**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.5. AWS SDKs, CLI e SigV4/6. Operação e troubleshooting/6.1 Logs, métricas e erros comuns/6.1.1. Depuração e observabilidade/6.1.1.1. Depuração e operação com SDKs — logs de debug, métricas, rastreamento, erros comuns, troubleshooting e checklist|6.1.1.1. Depuração e operação com SDKs — logs de debug, métricas, rastreamento, erros comuns, troubleshooting e checklist]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.1. Amazon Cognito/0 Amazon Cognito (Tópicos )|Amazon Cognito]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.2. Amazon DynamoDB/0 Amazon DynamoDB (Tópicos )|Amazon DynamoDB]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.1. Amazon SQS/0 Amazon SQS (Tópicos )|Amazon SQS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.5. Amazon API Gateway/0 Amazon API Gateway (Tópicos )|Amazon API Gateway]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.1. Amazon S3/0 Amazon S3 (Tópicos )|Amazon S3]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.8. AWS X-Ray/0 AWS X-Ray (Tópicos )|AWS X-Ray]]
