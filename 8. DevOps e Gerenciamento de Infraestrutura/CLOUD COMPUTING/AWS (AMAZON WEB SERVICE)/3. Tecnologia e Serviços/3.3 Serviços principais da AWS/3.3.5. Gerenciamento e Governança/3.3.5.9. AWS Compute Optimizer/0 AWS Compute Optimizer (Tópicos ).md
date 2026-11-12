# 📚 Guia de Estudos: AWS Compute Optimizer
#tag #aws #cloud #finops #rightsizing #custos #computeoptimizer #otimizacao

> [!info] Visão Geral
> O AWS Compute Optimizer analisa métricas de utilização (CloudWatch, memória via CloudWatch Agent, métricas externas) com machine learning e recomenda configurações ideais para EC2, Auto Scaling, EBS, Lambda, ECS no Fargate, RDS e licenças, além de identificar recursos ociosos, com economia estimada, risco de performance e esforço de migração. Este guia cobre fundamentos, recursos e recomendações, metodologia e preferências (headroom, janelas, métricas aprimoradas), aplicação segura das recomendações, segurança e governança e operação contínua (exportações, integrações, rotina FinOps).

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Right-sizing orientado por dados**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.9. AWS Compute Optimizer/1. Fundamentos/1.1 Visão geral/1.1.1. Right-sizing orientado por dados/1.1.1.1. O que é AWS Compute Optimizer — right-sizing com machine learning sobre métricas do CloudWatch, recursos suportados, findings, ativação e quando usar em vez de Trusted Advisor e Cost Explorer|1.1.1.1. O que é AWS Compute Optimizer — right-sizing com machine learning sobre métricas do CloudWatch, recursos suportados, findings, ativação e quando usar em vez de Trusted Advisor e Cost Explorer]]

---

## 2 Domínio: Recursos e recomendações

### 2.1 EC2, Auto Scaling, EBS, Lambda, ECS e RDS
- **2.1.1. Tipos de recurso e findings**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.9. AWS Compute Optimizer/2. Recursos e recomendações/2.1 EC2, Auto Scaling, EBS, Lambda, ECS e RDS/2.1.1. Tipos de recurso e findings/2.1.1.1. Recursos e recomendações do Compute Optimizer — EC2, Auto Scaling, EBS, Lambda, ECS no Fargate, RDS e licenças, findings, opções, risco de performance e esforço de migração|2.1.1.1. Recursos e recomendações do Compute Optimizer — EC2, Auto Scaling, EBS, Lambda, ECS no Fargate, RDS e licenças, findings, opções, risco de performance e esforço de migração]]

---

## 3 Domínio: Metodologia e preferências

### 3.1 Métricas, janelas e preferências
- **3.1.1. Como as recomendações são geradas**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.9. AWS Compute Optimizer/3. Metodologia e preferências/3.1 Métricas, janelas e preferências/3.1.1. Como as recomendações são geradas/3.1.1.1. Como o Compute Optimizer gera recomendações — métricas e janelas de análise, métricas de memória, preferências de recomendação, headroom, famílias preferidas e métricas externas|3.1.1.1. Como o Compute Optimizer gera recomendações — métricas e janelas de análise, métricas de memória, preferências de recomendação, headroom, famílias preferidas e métricas externas]]

---

## 4 Domínio: Aplicação das recomendações

### 4.1 Risco, economia e automação
- **4.1.1. Implementação segura**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.9. AWS Compute Optimizer/4. Aplicação das recomendações/4.1 Risco, economia e automação/4.1.1. Implementação segura/4.1.1.1. Aplicando recomendações do Compute Optimizer — avaliação de risco e economia, testes, mudanças seguras, automação e integração com Cost Optimization Hub|4.1.1.1. Aplicando recomendações do Compute Optimizer — avaliação de risco e economia, testes, mudanças seguras, automação e integração com Cost Optimization Hub]]

---

## 5 Domínio: Segurança e governança

### 5.1 Opt-in, Organizations e dados
- **5.1.1. Controle e conformidade**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.9. AWS Compute Optimizer/5. Segurança e governança/5.1 Opt-in, Organizations e dados/5.1.1. Controle e conformidade/5.1.1.1. Segurança e governança do Compute Optimizer — ativação por conta e Organizations, IAM, dados de métricas, exportação, auditoria e controles|5.1.1.1. Segurança e governança do Compute Optimizer — ativação por conta e Organizations, IAM, dados de métricas, exportação, auditoria e controles]]

---

## 6 Domínio: Operação e uso contínuo

### 6.1 Exportação, integrações e troubleshooting
- **6.1.1. Observabilidade e uso contínuo**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.9. AWS Compute Optimizer/6. Operação e uso contínuo/6.1 Exportação, integrações e troubleshooting/6.1.1. Observabilidade e uso contínuo/6.1.1.1. Operação do Compute Optimizer — exportações para S3, integrações, relatórios, custos de métricas aprimoradas, limitações, rotina FinOps e troubleshooting|6.1.1.1. Operação do Compute Optimizer — exportações para S3, integrações, relatórios, custos de métricas aprimoradas, limitações, rotina FinOps e troubleshooting]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.1. AWS CloudWatch/0 AWS CloudWatch (Tópicos )|AWS CloudWatch]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.1. Amazon EC2/0 Amazon EC2 (Tópicos )|Amazon EC2]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.2. AWS Lambda/0 AWS Lambda (Tópicos )|AWS Lambda]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.2. Amazon EBS/0 Amazon EBS (Tópicos )|Amazon EBS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.1. Amazon RDS/0 Amazon RDS (Tópicos )|Amazon RDS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/2. Segurança e Conformidade/2.4 Recursos de suporte à segurança/2.4.1. Ferramentas de governança/2.4.1.1. AWS Trusted Advisor|AWS Trusted Advisor]]
