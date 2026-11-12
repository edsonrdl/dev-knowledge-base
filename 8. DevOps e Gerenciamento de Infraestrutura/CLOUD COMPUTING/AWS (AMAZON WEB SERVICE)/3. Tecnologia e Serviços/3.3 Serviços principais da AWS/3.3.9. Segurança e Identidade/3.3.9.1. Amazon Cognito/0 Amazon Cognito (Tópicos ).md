# 📚 Guia de Estudos: Amazon Cognito
#tag #aws #cloud #seguranca #identidade #cognito #oauth #jwt #userpool #identitypool

> [!info] Visão Geral
> O Amazon Cognito é o serviço gerenciado de identidade de clientes (CIAM) da AWS: o user pool é o diretório de usuários e provedor OIDC que emite tokens JWT (ID, access, refresh), com cadastro, MFA, passkeys, federação social, SAML e OIDC; o identity pool troca tokens por credenciais AWS temporárias (STS) para acesso direto a serviços como S3 e DynamoDB. Este guia cobre fundamentos, user pools, tokens e federação, identity pools, integrações (API Gateway, ALB, AppSync, Lambda triggers, multi-tenancy) e segurança e operação.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Identidade para aplicações**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.1. Amazon Cognito/1. Fundamentos/1.1 Visão geral/1.1.1. Identidade para aplicações/1.1.1.1. O que é Amazon Cognito — user pools, identity pools, tokens JWT, autenticação vs autorização e quando usar em vez de IAM, Identity Center ou IdP próprio|1.1.1.1. O que é Amazon Cognito — user pools, identity pools, tokens JWT, autenticação vs autorização e quando usar em vez de IAM, Identity Center ou IdP próprio]]

---

## 2 Domínio: User pools

### 2.1 Diretório de usuários e login
- **2.1.1. Cadastro, atributos, grupos, MFA e Managed Login**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.1. Amazon Cognito/2. User pools/2.1 Diretório de usuários e login/2.1.1. Cadastro, atributos, grupos, MFA e Managed Login/2.1.1.1. User pools em profundidade — cadastro e verificação, atributos, grupos, políticas de senha, MFA e passkeys, recuperação de conta, app clients e Managed Login|2.1.1.1. User pools em profundidade — cadastro e verificação, atributos, grupos, políticas de senha, MFA e passkeys, recuperação de conta, app clients e Managed Login]]

---

## 3 Domínio: Tokens, OAuth e federação

### 3.1 Fluxos e provedores
- **3.1.1. OAuth 2.0, OIDC, SAML e social login**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.1. Amazon Cognito/3. Tokens, OAuth e federação/3.1 Fluxos e provedores/3.1.1. OAuth 2.0, OIDC, SAML e social login/3.1.1.1. Tokens, OAuth 2.0 e federação no Cognito — ID, access e refresh tokens, validação de JWT, escopos e resource servers, M2M, login social, SAML e OIDC|3.1.1.1. Tokens, OAuth 2.0 e federação no Cognito — ID, access e refresh tokens, validação de JWT, escopos e resource servers, M2M, login social, SAML e OIDC]]

---

## 4 Domínio: Identity pools e acesso AWS

### 4.1 Credenciais temporárias
- **4.1.1. STS, roles e mapeamento de identidades**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.1. Amazon Cognito/4. Identity pools e acesso AWS/4.1 Credenciais temporárias/4.1.1. STS, roles e mapeamento de identidades/4.1.1.1. Identity pools do Cognito — credenciais temporárias via STS, roles autenticada e não autenticada, mapeamento de papéis, políticas por usuário e acesso direto a S3 e DynamoDB|4.1.1.1. Identity pools do Cognito — credenciais temporárias via STS, roles autenticada e não autenticada, mapeamento de papéis, políticas por usuário e acesso direto a S3 e DynamoDB]]

---

## 5 Domínio: Integrações e Lambda triggers

### 5.1 API Gateway, ALB, AppSync e customização
- **5.1.1. Authorizers, triggers e SDKs**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.1. Amazon Cognito/5. Integrações e Lambda triggers/5.1 API Gateway, ALB, AppSync e customização/5.1.1. Authorizers, triggers e SDKs/5.1.1.1. Integrações do Cognito — authorizer do API Gateway, ALB, AppSync, Amplify e SDKs, Lambda triggers de cadastro, login e tokens, e padrões de multi-tenancy|5.1.1.1. Integrações do Cognito — authorizer do API Gateway, ALB, AppSync, Amplify e SDKs, Lambda triggers de cadastro, login e tokens, e padrões de multi-tenancy]]

---

## 6 Domínio: Segurança e operação

### 6.1 Proteção, custos e troubleshooting
- **6.1.1. Threat protection, logs, quotas, custos e checklist**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.1. Amazon Cognito/6. Segurança e operação/6.1 Proteção, custos e troubleshooting/6.1.1. Threat protection, logs, quotas, custos e checklist/6.1.1.1. Segurança e operação do Cognito — threat protection, WAF, logs e métricas, quotas, custos de MAU, SMS e M2M, backup e migração, IaC e checklist de produção|6.1.1.1. Segurança e operação do Cognito — threat protection, WAF, logs e métricas, quotas, custos de MAU, SMS e M2M, backup e migração, IaC e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.5. Amazon API Gateway/0 Amazon API Gateway (Tópicos )|Amazon API Gateway]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.7. Elastic Load Balancing/0 Elastic Load Balancing (Tópicos )|Elastic Load Balancing]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.2. AWS Lambda/0 AWS Lambda (Tópicos )|AWS Lambda]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/2. Segurança e Conformidade/2.3 Capacidades de gerenciamento de acesso da AWS/2.3.1. Identity and Access Management (IAM)/2.3.1.4. IAM Identity Center (SSO)|IAM Identity Center]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/2. Segurança e Conformidade/2.3 Capacidades de gerenciamento de acesso da AWS/2.3.2. Serviços de segurança/2.3.2.3. AWS WAF|AWS WAF]]
