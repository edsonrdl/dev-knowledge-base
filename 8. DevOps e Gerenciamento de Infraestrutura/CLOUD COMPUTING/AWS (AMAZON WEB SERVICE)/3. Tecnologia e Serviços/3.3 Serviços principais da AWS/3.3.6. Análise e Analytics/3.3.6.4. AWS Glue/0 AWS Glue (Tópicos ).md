# 📚 Guia de Estudos: AWS Glue
#tag #aws #cloud #analytics #glue #etl #data-catalog #data-lake

> [!info] Visão Geral
> O AWS Glue é o serviço de integração de dados serverless da AWS: descobre, cataloga, transforma e move dados entre fontes e destinos, sem administrar servidores, com cobrança por DPU-hora. Este guia cobre os fundamentos (componentes, DPUs e comparação com EMR, Athena e Lambda), o Data Catalog e os crawlers, os jobs de ETL (Spark, DynamicFrames, bookmarks, streaming), a orquestração e qualidade (workflows, DataBrew, Data Quality, PII), o desempenho e custo (tuning de Spark, Flex, Iceberg) e a segurança e operação (IAM, VPC, Lake Formation, CI/CD, troubleshooting).

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. ETL serverless e integração de dados**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.4. AWS Glue/1. Fundamentos/1.1 Visão geral/1.1.1. ETL serverless e integração de dados/1.1.1.1. O que é AWS Glue — ETL serverless, componentes, DPUs, arquitetura de data lake e quando usar em vez de EMR, Athena ou Lambda|1.1.1.1. O que é AWS Glue — ETL serverless, componentes, DPUs, arquitetura de data lake e quando usar em vez de EMR, Athena ou Lambda]]

---

## 2 Domínio: Data Catalog e crawlers

### 2.1 Metadados e descoberta
- **2.1.1. Catálogo, crawlers, classifiers e Schema Registry**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.4. AWS Glue/2. Data Catalog e crawlers/2.1 Metadados e descoberta/2.1.1. Catálogo, crawlers, classifiers e Schema Registry/2.1.1.1. Glue Data Catalog e crawlers — bancos, tabelas, partições, classifiers, evolução de esquema, connections, Schema Registry e estatísticas de colunas|2.1.1.1. Glue Data Catalog e crawlers — bancos, tabelas, partições, classifiers, evolução de esquema, connections, Schema Registry e estatísticas de colunas]]

---

## 3 Domínio: Jobs de ETL

### 3.1 Spark, Python e streaming
- **3.1.1. Jobs, DynamicFrames, bookmarks e transformações**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.4. AWS Glue/3. Jobs de ETL/3.1 Spark, Python e streaming/3.1.1. Jobs, DynamicFrames, bookmarks e transformações/3.1.1.1. Jobs de ETL no Glue — Spark, DynamicFrames, job bookmarks, Python shell, Ray, streaming, parâmetros, bibliotecas e padrões de transformação|3.1.1.1. Jobs de ETL no Glue — Spark, DynamicFrames, job bookmarks, Python shell, Ray, streaming, parâmetros, bibliotecas e padrões de transformação]]

---

## 4 Domínio: Orquestração e qualidade

### 4.1 Workflows, Studio e Data Quality
- **4.1.1. Triggers, workflows, DataBrew e qualidade de dados**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.4. AWS Glue/4. Orquestração e qualidade/4.1 Workflows, Studio e Data Quality/4.1.1. Triggers, workflows, DataBrew e qualidade de dados/4.1.1.1. Orquestração e qualidade no Glue — triggers, workflows, Step Functions, Glue Studio, DataBrew, Data Quality com DQDL e detecção de dados sensíveis|4.1.1.1. Orquestração e qualidade no Glue — triggers, workflows, Step Functions, Glue Studio, DataBrew, Data Quality com DQDL e detecção de dados sensíveis]]

---

## 5 Domínio: Desempenho e custo

### 5.1 Otimização de jobs
- **5.1.1. Tuning de Spark, DPUs e formatos de tabela**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.4. AWS Glue/5. Desempenho e custo/5.1 Otimização de jobs/5.1.1. Tuning de Spark, DPUs e formatos de tabela/5.1.1.1. Desempenho e custo no Glue — dimensionamento de DPUs, Auto Scaling, Flex, arquivos pequenos, skew, partições, Iceberg e otimização de jobs Spark|5.1.1.1. Desempenho e custo no Glue — dimensionamento de DPUs, Auto Scaling, Flex, arquivos pequenos, skew, partições, Iceberg e otimização de jobs Spark]]

---

## 6 Domínio: Segurança e operação

### 6.1 Segurança, monitoramento e diagnóstico
- **6.1.1. IAM, rede, CI-CD e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.4. AWS Glue/6. Segurança e operação/6.1 Segurança, monitoramento e diagnóstico/6.1.1. IAM, rede, CI-CD e troubleshooting/6.1.1.1. Segurança e operação do Glue — IAM, VPC, criptografia, Lake Formation, monitoramento, CI-CD de jobs, zero-ETL, troubleshooting e checklist de produção|6.1.1.1. Segurança e operação do Glue — IAM, VPC, criptografia, Lake Formation, monitoramento, CI-CD de jobs, zero-ETL, troubleshooting e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.1. Amazon Athena/0 Amazon Athena (Tópicos )|Amazon Athena]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.2. Amazon Kinesis/0 Amazon Kinesis (Tópicos )|Amazon Kinesis]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.3. Amazon QuickSight/0 Amazon QuickSight (Tópicos )|Amazon QuickSight]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.1. Amazon S3/0 Amazon S3 (Tópicos )|Amazon S3]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.5. Amazon Redshift/0 Amazon Redshift (Tópicos )|Amazon Redshift]]
