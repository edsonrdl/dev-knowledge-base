# 📚 Guia de Estudos: Amazon Redshift
#tag #aws #cloud #banco-de-dados #redshift #datawarehouse #olap

> [!info] Visão Geral
> O Amazon Redshift é o data warehouse gerenciado da AWS: colunar, MPP, compatível com SQL PostgreSQL, em clusters provisionados (RA3) ou Serverless. Este guia cobre fundamentos e modelagem (distribution e sort keys), carga e desempenho (COPY, WLM, tuning), Redshift Serverless, integrações (Spectrum, data sharing, zero-ETL, ML), segurança e governança, e operação e custo.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Data warehouse colunar e MPP**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.5. Amazon Redshift/1. Fundamentos/1.1 Visão geral/1.1.1. Data warehouse colunar e MPP/1.1.1.1. O que é Amazon Redshift — data warehouse colunar MPP, leader e compute nodes, RA3, provisionado e serverless, e quando usar|1.1.1.1. O que é Amazon Redshift — data warehouse colunar MPP, leader e compute nodes, RA3, provisionado e serverless, e quando usar]]

### 1.2 Modelagem
- **1.2.1. Colunar, distribution e sort keys**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.5. Amazon Redshift/1. Fundamentos/1.2 Modelagem/1.2.1. Colunar, distribution e sort keys/1.2.1.1. Modelagem no Redshift — armazenamento colunar, compressão, distribution styles, sort keys e esquema estrela|1.2.1.1. Modelagem no Redshift — armazenamento colunar, compressão, distribution styles, sort keys e esquema estrela]]

---

## 2 Domínio: Consultas e Capacidade

### 2.1 Carga, consulta e desempenho
- **2.1.1. COPY, WLM, caches e tuning**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.5. Amazon Redshift/2. Consultas e Capacidade/2.1 Carga, consulta e desempenho/2.1.1. COPY, WLM, caches e tuning/2.1.1.1. Carga, consulta e desempenho no Redshift — COPY e UNLOAD, WLM, concurrency scaling, caches, views materializadas e tuning|2.1.1.1. Carga, consulta e desempenho no Redshift — COPY e UNLOAD, WLM, concurrency scaling, caches, views materializadas e tuning]]

### 2.2 Redshift Serverless
- **2.2.1. RPUs, workgroups e custo**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.5. Amazon Redshift/2. Consultas e Capacidade/2.2 Redshift Serverless/2.2.1. RPUs, workgroups e custo/2.2.1.1. Redshift Serverless — RPUs, namespaces e workgroups, capacidade base, limites de uso e custo|2.2.1.1. Redshift Serverless — RPUs, namespaces e workgroups, capacidade base, limites de uso e custo]]

---

## 3 Domínio: Integrações

### 3.1 Data lake e integrações
- **3.1.1. Spectrum, data sharing, zero-ETL e ML**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.5. Amazon Redshift/3. Integrações/3.1 Data lake e integrações/3.1.1. Spectrum, data sharing, zero-ETL e ML/3.1.1.1. Integrações do Redshift — Spectrum, consultas federadas, data sharing, zero-ETL, streaming, Redshift ML e Data API|3.1.1.1. Integrações do Redshift — Spectrum, consultas federadas, data sharing, zero-ETL, streaming, Redshift ML e Data API]]

---

## 4 Domínio: Segurança e Operação

### 4.1 Segurança e Governança
- **4.1.1. Criptografia, RBAC e mascaramento**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.5. Amazon Redshift/4. Segurança e Operação/4.1 Segurança e Governança/4.1.1. Criptografia, RBAC e mascaramento/4.1.1.1. Segurança e governança no Redshift — VPC, criptografia, IAM, RBAC, segurança em nível de linha e coluna, mascaramento e auditoria|4.1.1.1. Segurança e governança no Redshift — VPC, criptografia, IAM, RBAC, segurança em nível de linha e coluna, mascaramento e auditoria]]

### 4.2 Operação e Custo
- **4.2.1. Snapshots, resize, pausa e reservas**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.5. Amazon Redshift/4. Segurança e Operação/4.2 Operação e Custo/4.2.1. Snapshots, resize, pausa e reservas/4.2.1.1. Operação e custo do Redshift — snapshots, resize, pausa e retomada, Reserved Nodes, monitoramento e rightsizing|4.2.1.1. Operação e custo do Redshift — snapshots, resize, pausa e retomada, Reserved Nodes, monitoramento e rightsizing]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.1. Amazon RDS/0 Amazon RDS (Tópicos )|Amazon RDS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.3. Amazon Aurora/0 Amazon Aurora (Tópicos )|Amazon Aurora]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.1. Amazon S3/0 Amazon S3 (Tópicos )|Amazon S3]]
