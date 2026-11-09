# 📚 Guia de Estudos: AWS Storage Gateway
#tag #aws #cloud #armazenamento #storagegateway #hibrido

> [!info] Visão Geral
> O AWS Storage Gateway conecta aplicações on-premises ao armazenamento da AWS com protocolos conhecidos (NFS, SMB, iSCSI, fita virtual), usando cache local. Este guia cobre os tipos (S3 File, FSx File, Volume e Tape Gateway), a implantação, a segurança e a operação, além da comparação com DataSync e Transfer Family.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Armazenamento híbrido e tipos de gateway**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.4. AWS Storage Gateway/1. Fundamentos/1.1 Visão geral/1.1.1. Armazenamento híbrido e tipos de gateway/1.1.1.1. O que é AWS Storage Gateway — armazenamento híbrido, tipos de gateway, cache local e como escolher|1.1.1.1. O que é AWS Storage Gateway — armazenamento híbrido, tipos de gateway, cache local e como escolher]]

---

## 2 Domínio: Tipos de Gateway

### 2.1 File Gateway
- **2.1.1. S3 File e FSx File**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.4. AWS Storage Gateway/2. Tipos de Gateway/2.1 File Gateway/2.1.1. S3 File e FSx File/2.1.1.1. File Gateway — S3 File Gateway e FSx File Gateway, SMB e NFS, cache e ciclo de vida do S3|2.1.1.1. File Gateway — S3 File Gateway e FSx File Gateway, SMB e NFS, cache e ciclo de vida do S3]]

- **2.1.2. Cache, consistência e SMB com AD**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.4. AWS Storage Gateway/2. Tipos de Gateway/2.1 File Gateway/2.1.2. Cache, consistência e SMB com AD/2.1.2.1. S3 File Gateway em profundidade — cache, consistência, RefreshCache, bloqueio de arquivos, autenticação SMB com AD, desempenho e troubleshooting|2.1.2.1. S3 File Gateway em profundidade — cache, consistência, RefreshCache, bloqueio de arquivos, autenticação SMB com AD, desempenho e troubleshooting]]

### 2.2 Volume e Tape
- **2.2.1. iSCSI e fitas virtuais**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.4. AWS Storage Gateway/2. Tipos de Gateway/2.2 Volume e Tape/2.2.1. iSCSI e fitas virtuais/2.2.1.1. Volume Gateway e Tape Gateway — iSCSI, modos cached e stored, snapshots e fitas virtuais|2.2.1.1. Volume Gateway e Tape Gateway — iSCSI, modos cached e stored, snapshots e fitas virtuais]]

- **2.2.2. Backup, DR e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.4. AWS Storage Gateway/2. Tipos de Gateway/2.2 Volume e Tape/2.2.2. Backup, DR e troubleshooting/2.2.2.1. Tape Gateway e Volume Gateway na prática — integração com software de backup, ciclo de vida de fitas, DR em EC2, dimensionamento de cache e troubleshooting|2.2.2.1. Tape Gateway e Volume Gateway na prática — integração com software de backup, ciclo de vida de fitas, DR em EC2, dimensionamento de cache e troubleshooting]]

---

## 3 Domínio: Implantação e Operação

### 3.1 Operação
- **3.1.1. Implantação, rede, segurança e monitoramento**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.4. AWS Storage Gateway/3. Implantação e Operação/3.1 Operação/3.1.1. Implantação, rede, segurança e monitoramento/3.1.1.1. Implantação e operação do Storage Gateway — appliance, VM e EC2, rede, segurança, monitoramento e comparação com DataSync|3.1.1.1. Implantação e operação do Storage Gateway — appliance, VM e EC2, rede, segurança, monitoramento e comparação com DataSync]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.1. Amazon S3/0 Amazon S3 (Tópicos )|Amazon S3]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.2. Amazon EBS/0 Amazon EBS (Tópicos )|Amazon EBS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.3. Amazon EFS/0 Amazon EFS (Tópicos )|Amazon EFS]]
