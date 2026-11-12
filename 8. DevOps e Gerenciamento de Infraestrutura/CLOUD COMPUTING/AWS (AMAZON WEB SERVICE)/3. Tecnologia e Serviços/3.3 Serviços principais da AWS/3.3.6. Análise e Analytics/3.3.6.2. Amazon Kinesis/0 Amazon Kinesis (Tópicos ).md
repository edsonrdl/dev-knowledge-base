# 📚 Guia de Estudos: Amazon Kinesis
#tag #aws #cloud #analytics #kinesis #streaming #tempo-real

> [!info] Visão Geral
> O Amazon Kinesis é a família de serviços da AWS para streaming de dados em tempo real: coletar, reter, processar e entregar fluxos de eventos em escala. Este guia cobre os fundamentos da família (Data Streams, Data Firehose, Managed Service for Apache Flink e Video Streams), os shards e modos de capacidade, os produtores e consumidores (KPL, KCL, Lambda, enhanced fan-out), a entrega gerenciada pelo Firehose, o processamento com estado no Flink e o vídeo, e a operação (segurança, monitoramento, custo e troubleshooting).

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Streaming de dados e a família Kinesis**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.2. Amazon Kinesis/1. Fundamentos/1.1 Visão geral/1.1.1. Streaming de dados e a família Kinesis/1.1.1.1. O que é Amazon Kinesis — streaming de dados em tempo real, a família de serviços, casos de uso e como escolher entre Streams, Firehose, Flink e Video Streams|1.1.1.1. O que é Amazon Kinesis — streaming de dados em tempo real, a família de serviços, casos de uso e como escolher entre Streams, Firehose, Flink e Video Streams]]

---

## 2 Domínio: Data Streams

### 2.1 Shards e capacidade
- **2.1.1. Shards, chaves de partição e modos de capacidade**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.2. Amazon Kinesis/2. Data Streams/2.1 Shards e capacidade/2.1.1. Shards, chaves de partição e modos de capacidade/2.1.1.1. Kinesis Data Streams — shards, chaves de partição, modos provisionado e sob demanda, retenção, limites de throughput e resharding|2.1.1.1. Kinesis Data Streams — shards, chaves de partição, modos provisionado e sob demanda, retenção, limites de throughput e resharding]]

---

## 3 Domínio: Produtores e consumidores

### 3.1 Escrita e leitura de streams
- **3.1.1. KPL, KCL, Lambda e enhanced fan-out**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.2. Amazon Kinesis/3. Produtores e consumidores/3.1 Escrita e leitura de streams/3.1.1. KPL, KCL, Lambda e enhanced fan-out/3.1.1.1. Produtores e consumidores do Kinesis — PutRecords, KPL, KCL, Lambda, enhanced fan-out, checkpoints, falhas e idempotência|3.1.1.1. Produtores e consumidores do Kinesis — PutRecords, KPL, KCL, Lambda, enhanced fan-out, checkpoints, falhas e idempotência]]

---

## 4 Domínio: Entrega de dados

### 4.1 Amazon Data Firehose
- **4.1.1. Entrega gerenciada, transformação e destinos**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.2. Amazon Kinesis/4. Entrega de dados/4.1 Amazon Data Firehose/4.1.1. Entrega gerenciada, transformação e destinos/4.1.1.1. Amazon Data Firehose — destinos, buffering, transformação com Lambda, conversão para Parquet, particionamento dinâmico, falhas e comparação com Data Streams|4.1.1.1. Amazon Data Firehose — destinos, buffering, transformação com Lambda, conversão para Parquet, particionamento dinâmico, falhas e comparação com Data Streams]]

---

## 5 Domínio: Processamento e vídeo

### 5.1 Apache Flink e Video Streams
- **5.1.1. Processamento em tempo real e vídeo**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.2. Amazon Kinesis/5. Processamento e vídeo/5.1 Apache Flink e Video Streams/5.1.1. Processamento em tempo real e vídeo/5.1.1.1. Processamento em tempo real e vídeo — Managed Service for Apache Flink, janelas, estado, checkpoints, Studio notebooks e Kinesis Video Streams|5.1.1.1. Processamento em tempo real e vídeo — Managed Service for Apache Flink, janelas, estado, checkpoints, Studio notebooks e Kinesis Video Streams]]

---

## 6 Domínio: Operação

### 6.1 Segurança, custo e diagnóstico
- **6.1.1. Segurança, monitoramento e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.2. Amazon Kinesis/6. Operação/6.1 Segurança, custo e diagnóstico/6.1.1. Segurança, monitoramento e troubleshooting/6.1.1.1. Operando o Kinesis — segurança, monitoramento, custos, limites, troubleshooting de streams e checklist de produção|6.1.1.1. Operando o Kinesis — segurança, monitoramento, custos, limites, troubleshooting de streams e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.1. Amazon Athena/0 Amazon Athena (Tópicos )|Amazon Athena]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.1. Amazon S3/0 Amazon S3 (Tópicos )|Amazon S3]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.5. Amazon Redshift/0 Amazon Redshift (Tópicos )|Amazon Redshift]]
