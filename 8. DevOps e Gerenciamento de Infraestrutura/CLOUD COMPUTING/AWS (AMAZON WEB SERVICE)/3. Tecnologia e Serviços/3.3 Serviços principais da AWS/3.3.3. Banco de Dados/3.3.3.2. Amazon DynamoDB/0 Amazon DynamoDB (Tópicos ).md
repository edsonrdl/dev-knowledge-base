# 📚 Guia de Estudos: Amazon DynamoDB
#tag #aws #cloud #banco-de-dados #dynamodb #nosql

> [!info] Visão Geral
> O Amazon DynamoDB é o banco NoSQL chave-valor e de documentos, serverless e de latência de milissegundos da AWS. Este guia cobre fundamentos (tabelas, itens, chaves), modelagem por access patterns (GSI/LSI, Query, transações), capacidade e desempenho (on-demand, provisioned, hot partitions, DAX, TTL) e proteção e integração (PITR, Global Tables, Streams, segurança).

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Tabelas, itens e chaves**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.2. Amazon DynamoDB/1. Fundamentos/1.1 Visão geral/1.1.1. Tabelas, itens e chaves/1.1.1.1. O que é Amazon DynamoDB — banco NoSQL serverless, tabelas, itens, partition key e sort key|1.1.1.1. O que é Amazon DynamoDB — banco NoSQL serverless, tabelas, itens, partition key e sort key]]

### 1.2 Armazenamento e Limites
- **1.2.1. Partições, limites e itens grandes**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.2. Amazon DynamoDB/1. Fundamentos/1.2 Armazenamento e Limites/1.2.1. Partições, limites e itens grandes/1.2.1.1. Armazenamento e limites do DynamoDB — estrutura de partições, quotas, itens grandes, compressão, import e export com S3|1.2.1.1. Armazenamento e limites do DynamoDB — estrutura de partições, quotas, itens grandes, compressão, import e export com S3]]

---

## 2 Domínio: Modelagem e Acesso

### 2.1 Modelagem
- **2.1.1. Access patterns, índices e transações**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.2. Amazon DynamoDB/2. Modelagem e Acesso/2.1 Modelagem/2.1.1. Access patterns, índices e transações/2.1.1.1. Modelagem no DynamoDB — access patterns, GSI e LSI, Query versus Scan, expressões e transações|2.1.1.1. Modelagem no DynamoDB — access patterns, GSI e LSI, Query versus Scan, expressões e transações]]

### 2.2 Consistência e Padrões
- **2.2.1. Concorrência, idempotência e padrões**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.2. Amazon DynamoDB/2. Modelagem e Acesso/2.2 Consistência e Padrões/2.2.1. Concorrência, idempotência e padrões/2.2.1.1. Consistência, concorrência e padrões avançados de modelagem no DynamoDB — locking otimista, idempotência, adjacency list, GSI overloading, versionamento e séries temporais|2.2.1.1. Consistência, concorrência e padrões avançados de modelagem no DynamoDB — locking otimista, idempotência, adjacency list, GSI overloading, versionamento e séries temporais]]

---

## 3 Domínio: Capacidade e Desempenho

### 3.1 Capacidade
- **3.1.1. RCU, WCU, on-demand, DAX e TTL**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.2. Amazon DynamoDB/3. Capacidade e Desempenho/3.1 Capacidade/3.1.1. RCU, WCU, on-demand, DAX e TTL/3.1.1.1. Capacidade e desempenho do DynamoDB — on-demand e provisioned, RCU e WCU, hot partitions, DAX, TTL e table classes|3.1.1.1. Capacidade e desempenho do DynamoDB — on-demand e provisioned, RCU e WCU, hot partitions, DAX, TTL e table classes]]

### 3.2 Escala e Partições
- **3.2.1. Partições, adaptive capacity e auto scaling**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.2. Amazon DynamoDB/3. Capacidade e Desempenho/3.2 Escala e Partições/3.2.1. Partições, adaptive capacity e auto scaling/3.2.1.1. Escala do DynamoDB em profundidade — divisão de partições, adaptive capacity, auto scaling, limites do on-demand e estratégias contra hot keys|3.2.1.1. Escala do DynamoDB em profundidade — divisão de partições, adaptive capacity, auto scaling, limites do on-demand e estratégias contra hot keys]]

---

## 4 Domínio: Proteção e Integração

### 4.1 Backup, Streams e Segurança
- **4.1.1. PITR, Global Tables, Streams e IAM**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.2. Amazon DynamoDB/4. Proteção e Integração/4.1 Backup, Streams e Segurança/4.1.1. PITR, Global Tables, Streams e IAM/4.1.1.1. Backup, replicação e segurança no DynamoDB — PITR, Global Tables, Streams, criptografia e IAM|4.1.1.1. Backup, replicação e segurança no DynamoDB — PITR, Global Tables, Streams, criptografia e IAM]]

### 4.2 Streams e Eventos
- **4.2.1. Lambda, Kinesis e Pipes**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.2. Amazon DynamoDB/4. Proteção e Integração/4.2 Streams e Eventos/4.2.1. Lambda, Kinesis e Pipes/4.2.1.1. DynamoDB Streams a fundo — view types, Lambda event source mapping, filtros, tratamento de erros, Kinesis Data Streams for DynamoDB e EventBridge Pipes|4.2.1.1. DynamoDB Streams a fundo — view types, Lambda event source mapping, filtros, tratamento de erros, Kinesis Data Streams for DynamoDB e EventBridge Pipes]]

### 4.3 Global Tables
- **4.3.1. Replicação multirregião**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.2. Amazon DynamoDB/4. Proteção e Integração/4.3 Global Tables/4.3.1. Replicação multirregião/4.3.1.1. Global Tables em profundidade — MREC e MRSC, resolução de conflitos, failover, requisitos, custos e arquiteturas|4.3.1.1. Global Tables em profundidade — MREC e MRSC, resolução de conflitos, failover, requisitos, custos e arquiteturas]]

### 4.4 Proteção e Recuperação
- **4.4.1. Backups, PITR e restauração**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.2. Amazon DynamoDB/4. Proteção e Integração/4.4 Proteção e Recuperação/4.4.1. Backups, PITR e restauração/4.4.1.1. Proteção e recuperação no DynamoDB — backups on-demand, PITR, AWS Backup, deletion protection, restauração e checklist de DR|4.4.1.1. Proteção e recuperação no DynamoDB — backups on-demand, PITR, AWS Backup, deletion protection, restauração e checklist de DR]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.1. Amazon RDS/0 Amazon RDS (Tópicos )|Amazon RDS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.6. AWS Backup/0 AWS Backup (Tópicos )|AWS Backup]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.5. Amazon Route 53/0 Amazon Route 53 (Tópicos )|Amazon Route 53]]
