# 📚 Guia de Estudos: AWS Batch
#tag #aws #cloud #computacao #batch #hpc

> [!info] Visão Geral
> O AWS Batch executa jobs em lote em qualquer escala, provisionando automaticamente a computação (EC2, Spot, Fargate) conforme a demanda. Este guia cobre os conceitos e o ciclo de vida do job, os compute environments, as job definitions e os tipos de job (array e multi-node), as filas e o scheduling (prioridade e fair share), a operação (logs, eventos, Step Functions, troubleshooting) e segurança e custo.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Componentes e conceitos**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.7. AWS Batch/1. Fundamentos/1.1 Visão geral/1.1.1. Componentes e conceitos/1.1.1.1. O que é AWS Batch — jobs em lote gerenciados, componentes, ciclo de vida do job e quando usar em vez de Lambda ou ECS|1.1.1.1. O que é AWS Batch — jobs em lote gerenciados, componentes, ciclo de vida do job e quando usar em vez de Lambda ou ECS]]

---

## 2 Domínio: Compute environments

### 2.1 Ambientes de computação
- **2.1.1. EC2, Spot e Fargate**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.7. AWS Batch/2. Compute environments/2.1 Ambientes de computação/2.1.1. EC2, Spot e Fargate/2.1.1.1. Compute environments — gerenciados e não gerenciados, EC2, Spot, Fargate, estratégias de alocação e escala|2.1.1.1. Compute environments — gerenciados e não gerenciados, EC2, Spot, Fargate, estratégias de alocação e escala]]

---

## 3 Domínio: Jobs e Filas

### 3.1 Definições e execução
- **3.1.1. Job definitions, jobs e array jobs**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.7. AWS Batch/3. Jobs e Filas/3.1 Definições e execução/3.1.1. Job definitions, jobs e array jobs/3.1.1.1. Job definitions e jobs — container properties, parâmetros, retries, timeout, dependências, array jobs e multi-node parallel|3.1.1.1. Job definitions e jobs — container properties, parâmetros, retries, timeout, dependências, array jobs e multi-node parallel]]

### 3.2 Filas e agendamento
- **3.2.1. Job queues, prioridades e fair share**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.7. AWS Batch/3. Jobs e Filas/3.2 Filas e agendamento/3.2.1. Job queues, prioridades e fair share/3.2.1.1. Job queues e scheduling — prioridades, ordem de compute environments, fair share, preempção e filas por carga|3.2.1.1. Job queues e scheduling — prioridades, ordem de compute environments, fair share, preempção e filas por carga]]

---

## 4 Domínio: Operação e Evolução

### 4.1 Observabilidade e integração
- **4.1.1. Monitoramento, eventos e orquestração**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.7. AWS Batch/4. Operação e Evolução/4.1 Observabilidade e integração/4.1.1. Monitoramento, eventos e orquestração/4.1.1.1. Operando o Batch — CloudWatch, EventBridge, logs, Step Functions e troubleshooting de jobs presos em RUNNABLE|4.1.1.1. Operando o Batch — CloudWatch, EventBridge, logs, Step Functions e troubleshooting de jobs presos em RUNNABLE]]

### 4.2 Segurança e custo
- **4.2.1. IAM, rede e otimização de custo**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.7. AWS Batch/4. Operação e Evolução/4.2 Segurança e custo/4.2.1. IAM, rede e otimização de custo/4.2.1.1. Segurança e custo no Batch — roles IAM, rede, segredos, Spot, Savings Plans, tags e checklist de produção|4.2.1.1. Segurança e custo no Batch — roles IAM, rede, segredos, Spot, Savings Plans, tags e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.1. Amazon EC2/0 Amazon EC2 (Tópicos )|Amazon EC2]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.3. Amazon ECS/0 Amazon ECS (Tópicos )|Amazon ECS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.1. Amazon S3/0 Amazon S3 (Tópicos )|Amazon S3]]
