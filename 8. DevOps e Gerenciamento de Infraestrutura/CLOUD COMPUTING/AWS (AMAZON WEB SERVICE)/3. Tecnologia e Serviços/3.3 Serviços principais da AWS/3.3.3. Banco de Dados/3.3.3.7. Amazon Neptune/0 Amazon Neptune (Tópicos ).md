# 📚 Guia de Estudos: Amazon Neptune
#tag #aws #cloud #banco-de-dados #neptune #grafos #gremlin #opencypher #sparql

> [!info] Visão Geral
> O Amazon Neptune é o banco de dados de grafos gerenciado da AWS, com suporte a property graph (Gremlin e openCypher) e RDF (SPARQL), armazenamento distribuído em seis cópias e até 15 réplicas. Este guia cobre fundamentos e modelagem de grafos, alta disponibilidade e escala (réplicas, Serverless, Global Database), carga de dados e integrações, Neptune ML, Neptune Analytics e GraphRAG, e segurança, backup, monitoramento e custo.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Grafos, modelos e arquitetura**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.7. Amazon Neptune/1. Fundamentos/1.1 Visão geral/1.1.1. Grafos, modelos e arquitetura/1.1.1.1. O que é Amazon Neptune — banco de dados de grafos, property graph e RDF, arquitetura de cluster, casos de uso e quando usar|1.1.1.1. O que é Amazon Neptune — banco de dados de grafos, property graph e RDF, arquitetura de cluster, casos de uso e quando usar]]

### 1.2 Modelagem e Consultas
- **1.2.1. Gremlin, openCypher e SPARQL**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.7. Amazon Neptune/1. Fundamentos/1.2 Modelagem e Consultas/1.2.1. Gremlin, openCypher e SPARQL/1.2.1.1. Modelagem de grafos e consultas no Neptune — Gremlin, openCypher e SPARQL, padrões de travessia, supernós e otimização|1.2.1.1. Modelagem de grafos e consultas no Neptune — Gremlin, openCypher e SPARQL, padrões de travessia, supernós e otimização]]

---

## 2 Domínio: Disponibilidade e Escala

### 2.1 Cluster, Serverless e Global
- **2.1.1. Réplicas, failover, NCUs e Global Database**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.7. Amazon Neptune/2. Disponibilidade e Escala/2.1 Cluster, Serverless e Global/2.1.1. Réplicas, failover, NCUs e Global Database/2.1.1.1. Alta disponibilidade e escala no Neptune — réplicas, failover, endpoints, Neptune Serverless e Global Database|2.1.1.1. Alta disponibilidade e escala no Neptune — réplicas, failover, endpoints, Neptune Serverless e Global Database]]

---

## 3 Domínio: Dados e Inteligência

### 3.1 Carga e Integração
- **3.1.1. Bulk loader, Streams e exportação**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.7. Amazon Neptune/3. Dados e Inteligência/3.1 Carga e Integração/3.1.1. Bulk loader, Streams e exportação/3.1.1.1. Carga de dados e integrações do Neptune — bulk loader, formatos CSV e RDF, Neptune Streams, exportação, notebooks e Graph-Explorer|3.1.1.1. Carga de dados e integrações do Neptune — bulk loader, formatos CSV e RDF, Neptune Streams, exportação, notebooks e Graph-Explorer]]

### 3.2 Neptune ML e Analytics
- **3.2.1. GNN, algoritmos, vetores e GraphRAG**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.7. Amazon Neptune/3. Dados e Inteligência/3.2 Neptune ML e Analytics/3.2.1. GNN, algoritmos, vetores e GraphRAG/3.2.1.1. Neptune ML e Neptune Analytics — redes neurais de grafos, algoritmos de grafos, busca vetorial e GraphRAG com IA generativa|3.2.1.1. Neptune ML e Neptune Analytics — redes neurais de grafos, algoritmos de grafos, busca vetorial e GraphRAG com IA generativa]]

---

## 4 Domínio: Segurança e Operação

### 4.1 Segurança, Backup, Monitoramento e Custo
- **4.1.1. IAM SigV4, snapshots, métricas e preços**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.7. Amazon Neptune/4. Segurança e Operação/4.1 Segurança, Backup, Monitoramento e Custo/4.1.1. IAM SigV4, snapshots, métricas e preços/4.1.1.1. Segurança, backup, monitoramento e custo no Neptune — VPC, IAM SigV4, KMS, snapshots, métricas, logs de consultas lentas e dimensionamento|4.1.1.1. Segurança, backup, monitoramento e custo no Neptune — VPC, IAM SigV4, KMS, snapshots, métricas, logs de consultas lentas e dimensionamento]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.3. Amazon Aurora/0 Amazon Aurora (Tópicos )|Amazon Aurora]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.6. Amazon DocumentDB/0 Amazon DocumentDB (Tópicos )|Amazon DocumentDB]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.2. Amazon DynamoDB/0 Amazon DynamoDB (Tópicos )|Amazon DynamoDB]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.5. Amazon Redshift/0 Amazon Redshift (Tópicos )|Amazon Redshift]]
