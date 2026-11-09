# 📚 Guia de Estudos: Amazon DocumentDB
#tag #aws #cloud #banco-de-dados #documentdb #nosql #mongodb

> [!info] Visão Geral
> O Amazon DocumentDB (com compatibilidade com o MongoDB) é o banco de documentos gerenciado da AWS, com API compatível com o MongoDB sobre um armazenamento distribuído de seis cópias em três AZs. Este guia cobre fundamentos e modelagem de documentos, alta disponibilidade e escala (réplicas, Global Clusters, Elastic Clusters, Serverless), backup e migração, e segurança, monitoramento e custo.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Documentos, compatibilidade e arquitetura**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.6. Amazon DocumentDB/1. Fundamentos/1.1 Visão geral/1.1.1. Documentos, compatibilidade e arquitetura/1.1.1.1. O que é Amazon DocumentDB — banco de documentos compatível com MongoDB, arquitetura de cluster, versões, limitações e quando usar|1.1.1.1. O que é Amazon DocumentDB — banco de documentos compatível com MongoDB, arquitetura de cluster, versões, limitações e quando usar]]

### 1.2 Modelagem e Operações
- **1.2.1. CRUD, índices, agregações e change streams**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.6. Amazon DocumentDB/1. Fundamentos/1.2 Modelagem e Operações/1.2.1. CRUD, índices, agregações e change streams/1.2.1.1. Modelagem e operações no DocumentDB — embutir ou referenciar, índices, agregações, change streams, TTL, transações e busca vetorial|1.2.1.1. Modelagem e operações no DocumentDB — embutir ou referenciar, índices, agregações, change streams, TTL, transações e busca vetorial]]

---

## 2 Domínio: Disponibilidade e Escala

### 2.1 Clusters baseados em instâncias
- **2.1.1. Réplicas, failover e Global Clusters**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.6. Amazon DocumentDB/2. Disponibilidade e Escala/2.1 Clusters baseados em instâncias/2.1.1. Réplicas, failover e Global Clusters/2.1.1.1. Alta disponibilidade e escala no DocumentDB — réplicas, failover, read preference, tipos de instância, I-O Optimized e Global Clusters|2.1.1.1. Alta disponibilidade e escala no DocumentDB — réplicas, failover, read preference, tipos de instância, I/O-Optimized e Global Clusters]]

### 2.2 Elastic Clusters e Serverless
- **2.2.1. Sharding e capacidade sob demanda**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.6. Amazon DocumentDB/2. Disponibilidade e Escala/2.2 Elastic Clusters e Serverless/2.2.1. Sharding e capacidade sob demanda/2.2.1.1. Elastic Clusters e Serverless no DocumentDB — sharding, shard key, capacidade por shard, limites e quando usar|2.2.1.1. Elastic Clusters e Serverless no DocumentDB — sharding, shard key, capacidade por shard, limites e quando usar]]

---

## 3 Domínio: Dados e Migração

### 3.1 Backup e Migração
- **3.1.1. PITR, snapshots, DMS e mongodump**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.6. Amazon DocumentDB/3. Dados e Migração/3.1 Backup e Migração/3.1.1. PITR, snapshots, DMS e mongodump/3.1.1.1. Backup, restauração e migração para o DocumentDB — PITR, snapshots, clonagem, DMS, mongodump e mongorestore, e estratégia de cutover|3.1.1.1. Backup, restauração e migração para o DocumentDB — PITR, snapshots, clonagem, DMS, mongodump e mongorestore, e estratégia de cutover]]

---

## 4 Domínio: Segurança, Operação e Custo

### 4.1 Segurança, Monitoramento e Custo
- **4.1.1. TLS, IAM, auditoria, métricas e preços**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.6. Amazon DocumentDB/4. Segurança, Operação e Custo/4.1 Segurança, Monitoramento e Custo/4.1.1. TLS, IAM, auditoria, métricas e preços/4.1.1.1. Segurança, monitoramento e custo no DocumentDB — VPC, TLS, KMS, RBAC e IAM, auditoria, profiler, métricas e dimensionamento de custos|4.1.1.1. Segurança, monitoramento e custo no DocumentDB — VPC, TLS, KMS, RBAC e IAM, auditoria, profiler, métricas e dimensionamento de custos]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.2. Amazon DynamoDB/0 Amazon DynamoDB (Tópicos )|Amazon DynamoDB]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.3. Amazon Aurora/0 Amazon Aurora (Tópicos )|Amazon Aurora]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.1. Amazon RDS/0 Amazon RDS (Tópicos )|Amazon RDS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.4. Amazon ElastiCache/0 Amazon ElastiCache (Tópicos )|Amazon ElastiCache]]
