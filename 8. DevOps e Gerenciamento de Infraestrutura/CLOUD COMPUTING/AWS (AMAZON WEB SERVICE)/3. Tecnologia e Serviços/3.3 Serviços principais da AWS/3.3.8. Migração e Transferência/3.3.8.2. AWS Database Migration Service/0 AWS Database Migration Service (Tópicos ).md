# 📚 Guia de Estudos: AWS Database Migration Service
#tag #aws #cloud #migracao #dms #banco-de-dados #cdc #schema-conversion

> [!info] Visão Geral
> O AWS Database Migration Service (DMS) migra e replica bancos de dados com mínima indisponibilidade: copia os dados existentes (full load) e captura as mudanças contínuas (CDC) lendo o log de transações da origem. Suporta migrações homogêneas e heterogêneas (com Schema Conversion/SCT), destinos analíticos e de streaming (S3, Redshift, Kinesis, Kafka) e replicação contínua. Este guia cobre fundamentos, instâncias/serverless e endpoints, tarefas e CDC, migração heterogênea, validação e cutover, e segurança e operação.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Migração de bancos de dados gerenciada**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.2. AWS Database Migration Service/1. Fundamentos/1.1 Visão geral/1.1.1. Migração de bancos de dados gerenciada/1.1.1.1. O que é AWS Database Migration Service — migração homogênea e heterogênea, full load e CDC, arquitetura, fontes e destinos e quando usar DMS vs ferramentas nativas|1.1.1.1. O que é AWS Database Migration Service — migração homogênea e heterogênea, full load e CDC, arquitetura, fontes e destinos e quando usar DMS vs ferramentas nativas]]

---

## 2 Domínio: Componentes e endpoints

### 2.1 Instâncias, serverless e endpoints
- **2.1.1. Replication instance, DMS Serverless e endpoints**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.2. AWS Database Migration Service/2. Componentes e endpoints/2.1 Instâncias, serverless e endpoints/2.1.1. Replication instance, DMS Serverless e endpoints/2.1.1.1. Instâncias de replicação, DMS Serverless e endpoints — dimensionamento, Multi-AZ, subnet groups, atributos de conexão por motor e preparação da origem e do destino|2.1.1.1. Instâncias de replicação, DMS Serverless e endpoints — dimensionamento, Multi-AZ, subnet groups, atributos de conexão por motor e preparação da origem e do destino]]

---

## 3 Domínio: Tarefas e CDC

### 3.1 Full load, CDC e mapeamento
- **3.1.1. Tipos de tarefa, regras e settings**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.2. AWS Database Migration Service/3. Tarefas e CDC/3.1 Full load, CDC e mapeamento/3.1.1. Tipos de tarefa, regras e settings/3.1.1.1. Tarefas de replicação no DMS — full load, CDC, table mappings, regras de transformação, task settings, modos de LOB e tratamento de erros|3.1.1.1. Tarefas de replicação no DMS — full load, CDC, table mappings, regras de transformação, task settings, modos de LOB e tratamento de erros]]

---

## 4 Domínio: Migração heterogênea e conversão de schema

### 4.1 Schema Conversion e cenários
- **4.1.1. Oracle e SQL Server para PostgreSQL e destinos analíticos**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.2. AWS Database Migration Service/4. Migração heterogênea e conversão de schema/4.1 Schema Conversion e cenários/4.1.1. Oracle e SQL Server para PostgreSQL e destinos analíticos/4.1.1.1. Migração heterogênea com DMS — Schema Conversion e SCT, Oracle e SQL Server para Aurora PostgreSQL, mapeamento de tipos e destinos S3, Redshift, Kinesis e Kafka|4.1.1.1. Migração heterogênea com DMS — Schema Conversion e SCT, Oracle e SQL Server para Aurora PostgreSQL, mapeamento de tipos e destinos S3, Redshift, Kinesis e Kafka]]

---

## 5 Domínio: Validação e cutover

### 5.1 Validação, monitoramento e virada
- **5.1.1. Validação de dados, latência e cutover**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.2. AWS Database Migration Service/5. Validação e cutover/5.1 Validação, monitoramento e virada/5.1.1. Validação de dados, latência e cutover/5.1.1.1. Validação, monitoramento e cutover no DMS — data validation, métricas de latência CDC, premigration assessment, plano de virada e rollback|5.1.1.1. Validação, monitoramento e cutover no DMS — data validation, métricas de latência CDC, premigration assessment, plano de virada e rollback]]

---

## 6 Domínio: Segurança e operação

### 6.1 Acesso, rede e custo
- **6.1.1. IAM, KMS, VPC, custos e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.2. AWS Database Migration Service/6. Segurança e operação/6.1 Acesso, rede e custo/6.1.1. IAM, KMS, VPC, custos e troubleshooting/6.1.1.1. Segurança e operação do DMS — roles IAM, criptografia e SSL, rede e VPC endpoints, eventos e logs, custos, quotas e checklist de migração de banco|6.1.1.1. Segurança e operação do DMS — roles IAM, criptografia e SSL, rede e VPC endpoints, eventos e logs, custos, quotas e checklist de migração de banco]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.1. AWS Migration Hub/0 AWS Migration Hub (Tópicos )|AWS Migration Hub]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.4. AWS Glue/0 AWS Glue (Tópicos )|AWS Glue]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.2. Amazon Kinesis/0 Amazon Kinesis (Tópicos )|Amazon Kinesis]]
