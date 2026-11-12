# 📚 Guia de Estudos: Amazon EMR
#tag #aws #cloud #analytics #emr #spark #hadoop #bigdata

> [!info] Visão Geral
> O Amazon EMR é a plataforma gerenciada de big data da AWS para executar Spark, Hadoop, Hive, Trino, Flink, HBase e formatos de tabela abertos (Iceberg, Hudi, Delta) com dados no S3, em três modos: EMR on EC2, EMR on EKS e EMR Serverless. Este guia cobre fundamentos, modos de implantação, processamento e dados, escala e custos, segurança (roles, criptografia, Lake Formation) e operação (logs, métricas, quotas, runbooks).

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Big data gerenciado**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.5. Amazon EMR/1. Fundamentos/1.1 Visão geral/1.1.1. Big data gerenciado/1.1.1.1. O que é Amazon EMR — big data gerenciado com Hadoop e Spark, clusters, nós primary, core e task, frameworks suportados e quando usar EMR em vez de Glue, Athena e Redshift|1.1.1.1. O que é Amazon EMR — big data gerenciado com Hadoop e Spark, clusters, nós primary, core e task, frameworks suportados e quando usar EMR em vez de Glue, Athena e Redshift]]

---

## 2 Domínio: Arquitetura e implantação

### 2.1 EC2, EKS e Serverless
- **2.1.1. Modos de implantação**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.5. Amazon EMR/2. Arquitetura e implantação/2.1 EC2, EKS e Serverless/2.1.1. Modos de implantação/2.1.1.1. Modos de implantação do EMR — EMR on EC2, EMR on EKS e EMR Serverless, instance groups e fleets, clusters transitórios e de longa duração e quando usar cada um|2.1.1.1. Modos de implantação do EMR — EMR on EC2, EMR on EKS e EMR Serverless, instance groups e fleets, clusters transitórios e de longa duração e quando usar cada um]]

---

## 3 Domínio: Processamento e dados

### 3.1 Spark, Hadoop, EMRFS e S3
- **3.1.1. Frameworks e armazenamento**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.5. Amazon EMR/3. Processamento e dados/3.1 Spark, Hadoop, EMRFS e S3/3.1.1. Frameworks e armazenamento/3.1.1.1. Processamento e dados no EMR — Spark, Hive, Trino, Flink, formatos Parquet e Iceberg, S3 e EMRFS, HDFS, Glue Data Catalog, steps e boas práticas de desempenho|3.1.1.1. Processamento e dados no EMR — Spark, Hive, Trino, Flink, formatos Parquet e Iceberg, S3 e EMRFS, HDFS, Glue Data Catalog, steps e boas práticas de desempenho]]

---

## 4 Domínio: Escalabilidade e custos

### 4.1 Managed scaling, Spot e frotas
- **4.1.1. Dimensionamento e economia**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.5. Amazon EMR/4. Escalabilidade e custos/4.1 Managed scaling, Spot e frotas/4.1.1. Dimensionamento e economia/4.1.1.1. Escala e custos no EMR — managed scaling, auto scaling, Spot e Instance Fleets, Graviton, dimensionamento de executors, auto-terminação e modelo de preços|4.1.1.1. Escala e custos no EMR — managed scaling, auto scaling, Spot e Instance Fleets, Graviton, dimensionamento de executors, auto-terminação e modelo de preços]]

---

## 5 Domínio: Segurança e governança

### 5.1 IAM, Kerberos, criptografia e Lake Formation
- **5.1.1. Controle e conformidade**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.5. Amazon EMR/5. Segurança e governança/5.1 IAM, Kerberos, criptografia e Lake Formation/5.1.1. Controle e conformidade/5.1.1.1. Segurança do EMR — roles de serviço e de instância, security configurations, criptografia, Kerberos, Lake Formation, runtime roles, rede e Block Public Access|5.1.1.1. Segurança do EMR — roles de serviço e de instância, security configurations, criptografia, Kerberos, Lake Formation, runtime roles, rede e Block Public Access]]

---

## 6 Domínio: Operação e troubleshooting

### 6.1 Monitoramento, logs e quotas
- **6.1.1. Observabilidade e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.5. Amazon EMR/6. Operação e troubleshooting/6.1 Monitoramento, logs e quotas/6.1.1. Observabilidade e troubleshooting/6.1.1.1. Operação do EMR — logs e UIs, métricas do CloudWatch, EMR Studio, troubleshooting de jobs e clusters, quotas e checklist de produção|6.1.1.1. Operação do EMR — logs e UIs, métricas do CloudWatch, EMR Studio, troubleshooting de jobs e clusters, quotas e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.4. AWS Glue/0 AWS Glue (Tópicos )|AWS Glue]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.1. Amazon Athena/0 Amazon Athena (Tópicos )|Amazon Athena]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.1. Amazon S3/0 Amazon S3 (Tópicos )|Amazon S3]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.5. Amazon Redshift/0 Amazon Redshift (Tópicos )|Amazon Redshift]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.4. Amazon EKS/0 Amazon EKS (Tópicos )|Amazon EKS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.4. AWS Systems Manager/0 AWS Systems Manager (Tópicos )|AWS Systems Manager]]
