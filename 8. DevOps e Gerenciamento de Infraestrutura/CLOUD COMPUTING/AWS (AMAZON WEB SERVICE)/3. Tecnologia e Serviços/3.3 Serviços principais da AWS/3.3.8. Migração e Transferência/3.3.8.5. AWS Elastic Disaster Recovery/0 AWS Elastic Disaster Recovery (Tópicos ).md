# 📚 Guia de Estudos: AWS Elastic Disaster Recovery
#tag #aws #cloud #dr #disasterrecovery #drs #rpo #rto #migracao

> [!info] Visão Geral
> O AWS Elastic Disaster Recovery (DRS) replica continuamente, em nível de bloco, servidores de qualquer origem (on-premises, outras nuvens ou AWS) para uma área de staging de baixo custo na AWS, permitindo lançar instâncias EC2 completas em minutos (RPO de segundos, RTO de minutos), com drills não disruptivos, recuperação por ponto no tempo e failback. Este guia cobre fundamentos e estratégias de DR, arquitetura de replicação, drills/failover/failback, rede e configuração de recuperação, segurança do DR e operação (estados, lag, quotas, custos, runbooks).

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Recuperação de desastres contínua**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.5. AWS Elastic Disaster Recovery/1. Fundamentos/1.1 Visão geral/1.1.1. Recuperação de desastres contínua/1.1.1.1. O que é AWS Elastic Disaster Recovery — replicação contínua em nível de bloco, RPO de segundos e RTO de minutos, estratégias de DR e quando usar em vez de Backup e Pilot Light|1.1.1.1. O que é AWS Elastic Disaster Recovery — replicação contínua em nível de bloco, RPO de segundos e RTO de minutos, estratégias de DR e quando usar em vez de Backup e Pilot Light]]

---

## 2 Domínio: Replicação e arquitetura

### 2.1 Agente, servidores de replicação e staging
- **2.1.1. Fluxo de replicação**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.5. AWS Elastic Disaster Recovery/2. Replicação e arquitetura/2.1 Agente, servidores de replicação e staging/2.1.1. Fluxo de replicação/2.1.1.1. Arquitetura de replicação do Elastic Disaster Recovery — AWS Replication Agent, staging area, replication servers, volumes EBS, snapshots de ponto no tempo e conversion server|2.1.1.1. Arquitetura de replicação do Elastic Disaster Recovery — AWS Replication Agent, staging area, replication servers, volumes EBS, snapshots de ponto no tempo e conversion server]]

---

## 3 Domínio: Drills e recuperação

### 3.1 Testes, failover e failback
- **3.1.1. Execução de recuperação**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.5. AWS Elastic Disaster Recovery/3. Drills e recuperação/3.1 Testes, failover e failback/3.1.1. Execução de recuperação/3.1.1.1. Drills, failover e failback no Elastic Disaster Recovery — testes não disruptivos, recovery jobs, recuperação de ponto no tempo, failback e limpeza|3.1.1.1. Drills, failover e failback no Elastic Disaster Recovery — testes não disruptivos, recovery jobs, recuperação de ponto no tempo, failback e limpeza]]

---

## 4 Domínio: Rede e configuração

### 4.1 Launch settings, conectividade e pós-lançamento
- **4.1.1. Configuração dos recursos recuperados**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.5. AWS Elastic Disaster Recovery/4. Rede e configuração/4.1 Launch settings, conectividade e pós-lançamento/4.1.1. Configuração dos recursos recuperados/4.1.1.1. Rede e configuração no Elastic Disaster Recovery — launch settings, launch templates, conectividade, throttling, pós-lançamento com SSM, DNS e licenciamento|4.1.1.1. Rede e configuração no Elastic Disaster Recovery — launch settings, launch templates, conectividade, throttling, pós-lançamento com SSM, DNS e licenciamento]]

---

## 5 Domínio: Segurança e governança

### 5.1 IAM, criptografia e conformidade
- **5.1.1. Controle e auditoria**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.5. AWS Elastic Disaster Recovery/5. Segurança e governança/5.1 IAM, criptografia e conformidade/5.1.1. Controle e auditoria/5.1.1.1. Segurança do Elastic Disaster Recovery — IAM e credenciais do agente, criptografia, rede de replicação, isolamento, auditoria e conformidade|5.1.1.1. Segurança do Elastic Disaster Recovery — IAM e credenciais do agente, criptografia, rede de replicação, isolamento, auditoria e conformidade]]

---

## 6 Domínio: Operação e custos

### 6.1 Monitoramento, quotas e custos
- **6.1.1. Observabilidade e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.5. AWS Elastic Disaster Recovery/6. Operação e custos/6.1 Monitoramento, quotas e custos/6.1.1. Observabilidade e troubleshooting/6.1.1.1. Operação do Elastic Disaster Recovery — estados de replicação, lag, monitoramento, quotas, custos por servidor e staging, runbooks e checklist de produção|6.1.1.1. Operação do Elastic Disaster Recovery — estados de replicação, lag, monitoramento, quotas, custos por servidor e staging, runbooks e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.6. AWS Backup/0 AWS Backup (Tópicos )|AWS Backup]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.1. AWS Migration Hub/0 AWS Migration Hub (Tópicos )|AWS Migration Hub]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.2. AWS Database Migration Service/0 AWS Database Migration Service (Tópicos )|AWS Database Migration Service]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.5. Amazon Route 53/0 Amazon Route 53 (Tópicos )|Amazon Route 53]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.4. AWS Systems Manager/0 AWS Systems Manager (Tópicos )|AWS Systems Manager]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.1. Amazon EC2/0 Amazon EC2 (Tópicos )|Amazon EC2]]
