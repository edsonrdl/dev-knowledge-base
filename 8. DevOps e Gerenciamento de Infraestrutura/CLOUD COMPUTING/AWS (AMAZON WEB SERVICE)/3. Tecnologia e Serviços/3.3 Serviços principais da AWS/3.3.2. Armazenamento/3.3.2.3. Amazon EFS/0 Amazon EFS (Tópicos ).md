# 📚 Guia de Estudos: Amazon EFS
#tag #aws #cloud #armazenamento #efs #nfs

> [!info] Visão Geral
> O Amazon EFS é um sistema de arquivos NFS elástico e compartilhado para Linux, com alta disponibilidade multi-AZ. Este guia cobre fundamentos (mount targets, Regional vs One Zone, montagem), desempenho (performance e throughput modes), classes de armazenamento com lifecycle, backup e replicação, e segurança (Security Groups, IAM, Access Points, criptografia).

---

## 1 Domínio: Fundamentos e Desempenho

### 1.1 Visão geral
- **1.1.1. NFS, mount targets e montagem**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.3. Amazon EFS/1. Fundamentos e Desempenho/1.1 Visão geral/1.1.1. NFS, mount targets e montagem/1.1.1.1. O que é Amazon EFS — sistema de arquivos NFS elástico, mount targets, Regional vs One Zone e montagem em EC2, ECS e Lambda|1.1.1.1. O que é Amazon EFS — sistema de arquivos NFS elástico, mount targets, Regional vs One Zone e montagem em EC2, ECS e Lambda]]

### 1.2 Desempenho
- **1.2.1. Performance e throughput modes**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.3. Amazon EFS/1. Fundamentos e Desempenho/1.2 Desempenho/1.2.1. Performance e throughput modes/1.2.1.1. Desempenho do EFS — performance modes, throughput modes (Elastic, Provisioned e Bursting) e dimensionamento|1.2.1.1. Desempenho do EFS — performance modes, throughput modes (Elastic, Provisioned e Bursting) e dimensionamento]]

### 1.3 Clientes e Plataformas
- **1.3.1. EC2, contêineres, Lambda e on-premises**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.3. Amazon EFS/1. Fundamentos e Desempenho/1.3 Clientes e Plataformas/1.3.1. EC2, contêineres, Lambda e on-premises/1.3.1.1. EFS com EC2, ECS, EKS, Lambda e on-premises — montagem, helper, driver CSI, Access Points, rede, DNS e migração de dados com DataSync|1.3.1.1. EFS com EC2, ECS, EKS, Lambda e on-premises — montagem, helper, driver CSI, Access Points, rede, DNS e migração de dados com DataSync]]

### 1.4 Desempenho Prático
- **1.4.1. Opções de montagem, paralelismo e benchmarks**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.3. Amazon EFS/1. Fundamentos e Desempenho/1.4 Desempenho Prático/1.4.1. Opções de montagem, paralelismo e benchmarks/1.4.1.1. Tuning prático de desempenho do EFS — opções de montagem NFS, paralelismo, arquivos pequenos, cache de cliente e benchmarks|1.4.1.1. Tuning prático de desempenho do EFS — opções de montagem NFS, paralelismo, arquivos pequenos, cache de cliente e benchmarks]]

---

## 2 Domínio: Classes, Custo e Proteção

### 2.1 Classes e Lifecycle
- **2.1.1. Classes, lifecycle, backup e replicação**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.3. Amazon EFS/2. Classes, Custo e Proteção/2.1 Classes e Lifecycle/2.1.1. Classes, lifecycle, backup e replicação/2.1.1.1. Classes de armazenamento, lifecycle, custo, backup e replicação do EFS|2.1.1.1. Classes de armazenamento, lifecycle, custo, backup e replicação do EFS]]

---

## 3 Domínio: Segurança e Acesso

### 3.1 Acesso
- **3.1.1. Security Groups, IAM, Access Points e criptografia**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.3. Amazon EFS/3. Segurança e Acesso/3.1 Acesso/3.1.1. Security Groups, IAM, Access Points e criptografia/3.1.1.1. Segurança e acesso ao EFS — Security Groups, IAM, Access Points, criptografia e montagem segura|3.1.1.1. Segurança e acesso ao EFS — Security Groups, IAM, Access Points, criptografia e montagem segura]]

---

## 4 Domínio: Operação e Custo

### 4.1 Monitoramento e Custo
- **4.1.1. Métricas, troubleshooting e FinOps**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.3. Amazon EFS/4. Operação e Custo/4.1 Monitoramento e Custo/4.1.1. Métricas, troubleshooting e FinOps/4.1.1.1. Monitoramento, troubleshooting e custo do EFS — métricas, alarmes, erros de montagem e desempenho, operação da replicação e checklist FinOps|4.1.1.1. Monitoramento, troubleshooting e custo do EFS — métricas, alarmes, erros de montagem e desempenho, operação da replicação e checklist FinOps]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.1. Amazon EC2/0 Amazon EC2 (Tópicos )|Amazon EC2]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.2. Amazon EBS/0 Amazon EBS (Tópicos )|Amazon EBS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.1. Amazon S3/0 Amazon S3 (Tópicos )|Amazon S3]]
