# 📚 Guia de Estudos: Amazon SNS
#tag #aws #cloud #integracao #sns #pub-sub #notificacoes #fan-out

> [!info] Visão Geral
> O Amazon SNS é o serviço gerenciado de publicação e assinatura (pub-sub) da AWS: um publicador envia uma mensagem a um tópico e o SNS entrega uma cópia a cada assinante (SQS, Lambda, HTTP/S, Firehose, e-mail, SMS e push móvel). Este guia cobre os fundamentos (tópicos, protocolos, Standard vs FIFO e comparação com SQS e EventBridge), os tópicos e mensagens (assinaturas, atributos, raw delivery), a filtragem e o fan-out (filter policies, FIFO, replay), a entrega e confiabilidade (retentativas, DLQ, validação), as notificações a pessoas (SMS, push, e-mail) e a segurança e operação.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Publicação e assinatura gerenciadas**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.2. Amazon SNS/1. Fundamentos/1.1 Visão geral/1.1.1. Publicação e assinatura gerenciadas/1.1.1.1. O que é Amazon SNS — publicação e assinatura (pub-sub), tópicos, assinantes, protocolos, Standard vs FIFO e quando usar em vez de SQS ou EventBridge|1.1.1.1. O que é Amazon SNS — publicação e assinatura (pub-sub), tópicos, assinantes, protocolos, Standard vs FIFO e quando usar em vez de SQS ou EventBridge]]

---

## 2 Domínio: Tópicos e mensagens

### 2.1 Publicação, assinaturas e formatos
- **2.1.1. Tópicos, assinaturas, atributos e estrutura de mensagem**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.2. Amazon SNS/2. Tópicos e mensagens/2.1 Publicação, assinaturas e formatos/2.1.1. Tópicos, assinaturas, atributos e estrutura de mensagem/2.1.1.1. Tópicos e mensagens no SNS — criação, assinaturas e confirmação, atributos, raw message delivery, estrutura por protocolo, publicação em lote e mensagens grandes|2.1.1.1. Tópicos e mensagens no SNS — criação, assinaturas e confirmação, atributos, raw message delivery, estrutura por protocolo, publicação em lote e mensagens grandes]]

---

## 3 Domínio: Filtragem e fan-out

### 3.1 Filter policies e padrões de distribuição
- **3.1.1. Filtros, fan-out, FIFO e replay**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.2. Amazon SNS/3. Filtragem e fan-out/3.1 Filter policies e padrões de distribuição/3.1.1. Filtros, fan-out, FIFO e replay/3.1.1.1. Filtragem e fan-out no SNS — filter policies por atributos e por corpo, operadores, fan-out com SQS, tópicos FIFO, ordenação, deduplicação, arquivamento e replay|3.1.1.1. Filtragem e fan-out no SNS — filter policies por atributos e por corpo, operadores, fan-out com SQS, tópicos FIFO, ordenação, deduplicação, arquivamento e replay]]

---

## 4 Domínio: Entrega e confiabilidade

### 4.1 Retentativas, DLQ e validação
- **4.1.1. Políticas de entrega, DLQ de assinatura e HTTP seguro**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.2. Amazon SNS/4. Entrega e confiabilidade/4.1 Retentativas, DLQ e validação/4.1.1. Políticas de entrega, DLQ de assinatura e HTTP seguro/4.1.1.1. Entrega e confiabilidade no SNS — políticas de retentativa, DLQ de assinatura, logs de status de entrega, idempotência, validação de assinatura em HTTP, throttling e falhas por protocolo|4.1.1.1. Entrega e confiabilidade no SNS — políticas de retentativa, DLQ de assinatura, logs de status de entrega, idempotência, validação de assinatura em HTTP, throttling e falhas por protocolo]]

---

## 5 Domínio: Notificações a pessoas

### 5.1 SMS, push móvel e e-mail
- **5.1.1. Canais A2P e conformidade**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.2. Amazon SNS/5. Notificações a pessoas/5.1 SMS, push móvel e e-mail/5.1.1. Canais A2P e conformidade/5.1.1.1. Notificações a pessoas com SNS — SMS, push móvel (APNs e FCM), e-mail, identidades de origem, limites de gasto, opt-out, conformidade e quando usar SES, Pinpoint ou End User Messaging|5.1.1.1. Notificações a pessoas com SNS — SMS, push móvel (APNs e FCM), e-mail, identidades de origem, limites de gasto, opt-out, conformidade e quando usar SES, Pinpoint ou End User Messaging]]

---

## 6 Domínio: Segurança e operação

### 6.1 Acesso, criptografia, monitoramento e custo
- **6.1.1. Políticas, KMS, VPC, métricas e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.2. Amazon SNS/6. Segurança e operação/6.1 Acesso, criptografia, monitoramento e custo/6.1.1. Políticas, KMS, VPC, métricas e troubleshooting/6.1.1.1. Segurança e operação do SNS — políticas de tópico, IAM, criptografia SSE-KMS, endpoints de VPC, data protection, métricas, quotas, custos, IaC e checklist de produção|6.1.1.1. Segurança e operação do SNS — políticas de tópico, IAM, criptografia SSE-KMS, endpoints de VPC, data protection, métricas, quotas, custos, IaC e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.1. Amazon SQS/0 Amazon SQS (Tópicos )|Amazon SQS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.1. AWS CloudWatch/0 AWS CloudWatch (Tópicos )|AWS CloudWatch]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.2. Amazon Kinesis/0 Amazon Kinesis (Tópicos )|Amazon Kinesis]]
