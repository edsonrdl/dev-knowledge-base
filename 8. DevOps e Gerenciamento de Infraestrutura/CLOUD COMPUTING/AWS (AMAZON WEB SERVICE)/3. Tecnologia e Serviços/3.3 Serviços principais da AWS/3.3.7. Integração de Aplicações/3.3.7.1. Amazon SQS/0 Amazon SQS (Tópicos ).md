# 📚 Guia de Estudos: Amazon SQS
#tag #aws #cloud #integracao #sqs #filas #mensageria #desacoplamento

> [!info] Visão Geral
> O Amazon SQS é o serviço de filas de mensagens totalmente gerenciado da AWS, usado para desacoplar produtores e consumidores, amortecer picos e distribuir trabalho com tolerância a falhas. Este guia cobre os fundamentos (Standard vs FIFO e comparação com SNS, Kinesis e EventBridge), o ciclo de vida da mensagem (polling, visibility timeout, batching, mensagens grandes), as garantias de Standard e FIFO, a confiabilidade (DLQ, retentativas, idempotência, Lambda, escala por backlog), a segurança (IAM, queue policy, KMS, VPC) e a operação (métricas, quotas, custos e troubleshooting).

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Filas de mensagens e desacoplamento**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.1. Amazon SQS/1. Fundamentos/1.1 Visão geral/1.1.1. Filas de mensagens e desacoplamento/1.1.1.1. O que é Amazon SQS — filas gerenciadas, desacoplamento, produtores e consumidores, Standard vs FIFO e quando usar em vez de SNS, Kinesis ou EventBridge|1.1.1.1. O que é Amazon SQS — filas gerenciadas, desacoplamento, produtores e consumidores, Standard vs FIFO e quando usar em vez de SNS, Kinesis ou EventBridge]]

---

## 2 Domínio: Ciclo de vida da mensagem

### 2.1 Envio, recebimento e visibilidade
- **2.1.1. Polling, visibility timeout, batching e mensagens grandes**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.1. Amazon SQS/2. Ciclo de vida da mensagem/2.1 Envio, recebimento e visibilidade/2.1.1. Polling, visibility timeout, batching e mensagens grandes/2.1.1.1. Ciclo de vida da mensagem no SQS — envio, long polling, visibility timeout, batching, delay, retenção, atributos e mensagens grandes com S3|2.1.1.1. Ciclo de vida da mensagem no SQS — envio, long polling, visibility timeout, batching, delay, retenção, atributos e mensagens grandes com S3]]

---

## 3 Domínio: Standard e FIFO

### 3.1 Garantias de entrega e ordem
- **3.1.1. Standard, FIFO, grupos e deduplicação**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.1. Amazon SQS/3. Standard e FIFO/3.1 Garantias de entrega e ordem/3.1.1. Standard, FIFO, grupos e deduplicação/3.1.1.1. Filas Standard e FIFO — garantias de entrega e ordem, MessageGroupId, deduplicação, high throughput FIFO, fair queues e como escolher|3.1.1.1. Filas Standard e FIFO — garantias de entrega e ordem, MessageGroupId, deduplicação, high throughput FIFO, fair queues e como escolher]]

---

## 4 Domínio: Confiabilidade e padrões

### 4.1 DLQ, retentativas e integrações
- **4.1.1. Dead-letter queues, Lambda, fan-out e padrões**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.1. Amazon SQS/4. Confiabilidade e padrões/4.1 DLQ, retentativas e integrações/4.1.1. Dead-letter queues, Lambda, fan-out e padrões/4.1.1.1. Confiabilidade e padrões com SQS — dead-letter queues, redrive, retentativas, idempotência, Lambda, Auto Scaling por backlog, fan-out com SNS e padrões de arquitetura|4.1.1.1. Confiabilidade e padrões com SQS — dead-letter queues, redrive, retentativas, idempotência, Lambda, Auto Scaling por backlog, fan-out com SNS e padrões de arquitetura]]

---

## 5 Domínio: Segurança

### 5.1 Acesso e criptografia
- **5.1.1. IAM, políticas de fila, KMS e VPC**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.1. Amazon SQS/5. Segurança/5.1 Acesso e criptografia/5.1.1. IAM, políticas de fila, KMS e VPC/5.1.1.1. Segurança no SQS — IAM, políticas de fila, acesso entre contas, criptografia SSE-SQS e SSE-KMS, endpoints de VPC, integrações com SNS e S3 e auditoria|5.1.1.1. Segurança no SQS — IAM, políticas de fila, acesso entre contas, criptografia SSE-SQS e SSE-KMS, endpoints de VPC, integrações com SNS e S3 e auditoria]]

---

## 6 Domínio: Operação

### 6.1 Monitoramento, custo e diagnóstico
- **6.1.1. Métricas, quotas, custos e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.1. Amazon SQS/6. Operação/6.1 Monitoramento, custo e diagnóstico/6.1.1. Métricas, quotas, custos e troubleshooting/6.1.1.1. Operando o SQS — métricas e alarmes, quotas, custos, IaC, testes de carga, troubleshooting de filas e checklist de produção|6.1.1.1. Operando o SQS — métricas e alarmes, quotas, custos, IaC, testes de carga, troubleshooting de filas e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.2. Amazon Kinesis/0 Amazon Kinesis (Tópicos )|Amazon Kinesis]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.1. Amazon S3/0 Amazon S3 (Tópicos )|Amazon S3]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.1. AWS CloudWatch/0 AWS CloudWatch (Tópicos )|AWS CloudWatch]]
