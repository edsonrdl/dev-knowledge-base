# 📚 Guia de Estudos: Amazon FSx
#tag #aws #cloud #armazenamento #fsx #windows #lustre #ontap #openzfs

> [!info] Visão Geral
> O Amazon FSx é uma família de sistemas de arquivos gerenciados: FSx for Windows File Server (SMB e Active Directory), FSx for Lustre (HPC e ML com S3), FSx for NetApp ONTAP (multiprotocolo e enterprise) e FSx for OpenZFS (baixa latência, snapshots e clones). Este guia ensina a escolher o sabor certo e a operar cada um.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Família FSx e escolha**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.5. Amazon FSx/1. Fundamentos/1.1 Visão geral/1.1.1. Família FSx e escolha/1.1.1.1. O que é Amazon FSx — a família de sistemas de arquivos gerenciados, comparação com EFS e como escolher|1.1.1.1. O que é Amazon FSx — a família de sistemas de arquivos gerenciados, comparação com EFS e como escolher]]

---

## 2 Domínio: Sistemas de Arquivos

### 2.1 FSx for Windows
- **2.1.1. SMB, Active Directory e DFS**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.5. Amazon FSx/2. Sistemas de Arquivos/2.1 FSx for Windows/2.1.1. SMB, Active Directory e DFS/2.1.1.1. FSx for Windows File Server — SMB, Active Directory, DFS, shadow copies, Multi-AZ e backup|2.1.1.1. FSx for Windows File Server — SMB, Active Directory, DFS, shadow copies, Multi-AZ e backup]]

- **2.1.2. Implantação, migração e operação**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.5. Amazon FSx/2. Sistemas de Arquivos/2.1 FSx for Windows/2.1.2. Implantação, migração e operação/2.1.2.1. FSx for Windows File Server na prática — implantação, migração com DataSync e Robocopy, administração por PowerShell, cotas, shadow copies, desempenho e troubleshooting|2.1.2.1. FSx for Windows File Server na prática — implantação, migração com DataSync e Robocopy, administração por PowerShell, cotas, shadow copies, desempenho e troubleshooting]]

### 2.2 FSx for Lustre
- **2.2.1. HPC, S3 e deployment types**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.5. Amazon FSx/2. Sistemas de Arquivos/2.2 FSx for Lustre/2.2.1. HPC, S3 e deployment types/2.2.1.1. FSx for Lustre — computação de alto desempenho, integração com S3, scratch e persistent|2.2.1.1. FSx for Lustre — computação de alto desempenho, integração com S3, scratch e persistent]]

- **2.2.2. Data repository, tuning e integrações**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.5. Amazon FSx/2. Sistemas de Arquivos/2.2 FSx for Lustre/2.2.2. Data repository, tuning e integrações/2.2.2.1. FSx for Lustre na prática — Data Repository Associations, striping, tuning do cliente, integração com Batch, ParallelCluster e SageMaker, e custo|2.2.2.1. FSx for Lustre na prática — Data Repository Associations, striping, tuning do cliente, integração com Batch, ParallelCluster e SageMaker, e custo]]

### 2.3 FSx for ONTAP e OpenZFS
- **2.3.1. Multiprotocolo, snapshots e tiering**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.5. Amazon FSx/2. Sistemas de Arquivos/2.3 FSx for ONTAP e OpenZFS/2.3.1. Multiprotocolo, snapshots e tiering/2.3.1.1. FSx for NetApp ONTAP e FSx for OpenZFS — multiprotocolo, snapshots, clones, tiering e replicação|2.3.1.1. FSx for NetApp ONTAP e FSx for OpenZFS — multiprotocolo, snapshots, clones, tiering e replicação]]

- **2.3.2. ONTAP em profundidade**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.5. Amazon FSx/2. Sistemas de Arquivos/2.3 FSx for ONTAP e OpenZFS/2.3.2. ONTAP em profundidade/2.3.2.1. FSx for NetApp ONTAP em profundidade — SVMs, volumes FlexVol e FlexGroup, tiering, SnapMirror, FlexClone, iSCSI e NVMe, e operação|2.3.2.1. FSx for NetApp ONTAP em profundidade — SVMs, volumes FlexVol e FlexGroup, tiering, SnapMirror, FlexClone, iSCSI e NVMe, e operação]]
- **2.3.3. OpenZFS em profundidade**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.5. Amazon FSx/2. Sistemas de Arquivos/2.3 FSx for ONTAP e OpenZFS/2.3.3. OpenZFS em profundidade/2.3.3.1. FSx for OpenZFS em profundidade — volumes, snapshots, clones, compressão, cotas, replicação e comparação com ONTAP|2.3.3.1. FSx for OpenZFS em profundidade — volumes, snapshots, clones, compressão, cotas, replicação e comparação com ONTAP]]

---

## 3 Domínio: Operação e Custo

### 3.1 Segurança, Monitoramento e Custo
- **3.1.1. Rede, criptografia, backups, métricas e FinOps**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.5. Amazon FSx/3. Operação e Custo/3.1 Segurança, Monitoramento e Custo/3.1.1. Rede, criptografia, backups, métricas e FinOps/3.1.1.1. Segurança, backup, monitoramento e custo no FSx — rede, criptografia, backups, métricas por sabor, comparação de preços e checklist FinOps|3.1.1.1. Segurança, backup, monitoramento e custo no FSx — rede, criptografia, backups, métricas por sabor, comparação de preços e checklist FinOps]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.3. Amazon EFS/0 Amazon EFS (Tópicos )|Amazon EFS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.4. AWS Storage Gateway/0 AWS Storage Gateway (Tópicos )|AWS Storage Gateway]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.1. Amazon S3/0 Amazon S3 (Tópicos )|Amazon S3]]
