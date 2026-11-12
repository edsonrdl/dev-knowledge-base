# 📚 Guia de Estudos: AWS DataSync
#tag #aws #cloud #migracao #datasync #transferencia-de-dados #nfs #smb #s3

> [!info] Visão Geral
> O AWS DataSync é o serviço gerenciado de transferência online de dados: copia arquivos e objetos em massa, de forma incremental e com verificação de integridade, entre storage local (NFS, SMB, HDFS, object storage, outras nuvens) e a AWS (S3, EFS, FSx), ou entre serviços AWS. Este guia cobre fundamentos, agents e locations, tarefas e execução, desempenho e rede, cenários e alternativas (Transfer Family, Storage Gateway, Snow Family) e segurança e operação.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Transferência online de dados**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.3. AWS DataSync/1. Fundamentos/1.1 Visão geral/1.1.1. Transferência online de dados/1.1.1.1. O que é AWS DataSync — transferência online de dados, agent, locations, tasks, origens e destinos suportados e quando usar DataSync vs rsync, Snow Family e Transfer Family|1.1.1.1. O que é AWS DataSync — transferência online de dados, agent, locations, tasks, origens e destinos suportados e quando usar DataSync vs rsync, Snow Family e Transfer Family]]

---

## 2 Domínio: Agentes e locations

### 2.1 Agentes, locations e conectividade
- **2.1.1. Agent, locations e endpoints**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.3. AWS DataSync/2. Agentes e locations/2.1 Agentes, locations e conectividade/2.1.1. Agent, locations e endpoints/2.1.1.1. Agentes e locations no DataSync — implantação do agent, ativação, endpoints públicos e VPC, locations NFS, SMB, HDFS, S3, EFS e FSx e requisitos de rede|2.1.1.1. Agentes e locations no DataSync — implantação do agent, ativação, endpoints públicos e VPC, locations NFS, SMB, HDFS, S3, EFS e FSx e requisitos de rede]]

---

## 3 Domínio: Tarefas e execução

### 3.1 Configuração e agendamento
- **3.1.1. Opções, filtros, modos e relatórios**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.3. AWS DataSync/3. Tarefas e execução/3.1 Configuração e agendamento/3.1.1. Opções, filtros, modos e relatórios/3.1.1.1. Tarefas no DataSync — opções de transferência e verificação, filtros include e exclude, agendamento, modos Basic e Enhanced, task reports e execuções incrementais|3.1.1.1. Tarefas no DataSync — opções de transferência e verificação, filtros include e exclude, agendamento, modos Basic e Enhanced, task reports e execuções incrementais]]

---

## 4 Domínio: Desempenho e rede

### 4.1 Throughput e otimização
- **4.1.1. Largura de banda, paralelismo e gargalos**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.3. AWS DataSync/4. Desempenho e rede/4.1 Throughput e otimização/4.1.1. Largura de banda, paralelismo e gargalos/4.1.1.1. Desempenho e rede no DataSync — dimensionamento de banda, throughput por tarefa, gargalos de agent, origem e destino, Direct Connect, limites de banda e planejamento de cargas grandes|4.1.1.1. Desempenho e rede no DataSync — dimensionamento de banda, throughput por tarefa, gargalos de agent, origem e destino, Direct Connect, limites de banda e planejamento de cargas grandes]]

---

## 5 Domínio: Cenários e alternativas

### 5.1 Casos de uso e comparações
- **5.1.1. Migração de NAS, S3 entre contas e arquivamento híbrido**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.3. AWS DataSync/5. Cenários e alternativas/5.1 Casos de uso e comparações/5.1.1. Migração de NAS, S3 entre contas e arquivamento híbrido/5.1.1.1. Cenários práticos com DataSync — NAS para S3 e FSx, Hadoop para S3, S3 entre contas e regiões, EFS entre regiões, multi-nuvem e comparação com Transfer Family, Storage Gateway e Snow Family|5.1.1.1. Cenários práticos com DataSync — NAS para S3 e FSx, Hadoop para S3, S3 entre contas e regiões, EFS entre regiões, multi-nuvem e comparação com Transfer Family, Storage Gateway e Snow Family]]

---

## 6 Domínio: Segurança e operação

### 6.1 Acesso, monitoramento e custo
- **6.1.1. IAM, criptografia, métricas, custos e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.3. AWS DataSync/6. Segurança e operação/6.1 Acesso, monitoramento e custo/6.1.1. IAM, criptografia, métricas, custos e troubleshooting/6.1.1.1. Segurança e operação do DataSync — IAM e roles de location, criptografia, VPC endpoints, CloudWatch e EventBridge, custos, quotas, IaC e checklist de transferência|6.1.1.1. Segurança e operação do DataSync — IAM e roles de location, criptografia, VPC endpoints, CloudWatch e EventBridge, custos, quotas, IaC e checklist de transferência]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.1. AWS Migration Hub/0 AWS Migration Hub (Tópicos )|AWS Migration Hub]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.2. AWS Database Migration Service/0 AWS Database Migration Service (Tópicos )|AWS Database Migration Service]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.4. AWS Glue/0 AWS Glue (Tópicos )|AWS Glue]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.3. Amazon EventBridge/0 Amazon EventBridge (Tópicos )|Amazon EventBridge]]
