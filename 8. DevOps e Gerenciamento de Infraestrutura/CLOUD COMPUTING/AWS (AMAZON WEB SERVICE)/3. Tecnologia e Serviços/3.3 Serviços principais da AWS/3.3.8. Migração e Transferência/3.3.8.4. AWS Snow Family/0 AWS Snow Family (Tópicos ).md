# 📚 Guia de Estudos: AWS Snow Family
#tag #aws #cloud #migracao #snow #snowball #edge #transferencia-offline

> [!info] Visão Geral
> A AWS Snow Family é a família de dispositivos físicos, robustos e criptografados para transferência offline de grandes volumes de dados para a AWS (e da AWS) e para computação e armazenamento na borda, inclusive sem conectividade. Este guia cobre fundamentos, dispositivos e capacidades (Snowcone, Snowball Edge, Snowmobile — com ressalva de disponibilidade), o fluxo de um job, computação na borda e clusters, planejamento e decisão (break-even entre rede e Snow) e segurança e operação.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Transferência offline e computação na borda**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.4. AWS Snow Family/1. Fundamentos/1.1 Visão geral/1.1.1. Transferência offline e computação na borda/1.1.1.1. O que é AWS Snow Family — transferência offline de dados, computação na borda, tipos de job, ciclo de vida de um dispositivo e quando usar Snow em vez de rede|1.1.1.1. O que é AWS Snow Family — transferência offline de dados, computação na borda, tipos de job, ciclo de vida de um dispositivo e quando usar Snow em vez de rede]]

---

## 2 Domínio: Dispositivos e capacidades

### 2.1 Snowcone, Snowball Edge e Snowmobile
- **2.1.1. Modelos, especificações e escolha**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.4. AWS Snow Family/2. Dispositivos e capacidades/2.1 Snowcone, Snowball Edge e Snowmobile/2.1.1. Modelos, especificações e escolha/2.1.1.1. Dispositivos da Snow Family — Snowcone, Snowball Edge Storage e Compute Optimized, Snowmobile, especificações, interfaces de rede, capacidade útil e como escolher o modelo|2.1.1.1. Dispositivos da Snow Family — Snowcone, Snowball Edge Storage e Compute Optimized, Snowmobile, especificações, interfaces de rede, capacidade útil e como escolher o modelo]]

---

## 3 Domínio: Fluxo de um job

### 3.1 Importação e exportação
- **3.1.1. Pedido, cópia, envio e ingestão**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.4. AWS Snow Family/3. Fluxo de um job/3.1 Importação e exportação/3.1.1. Pedido, cópia, envio e ingestão/3.1.1.1. O fluxo de um job Snow — criar o job, receber e desbloquear o dispositivo, copiar dados com S3 adapter e NFS, devolução, ingestão no S3, job report e exportação|3.1.1.1. O fluxo de um job Snow — criar o job, receber e desbloquear o dispositivo, copiar dados com S3 adapter e NFS, devolução, ingestão no S3, job report e exportação]]

---

## 4 Domínio: Computação na borda e clusters

### 4.1 EC2, Lambda e clusters
- **4.1.1. Edge computing, storage local e clusters**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.4. AWS Snow Family/4. Computação na borda e clusters/4.1 EC2, Lambda e clusters/4.1.1. Edge computing, storage local e clusters/4.1.1.1. Computação na borda com Snow — EC2 e Lambda locais, volumes e S3 local, clusters de Snowball Edge, operação desconectada, GPU e casos de uso|4.1.1.1. Computação na borda com Snow — EC2 e Lambda locais, volumes e S3 local, clusters de Snowball Edge, operação desconectada, GPU e casos de uso]]

---

## 5 Domínio: Planejamento e decisão

### 5.1 Online vs offline e custo
- **5.1.1. Break-even, estratégias híbridas e logística**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.4. AWS Snow Family/5. Planejamento e decisão/5.1 Online vs offline e custo/5.1.1. Break-even, estratégias híbridas e logística/5.1.1.1. Planejamento e decisão com Snow — break-even entre rede e Snow, estratégias híbridas com DataSync, custos, logística e alfândega, ondas de dispositivos e comparação com Direct Connect|5.1.1.1. Planejamento e decisão com Snow — break-even entre rede e Snow, estratégias híbridas com DataSync, custos, logística e alfândega, ondas de dispositivos e comparação com Direct Connect]]

---

## 6 Domínio: Segurança e operação

### 6.1 Criptografia, acesso e troubleshooting
- **6.1.1. KMS, cadeia de custódia, IAM, monitoramento e checklist**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.4. AWS Snow Family/6. Segurança e operação/6.1 Criptografia, acesso e troubleshooting/6.1.1. KMS, cadeia de custódia, IAM, monitoramento e checklist/6.1.1.1. Segurança e operação da Snow Family — criptografia com KMS, cadeia de custódia, IAM e roles, monitoramento com OpsHub e SNS, sanitização, conformidade e checklist de job|6.1.1.1. Segurança e operação da Snow Family — criptografia com KMS, cadeia de custódia, IAM e roles, monitoramento com OpsHub e SNS, sanitização, conformidade e checklist de job]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.1. AWS Migration Hub/0 AWS Migration Hub (Tópicos )|AWS Migration Hub]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.2. AWS Database Migration Service/0 AWS Database Migration Service (Tópicos )|AWS Database Migration Service]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.3. AWS DataSync/0 AWS DataSync (Tópicos )|AWS DataSync]]
