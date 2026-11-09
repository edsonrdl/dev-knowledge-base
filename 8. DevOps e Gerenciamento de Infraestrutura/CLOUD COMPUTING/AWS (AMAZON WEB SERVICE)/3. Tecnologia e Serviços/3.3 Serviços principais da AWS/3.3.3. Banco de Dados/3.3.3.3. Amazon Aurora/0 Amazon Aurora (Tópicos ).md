# 📚 Guia de Estudos: Amazon Aurora
#tag #aws #cloud #banco-de-dados #aurora #relacional

> [!info] Visão Geral
> O Amazon Aurora é o banco relacional da AWS compatível com MySQL e PostgreSQL, com armazenamento distribuído em seis cópias e três AZs, até ~15 réplicas e failover rápido. Este guia cobre a arquitetura, alta disponibilidade e escala (réplicas, Serverless v2, Global Database), recursos de dados (backup contínuo, clones, Backtrack, exportação) e segurança, custo e escolha.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Arquitetura de cluster e armazenamento**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.3. Amazon Aurora/1. Fundamentos/1.1 Visão geral/1.1.1. Arquitetura de cluster e armazenamento/1.1.1.1. O que é Amazon Aurora — arquitetura de cluster, armazenamento distribuído, endpoints e diferenças para o RDS|1.1.1.1. O que é Amazon Aurora — arquitetura de cluster, armazenamento distribuído, endpoints e diferenças para o RDS]]

### 1.2 Arquitetura Interna
- **1.2.1. Volume, quórum e recuperação**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.3. Amazon Aurora/1. Fundamentos/1.2 Arquitetura Interna/1.2.1. Volume, quórum e recuperação/1.2.1.1. Arquitetura interna do Aurora — volume distribuído, quórum, redo log, recuperação de falhas, cache e Optimized Reads|1.2.1.1. Arquitetura interna do Aurora — volume distribuído, quórum, redo log, recuperação de falhas, cache e Optimized Reads]]

---

## 2 Domínio: Disponibilidade e Escala

### 2.1 Réplicas, Serverless e Global
- **2.1.1. Failover, Serverless v2 e Global Database**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.3. Amazon Aurora/2. Disponibilidade e Escala/2.1 Réplicas, Serverless e Global/2.1.1. Failover, Serverless v2 e Global Database/2.1.1.1. Alta disponibilidade e escala no Aurora — réplicas, failover, Aurora Serverless v2 e Global Database|2.1.1.1. Alta disponibilidade e escala no Aurora — réplicas, failover, Aurora Serverless v2 e Global Database]]

### 2.2 Serverless v2
- **2.2.1. ACUs, escala e custo**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.3. Amazon Aurora/2. Disponibilidade e Escala/2.2 Serverless v2/2.2.1. ACUs, escala e custo/2.2.1.1. Aurora Serverless v2 a fundo — ACUs, escala, capacidade mínima e máxima, pausa automática, custo e quando usar|2.2.1.1. Aurora Serverless v2 a fundo — ACUs, escala, capacidade mínima e máxima, pausa automática, custo e quando usar]]

### 2.3 Global Database
- **2.3.1. Replicação, switchover e failover**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.3. Amazon Aurora/2. Disponibilidade e Escala/2.3 Global Database/2.3.1. Replicação, switchover e failover/2.3.1.1. Aurora Global Database a fundo — replicação por armazenamento, switchover, failover, write forwarding, RPO e RTO|2.3.1.1. Aurora Global Database a fundo — replicação por armazenamento, switchover, failover, write forwarding, RPO e RTO]]

---

## 3 Domínio: Recursos de Dados

### 3.1 Backup, Backtrack e Clones
- **3.1.1. Backup contínuo, clonagem e backtrack**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.3. Amazon Aurora/3. Recursos de Dados/3.1 Backup, Backtrack e Clones/3.1.1. Backup contínuo, clonagem e backtrack/3.1.1.1. Backup, clones e Backtrack no Aurora — backup contínuo, PITR, clonagem rápida, snapshots e exportação|3.1.1.1. Backup, clones e Backtrack no Aurora — backup contínuo, PITR, clonagem rápida, snapshots e exportação]]

### 3.2 Integrações e Desempenho
- **3.2.1. Parallel Query, zero-ETL e ML**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.3. Amazon Aurora/3. Recursos de Dados/3.2 Integrações e Desempenho/3.2.1. Parallel Query, zero-ETL e ML/3.2.1.1. Integrações e recursos avançados do Aurora — Parallel Query, zero-ETL, Aurora ML, Limitless Database, extensões e S3|3.2.1.1. Integrações e recursos avançados do Aurora — Parallel Query, zero-ETL, Aurora ML, Limitless Database, extensões e S3]]

---

## 4 Domínio: Segurança, Custo e Escolha

### 4.1 Segurança e Custo
- **4.1.1. IAM, Data API, I-O Optimized e Aurora vs RDS**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.3. Amazon Aurora/4. Segurança, Custo e Escolha/4.1 Segurança e Custo/4.1.1. IAM, Data API, I-O Optimized e Aurora vs RDS/4.1.1.1. Segurança, custo e escolha no Aurora — IAM, Data API, Standard versus I-O Optimized e Aurora versus RDS|4.1.1.1. Segurança, custo e escolha no Aurora — IAM, Data API, Standard versus I/O-Optimized e Aurora versus RDS]]

---

## 5 Domínio: Migração e Operação

### 5.1 Migração e Upgrades
- **5.1.1. RDS e on-premises, Blue-Green e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.3. Amazon Aurora/5. Migração e Operação/5.1 Migração e Upgrades/5.1.1. RDS e on-premises, Blue-Green e troubleshooting/5.1.1.1. Migração, upgrades e operação do Aurora — de RDS e on-premises, DMS, Blue-Green, versões, manutenção e troubleshooting|5.1.1.1. Migração, upgrades e operação do Aurora — de RDS e on-premises, DMS, Blue/Green, versões, manutenção e troubleshooting]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.1. Amazon RDS/0 Amazon RDS (Tópicos )|Amazon RDS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.2. Amazon DynamoDB/0 Amazon DynamoDB (Tópicos )|Amazon DynamoDB]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.6. AWS Backup/0 AWS Backup (Tópicos )|AWS Backup]]
