# 📚 Guia de Estudos: AWS Global Accelerator
#tag #aws #cloud #rede #globalaccelerator #anycast

> [!info] Visão Geral
> O AWS Global Accelerator fornece IPs anycast estáticos e leva o tráfego TCP/UDP dos usuários até o endpoint saudável mais próximo pela rede de backbone da AWS, com failover rápido entre regiões. Este guia cobre aceleradores, listeners, endpoint groups, traffic dials, health checks e a comparação com CloudFront e Route 53.

---

## 1 Domínio: Fundamentos

### 1.1 O que é Global Accelerator
- **1.1.1. Anycast, aceleradores e endpoints**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.8. AWS Global Accelerator/1. Fundamentos/1.1 O que é Global Accelerator/1.1.1. Anycast, aceleradores e endpoints/1.1.1.1. O que é AWS Global Accelerator — IPs anycast, rede global da AWS, aceleradores, listeners e endpoints|1.1.1.1. O que é AWS Global Accelerator — IPs anycast, rede global da AWS, aceleradores, listeners e endpoints]]

---

## 2 Domínio: Roteamento e Operação

### 2.1 Tráfego e Saúde
- **2.1.1. Traffic dials, health checks e comparação**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.8. AWS Global Accelerator/2. Roteamento e Operação/2.1 Tráfego e Saúde/2.1.1. Traffic dials, health checks e comparação/2.1.1.1. Traffic dials, health checks e failover — e quando usar Global Accelerator, CloudFront ou Route 53|2.1.1.1. Traffic dials, health checks e failover — e quando usar Global Accelerator, CloudFront ou Route 53]]

### 2.2 Prática e Operação
- **2.2.1. Custom routing, BYOIP e observabilidade**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.8. AWS Global Accelerator/2. Roteamento e Operação/2.2 Prática e Operação/2.2.1. Custom routing, BYOIP e observabilidade/2.2.1.1. Global Accelerator na prática — custom routing, BYOIP, preservação do IP do cliente, integração com ALB e NLB, observabilidade, segurança e custo|2.2.1.1. Global Accelerator na prática — custom routing, BYOIP, preservação do IP do cliente, integração com ALB e NLB, observabilidade, segurança e custo]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.7. Elastic Load Balancing/0 Elastic Load Balancing (Tópicos )|Elastic Load Balancing]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.6. Amazon CloudFront/0 Amazon CloudFront (Tópicos )|Amazon CloudFront]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.5. Amazon Route 53/0 Amazon Route 53 (Tópicos )|Amazon Route 53]]
