# 📚 Guia de Estudos: Amazon Athena
#tag #aws #cloud #analytics #athena #sql #data-lake

> [!info] Visão Geral
> O Amazon Athena é um serviço de consulta interativa e serverless que analisa dados diretamente no Amazon S3 com SQL padrão, sem provisionar servidores nem carregar dados em um banco. Este guia cobre os fundamentos (como funciona, preço e comparação com Redshift e EMR), as tabelas (Glue Data Catalog, formatos, partições, CTAS e Iceberg), o desempenho e custo, as consultas avançadas (logs AWS, federated queries, UDFs, Spark), a segurança (IAM, Lake Formation, KMS) e a operação (quotas, monitoramento e troubleshooting).

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Consulta serverless sobre S3**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.1. Amazon Athena/1. Fundamentos/1.1 Visão geral/1.1.1. Consulta serverless sobre S3/1.1.1.1. O que é Amazon Athena — SQL serverless sobre S3, como funciona, Glue Data Catalog, modelo de preço e quando usar em vez de Redshift ou EMR|1.1.1.1. O que é Amazon Athena — SQL serverless sobre S3, como funciona, Glue Data Catalog, modelo de preço e quando usar em vez de Redshift ou EMR]]

---

## 2 Domínio: Dados e tabelas

### 2.1 Catálogo, formatos e partições
- **2.1.1. Tabelas, SerDes e partições**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.1. Amazon Athena/2. Dados e tabelas/2.1 Catálogo, formatos e partições/2.1.1. Tabelas, SerDes e partições/2.1.1.1. Tabelas no Athena — Glue Data Catalog, DDL, SerDes, formatos, partições, partition projection, CTAS e tabelas Iceberg|2.1.1.1. Tabelas no Athena — Glue Data Catalog, DDL, SerDes, formatos, partições, partition projection, CTAS e tabelas Iceberg]]

---

## 3 Domínio: Desempenho e custo

### 3.1 Otimização de consultas
- **3.1.1. Escaneamento, formatos e planejamento**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.1. Amazon Athena/3. Desempenho e custo/3.1 Otimização de consultas/3.1.1. Escaneamento, formatos e planejamento/3.1.1.1. Desempenho e custo no Athena — dados escaneados, formatos colunares, arquivos, bucketing, boas práticas de SQL, reuso de resultados e capacidade provisionada|3.1.1.1. Desempenho e custo no Athena — dados escaneados, formatos colunares, arquivos, bucketing, boas práticas de SQL, reuso de resultados e capacidade provisionada]]

---

## 4 Domínio: Consultas avançadas

### 4.1 SQL, federação e Spark
- **4.1.1. Casos de uso, federated queries e notebooks**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.1. Amazon Athena/4. Consultas avançadas/4.1 SQL, federação e Spark/4.1.1. Casos de uso, federated queries e notebooks/4.1.1.1. Consultas avançadas no Athena — logs da AWS, funções SQL, views, federated queries, UDFs, prepared statements e Apache Spark|4.1.1.1. Consultas avançadas no Athena — logs da AWS, funções SQL, views, federated queries, UDFs, prepared statements e Apache Spark]]

---

## 5 Domínio: Segurança

### 5.1 Acesso e proteção de dados
- **5.1.1. IAM, Lake Formation, KMS e rede**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.1. Amazon Athena/5. Segurança/5.1 Acesso e proteção de dados/5.1.1. IAM, Lake Formation, KMS e rede/5.1.1.1. Segurança no Athena — IAM, permissões no S3, Lake Formation, criptografia com KMS, workgroups, endpoints de VPC e auditoria|5.1.1.1. Segurança no Athena — IAM, permissões no S3, Lake Formation, criptografia com KMS, workgroups, endpoints de VPC e auditoria]]

---

## 6 Domínio: Operação

### 6.1 Quotas, monitoramento e diagnóstico
- **6.1.1. Operação, limites e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.1. Amazon Athena/6. Operação/6.1 Quotas, monitoramento e diagnóstico/6.1.1. Operação, limites e troubleshooting/6.1.1.1. Operando o Athena — quotas, monitoramento, orquestração, troubleshooting de falhas e checklist de produção|6.1.1.1. Operando o Athena — quotas, monitoramento, orquestração, troubleshooting de falhas e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.1. Amazon S3/0 Amazon S3 (Tópicos )|Amazon S3]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.5. Amazon Redshift/0 Amazon Redshift (Tópicos )|Amazon Redshift]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.2. AWS CloudTrail/0 AWS CloudTrail (Tópicos )|AWS CloudTrail]]
