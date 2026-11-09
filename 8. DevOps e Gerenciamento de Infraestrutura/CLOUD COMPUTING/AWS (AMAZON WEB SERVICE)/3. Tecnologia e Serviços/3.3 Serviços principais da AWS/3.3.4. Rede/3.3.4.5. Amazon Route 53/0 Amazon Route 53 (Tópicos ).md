# 📚 Guia de Estudos: Amazon Route 53
#tag #aws #cloud #rede #dns #route53

> [!info] Visão Geral
> O Amazon Route 53 é o serviço de DNS gerenciado da AWS: DNS autoritativo com SLA de 100% (conferir o SLA vigente), roteamento inteligente de tráfego (peso, latência, geografia, failover), health checks, resolução de nomes dentro de VPCs (Resolver) e registro de domínios. Este guia cobre desde o modelo de DNS e as hosted zones até políticas de roteamento, arquiteturas de alta disponibilidade multi-região e DNS híbrido com on-premises.

---

## 1 Domínio: Fundamentos e Zonas DNS

### 1.1 O que é Route 53
- **1.1.1. Conceito e modelo de DNS**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.5. Amazon Route 53/1. Fundamentos e Zonas DNS/1.1 O que é Route 53/1.1.1. Conceito e modelo de DNS/1.1.1.1. O que é Route 53 — DNS gerenciado, as funções do serviço, TTL e o fluxo de resolução|1.1.1.1. O que é Route 53 — DNS gerenciado, as funções do serviço, TTL e o fluxo de resolução]]

### 1.2 Hosted Zones e Registros
- **1.2.1. Tipos de registro e Alias**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.5. Amazon Route 53/1. Fundamentos e Zonas DNS/1.2 Hosted Zones e Registros/1.2.1. Tipos de registro e Alias/1.2.1.1. Hosted Zones públicas e privadas — tipos de registro, delegação de NS e split-horizon DNS|1.2.1.1. Hosted Zones públicas e privadas — tipos de registro, delegação de NS e split-horizon DNS]]
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.5. Amazon Route 53/1. Fundamentos e Zonas DNS/1.2 Hosted Zones e Registros/1.2.1. Tipos de registro e Alias/1.2.1.2. Alias vs CNAME — zone apex, alvos AWS suportados, custo de consulta e Evaluate Target Health|1.2.1.2. Alias vs CNAME — zone apex, alvos AWS suportados, custo de consulta e Evaluate Target Health]]

---

## 2 Domínio: Políticas de Roteamento

### 2.1 Roteamento Estático e Ponderado
- **2.1.1. Simple, Weighted e Multivalue**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.5. Amazon Route 53/2. Políticas de Roteamento/2.1 Roteamento Estático e Ponderado/2.1.1. Simple, Weighted e Multivalue/2.1.1.1. Simple, Weighted e Multivalue Answer — distribuição por peso, canary e blue-green via DNS|2.1.1.1. Simple, Weighted e Multivalue Answer — distribuição por peso, canary e blue-green via DNS]]

### 2.2 Roteamento Inteligente
- **2.2.1. Latency, Geolocation, Geoproximity e IP-based**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.5. Amazon Route 53/2. Políticas de Roteamento/2.2 Roteamento Inteligente/2.2.1. Latency, Geolocation, Geoproximity e IP-based/2.2.1.1. Latency e Geolocation — roteamento por proximidade de rede e por localização do usuário|2.2.1.1. Latency e Geolocation — roteamento por proximidade de rede e por localização do usuário]]
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.5. Amazon Route 53/2. Políticas de Roteamento/2.2 Roteamento Inteligente/2.2.1. Latency, Geolocation, Geoproximity e IP-based/2.2.1.2. Geoproximity e IP-based routing — bias, Traffic Flow e CIDR de origem|2.2.1.2. Geoproximity e IP-based routing — bias, Traffic Flow e CIDR de origem]]

---

## 3 Domínio: Alta Disponibilidade e Failover

### 3.1 Health Checks
- **3.1.1. Tipos de verificação e alarmes**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.5. Amazon Route 53/3. Alta Disponibilidade e Failover/3.1 Health Checks/3.1.1. Tipos de verificação e alarmes/3.1.1.1. Health Checks — endpoint, calculated e CloudWatch alarm, string matching, intervalos e custo|3.1.1.1. Health Checks — endpoint, calculated e CloudWatch alarm, string matching, intervalos e custo]]

### 3.2 Failover e DR
- **3.2.1. Active-passive, active-active e arquiteturas multi-região**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.5. Amazon Route 53/3. Alta Disponibilidade e Failover/3.2 Failover e DR/3.2.1. Active-passive, active-active e arquiteturas multi-região/3.2.1.1. Failover com Route 53 — active-passive, active-active e arquiteturas multi-região|3.2.1.1. Failover com Route 53 — active-passive, active-active e arquiteturas multi-região]]

---

## 4 Domínio: Resolver e DNS Híbrido

### 4.1 Route 53 Resolver
- **4.1.1. Endpoints inbound e outbound**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.5. Amazon Route 53/4. Resolver e DNS Híbrido/4.1 Route 53 Resolver/4.1.1. Endpoints inbound e outbound/4.1.1.1. Route 53 Resolver — endpoints inbound e outbound, regras de encaminhamento e DNS híbrido|4.1.1.1. Route 53 Resolver — endpoints inbound e outbound, regras de encaminhamento e DNS híbrido]]

### 4.2 Domínios e DNSSEC
- **4.2.1. Registro de domínios e segurança**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.5. Amazon Route 53/4. Resolver e DNS Híbrido/4.2 Domínios e DNSSEC/4.2.1. Registro de domínios e segurança/4.2.1.1. Registro de domínios, DNSSEC e boas práticas de segurança de DNS|4.2.1.1. Registro de domínios, DNSSEC e boas práticas de segurança de DNS]]

---

> **Links Relacionados:**
> [[1. REDES E INFRAESTRUTURA/Conceitos Fundamentais/DNS/0 DNS (Tópicos )|DNS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.1. Amazon VPC/0 Amazon VPC (Tópicos )|Amazon VPC]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/Guia de rede AWS VPC para ambientes de produção|Guia de rede AWS VPC para ambientes de produção]]
