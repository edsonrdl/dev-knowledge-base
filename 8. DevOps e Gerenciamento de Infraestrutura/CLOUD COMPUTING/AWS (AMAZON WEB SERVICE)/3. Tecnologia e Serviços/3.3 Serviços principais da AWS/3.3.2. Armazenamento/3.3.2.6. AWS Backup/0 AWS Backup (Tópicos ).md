# 📚 Guia de Estudos: AWS Backup
#tag #aws #cloud #armazenamento #backup #dr

> [!info] Visão Geral
> O AWS Backup centraliza e automatiza backups de vários serviços AWS com planos, cofres e pontos de recuperação, cópias entre regiões e contas, imutabilidade (Vault Lock) e auditoria. Este guia cobre os conceitos, os planos e políticas (inclusive Organizations), a proteção e conformidade, e a restauração, o monitoramento e o checklist de DR.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Backup centralizado e conceitos**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.6. AWS Backup/1. Fundamentos/1.1 Visão geral/1.1.1. Backup centralizado e conceitos/1.1.1.1. O que é AWS Backup — backup centralizado, serviços suportados, planos, cofres e pontos de recuperação|1.1.1.1. O que é AWS Backup — backup centralizado, serviços suportados, planos, cofres e pontos de recuperação]]

---

## 2 Domínio: Planos e Políticas

### 2.1 Planos de backup
- **2.1.1. Regras, lifecycle e cópias**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.6. AWS Backup/2. Planos e Políticas/2.1 Planos de backup/2.1.1. Regras, lifecycle e cópias/2.1.1.1. Planos de backup — regras, janelas, lifecycle e cold storage, cópias entre regiões e contas e políticas do Organizations|2.1.1.1. Planos de backup — regras, janelas, lifecycle e cold storage, cópias entre regiões e contas e políticas do Organizations]]

### 2.2 Backup por Serviço
- **2.2.1. EC2, bancos, S3 e arquivos**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.6. AWS Backup/2. Planos e Políticas/2.2 Backup por Serviço/2.2.1. EC2, bancos, S3 e arquivos/2.2.1.1. AWS Backup por serviço — como EC2, EBS, RDS, Aurora, DynamoDB, S3, EFS, FSx e VMware são protegidos e restaurados, backup contínuo e particularidades|2.2.1.1. AWS Backup por serviço — como EC2, EBS, RDS, Aurora, DynamoDB, S3, EFS, FSx e VMware são protegidos e restaurados, backup contínuo e particularidades]]

---

## 3 Domínio: Proteção e Conformidade

### 3.1 Imutabilidade e auditoria
- **3.1.1. Vault Lock, air-gap e Audit Manager**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.6. AWS Backup/3. Proteção e Conformidade/3.1 Imutabilidade e auditoria/3.1.1. Vault Lock, air-gap e Audit Manager/3.1.1.1. Proteção e conformidade no AWS Backup — Vault Lock, cofres logicamente isolados, KMS e Backup Audit Manager|3.1.1.1. Proteção e conformidade no AWS Backup — Vault Lock, cofres logicamente isolados, KMS e Backup Audit Manager]]

### 3.2 Governança Multi-Conta
- **3.2.1. Organizations, administrador delegado e conta de cofre**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.6. AWS Backup/3. Proteção e Conformidade/3.2 Governança Multi-Conta/3.2.1. Organizations, administrador delegado e conta de cofre/3.2.1.1. AWS Backup em organizações multi-conta — administrador delegado, políticas de backup, cópia entre contas, conta de cofre isolada e arquitetura de recuperação|3.2.1.1. AWS Backup em organizações multi-conta — administrador delegado, políticas de backup, cópia entre contas, conta de cofre isolada e arquitetura de recuperação]]

---

## 4 Domínio: Restauração e Operação

### 4.1 Restore e monitoramento
- **4.1.1. Restore testing, notificações e custo**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.6. AWS Backup/4. Restauração e Operação/4.1 Restore e monitoramento/4.1.1. Restore testing, notificações e custo/4.1.1.1. Restauração e operação do AWS Backup — restore testing, monitoramento, notificações, custo e checklist de DR|4.1.1.1. Restauração e operação do AWS Backup — restore testing, monitoramento, notificações, custo e checklist de DR]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.2. Amazon EBS/0 Amazon EBS (Tópicos )|Amazon EBS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.3. Amazon EFS/0 Amazon EFS (Tópicos )|Amazon EFS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.5. Amazon FSx/0 Amazon FSx (Tópicos )|Amazon FSx]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.1. Amazon S3/0 Amazon S3 (Tópicos )|Amazon S3]]
