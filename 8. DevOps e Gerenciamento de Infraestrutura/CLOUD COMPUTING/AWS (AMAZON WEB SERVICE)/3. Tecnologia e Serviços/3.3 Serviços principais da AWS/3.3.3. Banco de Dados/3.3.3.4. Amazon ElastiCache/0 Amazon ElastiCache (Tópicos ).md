# 📚 Guia de Estudos: Amazon ElastiCache
#tag #aws #cloud #banco-de-dados #elasticache #cache #valkey #redis #memcached

> [!info] Visão Geral
> O Amazon ElastiCache é o serviço gerenciado de armazenamento em memória da AWS, com os engines Valkey, Redis OSS e Memcached, usado como cache, para sessões, rankings, filas leves e contadores. Este guia cobre fundamentos e estratégias de cache, Valkey/Redis OSS na prática e em topologias de alta disponibilidade, Memcached, segurança, backup, operação, custo e dimensionamento.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Cache, engines e casos de uso**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.4. Amazon ElastiCache/1. Fundamentos/1.1 Visão geral/1.1.1. Cache, engines e casos de uso/1.1.1.1. O que é Amazon ElastiCache — caching em memória, engines Valkey, Redis OSS e Memcached, nós, clusters, serverless e casos de uso|1.1.1.1. O que é Amazon ElastiCache — caching em memória, engines Valkey, Redis OSS e Memcached, nós, clusters, serverless e casos de uso]]

### 1.2 Estratégias de Cache
- **1.2.1. Cache-aside, write-through e invalidação**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.4. Amazon ElastiCache/1. Fundamentos/1.2 Estratégias de Cache/1.2.1. Cache-aside, write-through e invalidação/1.2.1.1. Estratégias de cache — cache-aside, read-through, write-through, write-behind, TTL, invalidação, cache stampede e padrões de projeto|1.2.1.1. Estratégias de cache — cache-aside, read-through, write-through, write-behind, TTL, invalidação, cache stampede e padrões de projeto]]

---

## 2 Domínio: Valkey e Redis OSS

### 2.1 Estruturas e Padrões
- **2.1.1. Tipos de dados e padrões de uso**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.4. Amazon ElastiCache/2. Valkey e Redis OSS/2.1 Estruturas e Padrões/2.1.1. Tipos de dados e padrões de uso/2.1.1.1. Valkey e Redis OSS em prática — estruturas de dados, comandos, pub-sub, streams, locks, rate limiting, leaderboards e sessões|2.1.1.1. Valkey e Redis OSS em prática — estruturas de dados, comandos, pub/sub, streams, locks, rate limiting, leaderboards e sessões]]

### 2.2 Topologias e Alta Disponibilidade
- **2.2.1. Replicação, cluster mode e Global Datastore**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.4. Amazon ElastiCache/2. Valkey e Redis OSS/2.2 Topologias e Alta Disponibilidade/2.2.1. Replicação, cluster mode e Global Datastore/2.2.1.1. Topologias do Valkey e Redis OSS no ElastiCache — replication groups, cluster mode, sharding, Multi-AZ, failover, Global Datastore e escala|2.2.1.1. Topologias do Valkey e Redis OSS no ElastiCache — replication groups, cluster mode, sharding, Multi-AZ, failover, Global Datastore e escala]]

---

## 3 Domínio: Memcached

### 3.1 Memcached
- **3.1.1. Modelo e escala horizontal**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.4. Amazon ElastiCache/3. Memcached/3.1 Memcached/3.1.1. Modelo e escala horizontal/3.1.1.1. Memcached no ElastiCache — modelo multithread, sharding no cliente, auto discovery, escala horizontal e quando escolher|3.1.1.1. Memcached no ElastiCache — modelo multithread, sharding no cliente, auto discovery, escala horizontal e quando escolher]]

---

## 4 Domínio: Operação e Custo

### 4.1 Segurança e Operação
- **4.1.1. Rede, criptografia, backups e métricas**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.4. Amazon ElastiCache/4. Operação e Custo/4.1 Segurança e Operação/4.1.1. Rede, criptografia, backups e métricas/4.1.1.1. Segurança, backup e operação do ElastiCache — VPC, TLS, AUTH, RBAC e IAM, snapshots, parameter groups, métricas e troubleshooting|4.1.1.1. Segurança, backup e operação do ElastiCache — VPC, TLS, AUTH, RBAC e IAM, snapshots, parameter groups, métricas e troubleshooting]]

### 4.2 Custo e Dimensionamento
- **4.2.1. Serverless, nós reservados e eviction**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.4. Amazon ElastiCache/4. Operação e Custo/4.2 Custo e Dimensionamento/4.2.1. Serverless, nós reservados e eviction/4.2.1.1. Custo e dimensionamento do ElastiCache — Serverless contra nós, data tiering, políticas de eviction, Reserved Nodes e rightsizing|4.2.1.1. Custo e dimensionamento do ElastiCache — Serverless contra nós, data tiering, políticas de eviction, Reserved Nodes e rightsizing]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.1. Amazon RDS/0 Amazon RDS (Tópicos )|Amazon RDS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.2. Amazon DynamoDB/0 Amazon DynamoDB (Tópicos )|Amazon DynamoDB]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.3. Amazon Aurora/0 Amazon Aurora (Tópicos )|Amazon Aurora]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.1. Amazon VPC/0 Amazon VPC (Tópicos )|Amazon VPC]]
