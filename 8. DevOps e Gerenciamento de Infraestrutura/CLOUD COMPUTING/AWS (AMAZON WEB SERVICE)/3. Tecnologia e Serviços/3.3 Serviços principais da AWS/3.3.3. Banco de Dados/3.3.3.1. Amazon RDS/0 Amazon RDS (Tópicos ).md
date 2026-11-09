# 📚 Guia de Estudos: Amazon RDS
#tag #aws #cloud #banco-de-dados #rds #relacional

> [!info] Visão Geral
> O Amazon RDS é o serviço de banco de dados relacional gerenciado da AWS (MySQL, PostgreSQL, MariaDB, Oracle, SQL Server e Db2). Este guia cobre fundamentos (engines, classes, armazenamento, parameter groups), alta disponibilidade e escala (Multi-AZ, read replicas, RDS Proxy), backup e operação (PITR, snapshots, manutenção, Blue/Green, monitoramento) e segurança (rede, KMS, TLS, IAM auth, Secrets Manager).

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Engines, instâncias e armazenamento**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.1. Amazon RDS/1. Fundamentos/1.1 Visão geral/1.1.1. Engines, instâncias e armazenamento/1.1.1.1. O que é Amazon RDS — engines, classes de instância, armazenamento, subnet groups e parameter groups|1.1.1.1. O que é Amazon RDS — engines, classes de instância, armazenamento, subnet groups e parameter groups]]

### 1.2 Engines em Detalhe
- **1.2.1. MySQL, PostgreSQL, Oracle, SQL Server e Db2**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.1. Amazon RDS/1. Fundamentos/1.2 Engines em Detalhe/1.2.1. MySQL, PostgreSQL, Oracle, SQL Server e Db2/1.2.1.1. Engines do RDS em detalhe — MySQL, MariaDB, PostgreSQL, Oracle, SQL Server e Db2, licenciamento, RDS Custom e limitações|1.2.1.1. Engines do RDS em detalhe — MySQL, MariaDB, PostgreSQL, Oracle, SQL Server e Db2, licenciamento, RDS Custom e limitações]]

### 1.3 Configuração e Tuning
- **1.3.1. Parameter groups, option groups e tuning**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.1. Amazon RDS/1. Fundamentos/1.3 Configuração e Tuning/1.3.1. Parameter groups, option groups e tuning/1.3.1.1. Parameter groups, option groups e tuning de engines no RDS — parâmetros dinâmicos e estáticos, conexões, memória, logs e boas práticas|1.3.1.1. Parameter groups, option groups e tuning de engines no RDS — parâmetros dinâmicos e estáticos, conexões, memória, logs e boas práticas]]

---

## 2 Domínio: Alta Disponibilidade e Escala

### 2.1 Multi-AZ e Réplicas
- **2.1.1. Multi-AZ, read replicas e RDS Proxy**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.1. Amazon RDS/2. Alta Disponibilidade e Escala/2.1 Multi-AZ e Réplicas/2.1.1. Multi-AZ, read replicas e RDS Proxy/2.1.1.1. Multi-AZ, read replicas e RDS Proxy — alta disponibilidade, escala de leitura e pool de conexões|2.1.1.1. Multi-AZ, read replicas e RDS Proxy — alta disponibilidade, escala de leitura e pool de conexões]]

---

## 3 Domínio: Backup e Operação

### 3.1 Backup e Manutenção
- **3.1.1. Snapshots, PITR, monitoramento e Blue-Green**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.1. Amazon RDS/3. Backup e Operação/3.1 Backup e Manutenção/3.1.1. Snapshots, PITR, monitoramento e Blue-Green/3.1.1.1. Backups, snapshots e PITR no RDS — retenção, restauração, manutenção, monitoramento e Blue-Green deployments|3.1.1.1. Backups, snapshots e PITR no RDS — retenção, restauração, manutenção, monitoramento e Blue/Green deployments]]

### 3.2 Diagnóstico e Desempenho
- **3.2.1. Performance Insights, logs e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.1. Amazon RDS/3. Backup e Operação/3.2 Diagnóstico e Desempenho/3.2.1. Performance Insights, logs e troubleshooting/3.2.1.1. Diagnóstico de desempenho no RDS — Performance Insights, Enhanced Monitoring, slow logs, wait events e troubleshooting|3.2.1.1. Diagnóstico de desempenho no RDS — Performance Insights, Enhanced Monitoring, slow logs, wait events e troubleshooting]]

---

## 4 Domínio: Segurança

### 4.1 Proteção
- **4.1.1. Rede, KMS, IAM e Secrets Manager**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.1. Amazon RDS/4. Segurança/4.1 Proteção/4.1.1. Rede, KMS, IAM e Secrets Manager/4.1.1.1. Segurança do RDS — rede, criptografia KMS, SSL-TLS, IAM database authentication e Secrets Manager|4.1.1.1. Segurança do RDS — rede, criptografia KMS, SSL/TLS, IAM database authentication e Secrets Manager]]

---

## 5 Domínio: Migração e Custo

### 5.1 Migração
- **5.1.1. DMS, dump, replicação nativa e cutover**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.1. Amazon RDS/5. Migração e Custo/5.1 Migração/5.1.1. DMS, dump, replicação nativa e cutover/5.1.1.1. Migração para o RDS — DMS e SCT, dump e restore, replicação nativa, backup nativo do SQL Server e estratégias de cutover|5.1.1.1. Migração para o RDS — DMS e SCT, dump e restore, replicação nativa, backup nativo do SQL Server e estratégias de cutover]]

### 5.2 Custo e Dimensionamento
- **5.2.1. Reservas, rightsizing e FinOps**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.1. Amazon RDS/5. Migração e Custo/5.2 Custo e Dimensionamento/5.2.1. Reservas, rightsizing e FinOps/5.2.1.1. Custo e dimensionamento do RDS — modelos de cobrança, Reserved Instances, rightsizing, armazenamento e checklist FinOps|5.2.1.1. Custo e dimensionamento do RDS — modelos de cobrança, Reserved Instances, rightsizing, armazenamento e checklist FinOps]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.1. Amazon VPC/0 Amazon VPC (Tópicos )|Amazon VPC]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.2. Amazon EBS/0 Amazon EBS (Tópicos )|Amazon EBS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.6. AWS Backup/0 AWS Backup (Tópicos )|AWS Backup]]
