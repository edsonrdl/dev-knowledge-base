# 📚 Guia de Estudos: Amazon EBS
#tag #aws #cloud #armazenamento #ebs #bloco

> [!info] Visão Geral
> O Amazon EBS fornece volumes de armazenamento em bloco persistentes para instâncias EC2, replicados dentro de uma Availability Zone. Este guia cobre os fundamentos (bloco, AZ, instance store, ciclo de vida), os tipos de volume (gp3, io2, st1, sc1) e seu desempenho, snapshots e automação, e criptografia com KMS.

---

## 1 Domínio: Fundamentos e Tipos

### 1.1 Visão geral
- **1.1.1. Blocos, AZ e ciclo de vida**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.2. Amazon EBS/1. Fundamentos e Tipos/1.1 Visão geral/1.1.1. Blocos, AZ e ciclo de vida/1.1.1.1. O que é Amazon EBS — volumes de bloco, Availability Zone, anexo à EC2, instance store e ciclo de vida|1.1.1.1. O que é Amazon EBS — volumes de bloco, Availability Zone, anexo à EC2, instance store e ciclo de vida]]

### 1.2 Tipos e Desempenho
- **1.2.1. Tipos de volume, IOPS e throughput**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.2. Amazon EBS/1. Fundamentos e Tipos/1.2 Tipos e Desempenho/1.2.1. Tipos de volume, IOPS e throughput/1.2.1.1. Tipos de volume EBS — gp3, gp2, io2, st1 e sc1, IOPS, throughput e Elastic Volumes|1.2.1.1. Tipos de volume EBS — gp3, gp2, io2, st1 e sc1, IOPS, throughput e Elastic Volumes]]

### 1.3 Desempenho e Benchmarking
- **1.3.1. Limites da instância, fio e RAID**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.2. Amazon EBS/1. Fundamentos e Tipos/1.3 Desempenho e Benchmarking/1.3.1. Limites da instância, fio e RAID/1.3.1.1. Desempenho do EBS em profundidade — limites do volume e da instância, EBS-optimized, benchmarking com fio, fila de I-O, RAID e diagnóstico|1.3.1.1. Desempenho do EBS em profundidade — limites do volume e da instância, EBS-optimized, benchmarking com fio, fila de I/O, RAID e diagnóstico]]

### 1.4 Operação de Volumes
- **1.4.1. Elastic Volumes, expansão e Multi-Attach**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.2. Amazon EBS/1. Fundamentos e Tipos/1.4 Operação de Volumes/1.4.1. Elastic Volumes, expansão e Multi-Attach/1.4.1.1. Operações com volumes EBS — Elastic Volumes, expansão do sistema de arquivos, Multi-Attach, mudança de AZ e automação|1.4.1.1. Operações com volumes EBS — Elastic Volumes, expansão do sistema de arquivos, Multi-Attach, mudança de AZ e automação]]

---

## 2 Domínio: Snapshots e Proteção

### 2.1 Snapshots
- **2.1.1. Incremental, restore e automação**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.2. Amazon EBS/2. Snapshots e Proteção/2.1 Snapshots/2.1.1. Incremental, restore e automação/2.1.1.1. Snapshots do EBS — incrementais, restauração, Fast Snapshot Restore, Data Lifecycle Manager e Recycle Bin|2.1.1.1. Snapshots do EBS — incrementais, restauração, Fast Snapshot Restore, Data Lifecycle Manager e Recycle Bin]]

### 2.2 Snapshots Avançados
- **2.2.1. Archive, FSR, Lock e DR**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.2. Amazon EBS/2. Snapshots e Proteção/2.2 Snapshots Avançados/2.2.1. Archive, FSR, Lock e DR/2.2.1.1. Snapshots avançados do EBS — Archive, Fast Snapshot Restore, Snapshot Lock, compartilhamento, cópia entre regiões, AMIs e estratégias de DR|2.2.1.1. Snapshots avançados do EBS — Archive, Fast Snapshot Restore, Snapshot Lock, compartilhamento, cópia entre regiões, AMIs e estratégias de DR]]

---

## 3 Domínio: Segurança

### 3.1 Criptografia
- **3.1.1. KMS e criptografia padrão**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.2. Amazon EBS/3. Segurança/3.1 Criptografia/3.1.1. KMS e criptografia padrão/3.1.1.1. Criptografia do EBS — KMS, criptografia por padrão e compartilhamento de snapshots criptografados|3.1.1.1. Criptografia do EBS — KMS, criptografia por padrão e compartilhamento de snapshots criptografados]]

---

## 4 Domínio: Operação e Custo

### 4.1 Monitoramento e Custo
- **4.1.1. Métricas, troubleshooting e FinOps**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.2. Amazon EBS/4. Operação e Custo/4.1 Monitoramento e Custo/4.1.1. Métricas, troubleshooting e FinOps/4.1.1.1. Monitoramento, troubleshooting e custo do EBS — métricas, status checks, volumes ociosos, gp2 para gp3, rightsizing e checklist FinOps|4.1.1.1. Monitoramento, troubleshooting e custo do EBS — métricas, status checks, volumes ociosos, gp2 para gp3, rightsizing e checklist FinOps]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.1. Amazon EC2/0 Amazon EC2 (Tópicos )|Amazon EC2]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.1. Amazon S3/0 Amazon S3 (Tópicos )|Amazon S3]]
