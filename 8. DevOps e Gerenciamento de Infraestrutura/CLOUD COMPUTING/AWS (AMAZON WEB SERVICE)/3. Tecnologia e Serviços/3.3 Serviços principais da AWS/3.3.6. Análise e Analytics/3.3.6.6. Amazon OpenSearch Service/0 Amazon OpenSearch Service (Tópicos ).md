# 📚 Guia de Estudos: Amazon OpenSearch Service
#tag #aws #cloud #analytics #opensearch #busca #logs #vetores #observabilidade

> [!info] Visão Geral
> O Amazon OpenSearch Service é o serviço gerenciado de busca e análise da AWS (OpenSearch e OpenSearch Dashboards): busca full-text, análise de logs e observabilidade, SIEM, busca geoespacial e busca vetorial para RAG, em domínios (clusters) ou OpenSearch Serverless (coleções). Este guia cobre fundamentos, dimensionamento de domínios (nós, shards, Multi-AZ), ingestão e consultas, camadas de armazenamento e custos (UltraWarm, cold, ISM), segurança (VPC, FGAC, criptografia) e operação (métricas, snapshots, runbooks).

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Busca e análise de logs**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.6. Amazon OpenSearch Service/1. Fundamentos/1.1 Visão geral/1.1.1. Busca e análise de logs/1.1.1.1. O que é Amazon OpenSearch Service — busca e análise de logs, domínios e Serverless, índices, documentos e shards, OpenSearch Dashboards e quando usar em vez de Athena, CloudWatch Logs e DynamoDB|1.1.1.1. O que é Amazon OpenSearch Service — busca e análise de logs, domínios e Serverless, índices, documentos e shards, OpenSearch Dashboards e quando usar em vez de Athena, CloudWatch Logs e DynamoDB]]

---

## 2 Domínio: Domínios e arquitetura

### 2.1 Nós, shards e implantação
- **2.1.1. Dimensionamento e topologia**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.6. Amazon OpenSearch Service/2. Domínios e arquitetura/2.1 Nós, shards e implantação/2.1.1. Dimensionamento e topologia/2.1.1.1. Domínios do OpenSearch — nós de dados, cluster manager e warm, instâncias e EBS, shards e réplicas, Multi-AZ com standby, dimensionamento e blue-green|2.1.1.1. Domínios do OpenSearch — nós de dados, cluster manager e warm, instâncias e EBS, shards e réplicas, Multi-AZ com standby, dimensionamento e blue-green]]

---

## 3 Domínio: Ingestão e consultas

### 3.1 Índices, pipelines e consultas
- **3.1.1. Dados e busca**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.6. Amazon OpenSearch Service/3. Ingestão e consultas/3.1 Índices, pipelines e consultas/3.1.1. Dados e busca/3.1.1.1. Ingestão e consultas no OpenSearch — mapeamentos, Query DSL, busca full-text, agregações, OpenSearch Ingestion, Firehose, CloudWatch Logs, vetores e k-NN|3.1.1.1. Ingestão e consultas no OpenSearch — mapeamentos, Query DSL, busca full-text, agregações, OpenSearch Ingestion, Firehose, CloudWatch Logs, vetores e k-NN]]

---

## 4 Domínio: Armazenamento e custos

### 4.1 UltraWarm, cold e ciclo de vida
- **4.1.1. Camadas e economia**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.6. Amazon OpenSearch Service/4. Armazenamento e custos/4.1 UltraWarm, cold e ciclo de vida/4.1.1. Camadas e economia/4.1.1.1. Camadas de armazenamento e custos no OpenSearch — hot, UltraWarm e cold, Index State Management, snapshots, OpenSearch Serverless, instâncias reservadas e otimização|4.1.1.1. Camadas de armazenamento e custos no OpenSearch — hot, UltraWarm e cold, Index State Management, snapshots, OpenSearch Serverless, instâncias reservadas e otimização]]

---

## 5 Domínio: Segurança e governança

### 5.1 Acesso, criptografia e VPC
- **5.1.1. Controle e conformidade**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.6. Amazon OpenSearch Service/5. Segurança e governança/5.1 Acesso, criptografia e VPC/5.1.1. Controle e conformidade/5.1.1.1. Segurança do OpenSearch — VPC e endpoints públicos, políticas de acesso, fine-grained access control, SAML e Cognito, criptografia, audit logs e conformidade|5.1.1.1. Segurança do OpenSearch — VPC e endpoints públicos, políticas de acesso, fine-grained access control, SAML e Cognito, criptografia, audit logs e conformidade]]

---

## 6 Domínio: Operação e troubleshooting

### 6.1 Monitoramento, snapshots e quotas
- **6.1.1. Observabilidade e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.6. Amazon OpenSearch Service/6. Operação e troubleshooting/6.1 Monitoramento, snapshots e quotas/6.1.1. Observabilidade e troubleshooting/6.1.1.1. Operação do OpenSearch — métricas, status do cluster, JVM memory pressure, snapshots, atualizações, quotas, troubleshooting e checklist de produção|6.1.1.1. Operação do OpenSearch — métricas, status do cluster, JVM memory pressure, snapshots, atualizações, quotas, troubleshooting e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.2. Amazon Kinesis/0 Amazon Kinesis (Tópicos )|Amazon Kinesis]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.1. Amazon Athena/0 Amazon Athena (Tópicos )|Amazon Athena]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.5. Amazon EMR/0 Amazon EMR (Tópicos )|Amazon EMR]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.1. AWS CloudWatch/0 AWS CloudWatch (Tópicos )|AWS CloudWatch]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.1. Amazon Cognito/0 Amazon Cognito (Tópicos )|Amazon Cognito]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.2. Amazon DynamoDB/0 Amazon DynamoDB (Tópicos )|Amazon DynamoDB]]
