# 📚 Guia de Estudos: AWS Control Tower
#tag #aws #cloud #governanca #controltower #landing-zone #multi-conta

> [!info] Visão Geral
> O AWS Control Tower monta e governa um ambiente AWS multi-conta seguindo as melhores práticas: cria uma landing zone com contas fundamentais (Management, Log Archive e Audit), OUs, logs centralizados, acesso federado e controles preventivos, detectivos e proativos, além de provisionar contas padronizadas pelo Account Factory. Este guia cobre os fundamentos, a montagem da landing zone, os controles, o Account Factory (AFT, CfCT, blueprints), a governança contínua (drift, Security Hub, Audit Manager) e a operação (custos, permissões, limites e troubleshooting).

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Landing zone e arquitetura**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.7. AWS Control Tower/1. Fundamentos/1.1 Visão geral/1.1.1. Landing zone e arquitetura/1.1.1.1. O que é AWS Control Tower — landing zone multi-conta, contas e OUs, controles, home region e quando usar|1.1.1.1. O que é AWS Control Tower — landing zone multi-conta, contas e OUs, controles, home region e quando usar]]

---

## 2 Domínio: Landing zone

### 2.1 Configuração e baseline
- **2.1.1. Contas, OUs, identidade e logs**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.7. AWS Control Tower/2. Landing zone/2.1 Configuração e baseline/2.1.1. Contas, OUs, identidade e logs/2.1.1.1. Montando a landing zone — desenho de OUs, contas fundamentais, IAM Identity Center, logs centralizados, regiões governadas e atualizações de versão|2.1.1.1. Montando a landing zone — desenho de OUs, contas fundamentais, IAM Identity Center, logs centralizados, regiões governadas e atualizações de versão]]

---

## 3 Domínio: Controles

### 3.1 Controls e conformidade
- **3.1.1. Preventivos, detectivos e proativos**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.7. AWS Control Tower/3. Controles/3.1 Controls e conformidade/3.1.1. Preventivos, detectivos e proativos/3.1.1.1. Controles do Control Tower — preventivos, detectivos e proativos, comportamento e orientação, catálogo, habilitação por OU e conformidade|3.1.1.1. Controles do Control Tower — preventivos, detectivos e proativos, comportamento e orientação, catálogo, habilitação por OU e conformidade]]

---

## 4 Domínio: Account Factory

### 4.1 Provisionamento de contas
- **4.1.1. Account Factory, AFT e customizações**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.7. AWS Control Tower/4. Account Factory/4.1 Provisionamento de contas/4.1.1. Account Factory, AFT e customizações/4.1.1.1. Account Factory — criação e inscrição de contas, Service Catalog, AFT com Terraform, CfCT, blueprints e ciclo de vida de contas|4.1.1.1. Account Factory — criação e inscrição de contas, Service Catalog, AFT com Terraform, CfCT, blueprints e ciclo de vida de contas]]

---

## 5 Domínio: Governança contínua

### 5.1 Drift, integrações e conformidade
- **5.1.1. Drift, Security Hub e ecossistema de segurança**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.7. AWS Control Tower/5. Governança contínua/5.1 Drift, integrações e conformidade/5.1.1. Drift, Security Hub e ecossistema de segurança/5.1.1.1. Governança contínua — drift, reparo, atualização de contas, Security Hub, Audit Manager, GuardDuty e integração com o ecossistema de segurança|5.1.1.1. Governança contínua — drift, reparo, atualização de contas, Security Hub, Audit Manager, GuardDuty e integração com o ecossistema de segurança]]

---

## 6 Domínio: Operação

### 6.1 Custo, segurança e diagnóstico
- **6.1.1. Custos, permissões e checklist**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.7. AWS Control Tower/6. Operação/6.1 Custo, segurança e diagnóstico/6.1.1. Custos, permissões e checklist/6.1.1.1. Operando o Control Tower — custos, permissões, limites, troubleshooting de falhas e checklist de produção|6.1.1.1. Operando o Control Tower — custos, permissões, limites, troubleshooting de falhas e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.6. AWS Service Catalog/0 AWS Service Catalog (Tópicos )|AWS Service Catalog]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.5. AWS CloudFormation/0 AWS CloudFormation (Tópicos )|AWS CloudFormation]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.3. AWS Config/0 AWS Config (Tópicos )|AWS Config]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.2. AWS CloudTrail/0 AWS CloudTrail (Tópicos )|AWS CloudTrail]]
