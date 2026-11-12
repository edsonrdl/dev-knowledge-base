# 📚 Guia de Estudos: AWS Network Firewall
#tag #aws #cloud #seguranca #rede #networkfirewall #ips #suricata #vpc

> [!info] Visão Geral
> O AWS Network Firewall é o firewall de rede gerenciado e serviço de IDS/IPS da AWS para VPCs: inspeção stateless e stateful, filtragem por domínio, regras compatíveis com Suricata, regras gerenciadas e inspeção TLS opcional. Este guia cobre fundamentos, arquitetura e roteamento (endpoints por AZ, topologias distribuída e centralizada), regras e ordem de avaliação, inspeção centralizada com Transit Gateway e Firewall Manager, segurança e governança do próprio firewall e operação (quotas, custos, runbooks).

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Firewall de rede gerenciado**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.3. AWS Network Firewall/1. Fundamentos/1.1 Visão geral/1.1.1. Firewall de rede gerenciado/1.1.1.1. O que é AWS Network Firewall — firewall de rede gerenciado na VPC, inspeção stateless e stateful, IPS, firewall policy e quando usar em vez de Security Groups, NACLs e WAF|1.1.1.1. O que é AWS Network Firewall — firewall de rede gerenciado na VPC, inspeção stateless e stateful, IPS, firewall policy e quando usar em vez de Security Groups, NACLs e WAF]]

---

## 2 Domínio: Arquitetura e implantação

### 2.1 Firewalls, políticas e endpoints
- **2.1.1. Topologias na VPC**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.3. AWS Network Firewall/2. Arquitetura e implantação/2.1 Firewalls, políticas e endpoints/2.1.1. Topologias na VPC/2.1.1.1. Arquitetura do Network Firewall — firewall, policy, subnets e endpoints, roteamento, topologias distribuída e centralizada, alta disponibilidade e tabelas de rota|2.1.1.1. Arquitetura do Network Firewall — firewall, policy, subnets e endpoints, roteamento, topologias distribuída e centralizada, alta disponibilidade e tabelas de rota]]

---

## 3 Domínio: Regras e inspeção

### 3.1 Stateless, stateful e Suricata
- **3.1.1. Motor de regras**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.3. AWS Network Firewall/3. Regras e inspeção/3.1 Stateless, stateful e Suricata/3.1.1. Motor de regras/3.1.1.1. Regras do Network Firewall — rule groups stateless e stateful, ações, listas de domínios, Suricata, ordem de avaliação, regras gerenciadas e exemplos|3.1.1.1. Regras do Network Firewall — rule groups stateless e stateful, ações, listas de domínios, Suricata, ordem de avaliação, regras gerenciadas e exemplos]]

---

## 4 Domínio: Integrações e inspeção centralizada

### 4.1 Firewall Manager, Transit Gateway e logs
- **4.1.1. Roteamento e governança**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.3. AWS Network Firewall/4. Integrações e inspeção centralizada/4.1 Firewall Manager, Transit Gateway e logs/4.1.1. Roteamento e governança/4.1.1.1. Inspeção centralizada e integrações do Network Firewall — Transit Gateway, Firewall Manager, logs em S3, CloudWatch e Firehose, e automação|4.1.1.1. Inspeção centralizada e integrações do Network Firewall — Transit Gateway, Firewall Manager, logs em S3, CloudWatch e Firehose, e automação]]

---

## 5 Domínio: Segurança e governança

### 5.1 IAM, logging e conformidade
- **5.1.1. Controle e auditoria**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.3. AWS Network Firewall/5. Segurança e governança/5.1 IAM, logging e conformidade/5.1.1. Controle e auditoria/5.1.1.1. Segurança do Network Firewall — IAM, proteção contra alteração, logging, TLS inspection e certificados, endurecimento e governança|5.1.1.1. Segurança do Network Firewall — IAM, proteção contra alteração, logging, TLS inspection e certificados, endurecimento e governança]]

---

## 6 Domínio: Operação e custos

### 6.1 Quotas, custos e troubleshooting
- **6.1.1. Observabilidade e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.3. AWS Network Firewall/6. Operação e custos/6.1 Quotas, custos e troubleshooting/6.1.1. Observabilidade e troubleshooting/6.1.1.1. Operação do Network Firewall — quotas e capacidade, custos por endpoint e por GB, métricas, troubleshooting e checklist de produção|6.1.1.1. Operação do Network Firewall — quotas e capacidade, custos por endpoint e por GB, métricas, troubleshooting e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.1. Amazon VPC/0 Amazon VPC (Tópicos )|Amazon VPC]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.1. AWS CloudWatch/0 AWS CloudWatch (Tópicos )|AWS CloudWatch]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.2. AWS CloudTrail/0 AWS CloudTrail (Tópicos )|AWS CloudTrail]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.1. Amazon S3/0 Amazon S3 (Tópicos )|Amazon S3]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.2. Amazon Macie/0 Amazon Macie (Tópicos )|Amazon Macie]]
