# 📚 Guia de Estudos: AWS Firewall Manager
#tag #aws #cloud #seguranca #governanca #firewallmanager #organizations #waf #shield

> [!info] Visão Geral
> O AWS Firewall Manager é o serviço de gerenciamento central de políticas de segurança de rede para AWS Organizations: define políticas uma vez e as aplica, monitora e remedia em todas as contas e recursos, inclusive futuros. Cobre WAF, Shield Advanced, Security Groups, Network Firewall, DNS Firewall, NACL e firewalls de terceiros. Este guia trata de fundamentos, configuração e escopo, tipos de política, conformidade e remediação, segurança do próprio serviço e operação (custos, quotas, runbooks).

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Governança central de segurança**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.4. AWS Firewall Manager/1. Fundamentos/1.1 Visão geral/1.1.1. Governança central de segurança/1.1.1.1. O que é AWS Firewall Manager — governança central de segurança em Organizations, políticas, escopo, conformidade e quando usar|1.1.1.1. O que é AWS Firewall Manager — governança central de segurança em Organizations, políticas, escopo, conformidade e quando usar]]

---

## 2 Domínio: Configuração e escopo

### 2.1 Organizations, Config e administrador
- **2.1.1. Pré-requisitos e escopo**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.4. AWS Firewall Manager/2. Configuração e escopo/2.1 Organizations, Config e administrador/2.1.1. Pré-requisitos e escopo/2.1.1.1. Configuração do Firewall Manager — pré-requisitos, Organizations, AWS Config, administrador, regiões, escopo por OU e tags, piloto e primeiros passos|2.1.1.1. Configuração do Firewall Manager — pré-requisitos, Organizations, AWS Config, administrador, regiões, escopo por OU e tags, piloto e primeiros passos]]

---

## 3 Domínio: Tipos de política

### 3.1 WAF, Shield, Security Groups, Network Firewall e DNS Firewall
- **3.1.1. Políticas por serviço**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.4. AWS Firewall Manager/3. Tipos de política/3.1 WAF, Shield, Security Groups, Network Firewall e DNS Firewall/3.1.1. Políticas por serviço/3.1.1.1. Políticas do Firewall Manager — WAF, Shield Advanced, Security Groups, Network Firewall, DNS Firewall, NACL e firewalls de terceiros, com exemplos e armadilhas|3.1.1.1. Políticas do Firewall Manager — WAF, Shield Advanced, Security Groups, Network Firewall, DNS Firewall, NACL e firewalls de terceiros, com exemplos e armadilhas]]

---

## 4 Domínio: Conformidade e remediação

### 4.1 Auditoria, auto-remediação e integrações
- **4.1.1. Detecção de desvios**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.4. AWS Firewall Manager/4. Conformidade e remediação/4.1 Auditoria, auto-remediação e integrações/4.1.1. Detecção de desvios/4.1.1.1. Conformidade e remediação no Firewall Manager — auditoria, auto-remediação, notificações, Security Hub, logs centralizados e automação|4.1.1.1. Conformidade e remediação no Firewall Manager — auditoria, auto-remediação, notificações, Security Hub, logs centralizados e automação]]

---

## 5 Domínio: Segurança e governança

### 5.1 Delegação, roles e proteção
- **5.1.1. Controle e auditoria**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.4. AWS Firewall Manager/5. Segurança e governança/5.1 Delegação, roles e proteção/5.1.1. Controle e auditoria/5.1.1.1. Segurança do Firewall Manager — roles vinculadas, administradores delegados e escopo, proteção de políticas, SCPs, auditoria e governança|5.1.1.1. Segurança do Firewall Manager — roles vinculadas, administradores delegados e escopo, proteção de políticas, SCPs, auditoria e governança]]

---

## 6 Domínio: Operação e custos

### 6.1 Quotas, custos e troubleshooting
- **6.1.1. Observabilidade e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.4. AWS Firewall Manager/6. Operação e custos/6.1 Quotas, custos e troubleshooting/6.1.1. Observabilidade e troubleshooting/6.1.1.1. Operação do Firewall Manager — quotas, custos por política e AWS Config, métricas, troubleshooting e checklist de produção|6.1.1.1. Operação do Firewall Manager — quotas, custos por política e AWS Config, métricas, troubleshooting e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.3. AWS Network Firewall/0 AWS Network Firewall (Tópicos )|AWS Network Firewall]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.3. AWS Config/0 AWS Config (Tópicos )|AWS Config]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.2. AWS CloudTrail/0 AWS CloudTrail (Tópicos )|AWS CloudTrail]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.7. AWS Control Tower/0 AWS Control Tower (Tópicos )|AWS Control Tower]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.2. Amazon Macie/0 Amazon Macie (Tópicos )|Amazon Macie]]
