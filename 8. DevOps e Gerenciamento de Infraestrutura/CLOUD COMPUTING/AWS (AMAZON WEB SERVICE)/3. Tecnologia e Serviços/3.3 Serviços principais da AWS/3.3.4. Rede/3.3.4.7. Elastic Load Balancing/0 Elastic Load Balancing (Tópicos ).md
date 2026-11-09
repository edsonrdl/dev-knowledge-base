# 📚 Guia de Estudos: Elastic Load Balancing
#tag #aws #cloud #rede #alb #nlb #gwlb #elb

> [!info] Visão Geral
> O Elastic Load Balancing (ELB) distribui tráfego entre alvos em várias Availability Zones, verifica a saúde deles e escala automaticamente. Este guia cobre os quatro tipos (ALB, NLB, GWLB e CLB legado), listeners e regras, target groups com health checks, e TLS, sticky sessions, cross-zone e logs.

---

## 1 Domínio: Fundamentos e Tipos

### 1.1 Visão geral
- **1.1.1. Tipos e escolha**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.7. Elastic Load Balancing/1. Fundamentos e Tipos/1.1 Visão geral/1.1.1. Tipos e escolha/1.1.1.1. O que é Elastic Load Balancing — tipos de load balancer, componentes e como escolher|1.1.1.1. O que é Elastic Load Balancing — tipos de load balancer, componentes e como escolher]]

---

## 2 Domínio: Application Load Balancer

### 2.1 ALB
- **2.1.1. Listeners, regras e roteamento**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.7. Elastic Load Balancing/2. Application Load Balancer/2.1 ALB/2.1.1. Listeners, regras e roteamento/2.1.1.1. Application Load Balancer — listeners, regras, ações e roteamento por caminho, host e header|2.1.1.1. Application Load Balancer — listeners, regras, ações e roteamento por caminho, host e header]]

### 2.2 ALB Avançado
- **2.2.1. Autenticação, gRPC, WAF e mTLS**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.7. Elastic Load Balancing/2. Application Load Balancer/2.2 ALB Avançado/2.2.1. Autenticação, gRPC, WAF e mTLS/2.2.1.1. ALB avançado — autenticação OIDC e Cognito, gRPC e WebSocket, WAF, mTLS, pesos entre target groups, regras e integrações com ECS, EKS e Lambda|2.2.1.1. ALB avançado — autenticação OIDC e Cognito, gRPC e WebSocket, WAF, mTLS, pesos entre target groups, regras e integrações com ECS, EKS e Lambda]]

---

## 3 Domínio: Network e Gateway Load Balancer

### 3.1 NLB
- **3.1.1. Camada 4 e IP estático**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.7. Elastic Load Balancing/3. Network e Gateway Load Balancer/3.1 NLB/3.1.1. Camada 4 e IP estático/3.1.1.1. Network Load Balancer — camada 4, IP estático, preservação de IP e PrivateLink|3.1.1.1. Network Load Balancer — camada 4, IP estático, preservação de IP e PrivateLink]]

### 3.2 GWLB e CLB
- **3.2.1. Appliances e legado**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.7. Elastic Load Balancing/3. Network e Gateway Load Balancer/3.2 GWLB e CLB/3.2.1. Appliances e legado/3.2.1.1. Gateway Load Balancer e Classic Load Balancer — appliances de rede e legado|3.2.1.1. Gateway Load Balancer e Classic Load Balancer — appliances de rede e legado]]

---

## 4 Domínio: Target Groups e Saúde

### 4.1 Target Groups
- **4.1.1. Alvos, health checks e draining**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.7. Elastic Load Balancing/4. Target Groups e Saúde/4.1 Target Groups/4.1.1. Alvos, health checks e draining/4.1.1.1. Target groups, health checks, deregistration delay e slow start|4.1.1.1. Target groups, health checks, deregistration delay e slow start]]

---

## 5 Domínio: TLS e Operação

### 5.1 TLS e Operação
- **5.1.1. Certificados, sticky, cross-zone e logs**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.7. Elastic Load Balancing/5. TLS e Operação/5.1 TLS e Operação/5.1.1. Certificados, sticky, cross-zone e logs/5.1.1.1. TLS, SNI, sticky sessions, cross-zone e logs de acesso|5.1.1.1. TLS, SNI, sticky sessions, cross-zone e logs de acesso]]

---

## 6 Domínio: Diagnóstico e Custo

### 6.1 Troubleshooting e Custo
- **6.1.1. Erros, logs, métricas e LCU**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.7. Elastic Load Balancing/6. Diagnóstico e Custo/6.1 Troubleshooting e Custo/6.1.1. Erros, logs, métricas e LCU/6.1.1.1. Diagnóstico e custo do Elastic Load Balancing — erros 4xx e 5xx do ELB, logs de acesso com Athena, métricas, LCU e otimização de custo|6.1.1.1. Diagnóstico e custo do Elastic Load Balancing — erros 4xx e 5xx do ELB, logs de acesso com Athena, métricas, LCU e otimização de custo]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.1. Amazon VPC/0 Amazon VPC (Tópicos )|Amazon VPC]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.6. Amazon CloudFront/0 Amazon CloudFront (Tópicos )|Amazon CloudFront]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.5. Amazon Route 53/0 Amazon Route 53 (Tópicos )|Amazon Route 53]]
