# 📚 Guia de Estudos: Amazon ECR
#tag #aws #cloud #containers #ecr #registry #docker #supplychain

> [!info] Visão Geral
> O Amazon Elastic Container Registry (ECR) é o registry gerenciado de imagens de container (OCI/Docker) da AWS, integrado a IAM, KMS, ECS, EKS, Lambda e CodeBuild. Este guia cobre fundamentos (repositórios, tags, digests, privado vs público), push e pull (autenticação, multi-arch, CI), ciclo de vida e pull through cache, replicação e integrações, segurança (policies, scanning, assinatura, VPC endpoints) e operação (quotas, erros, custos).

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Registry de imagens**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.8. Amazon ECR/1. Fundamentos/1.1 Visão geral/1.1.1. Registry de imagens/1.1.1.1. O que é Amazon ECR — repositórios privados e públicos, imagens, tags e digests, OCI, registry e quando usar ECR em vez de Docker Hub|1.1.1.1. O que é Amazon ECR — repositórios privados e públicos, imagens, tags e digests, OCI, registry e quando usar ECR em vez de Docker Hub]]

---

## 2 Domínio: Push e pull

### 2.1 Autenticação e publicação
- **2.1.1. Fluxo de imagens**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.8. Amazon ECR/2. Push e pull/2.1 Autenticação e publicação/2.1.1. Fluxo de imagens/2.1.1.1. Push e pull no ECR — autenticação com get-login-password, build e push, tags e digests, multi-arch, manifest lists, Buildx e fluxo de CI|2.1.1.1. Push e pull no ECR — autenticação com get-login-password, build e push, tags e digests, multi-arch, manifest lists, Buildx e fluxo de CI]]

---

## 3 Domínio: Ciclo de vida e cache

### 3.1 Retenção e pull through cache
- **3.1.1. Limpeza e economia**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.8. Amazon ECR/3. Ciclo de vida e cache/3.1 Retenção e pull through cache/3.1.1. Limpeza e economia/3.1.1.1. Ciclo de vida e pull through cache no ECR — lifecycle policies, tag immutability, limpeza de imagens, espelhos de registries públicos e custos de armazenamento|3.1.1.1. Ciclo de vida e pull through cache no ECR — lifecycle policies, tag immutability, limpeza de imagens, espelhos de registries públicos e custos de armazenamento]]

---

## 4 Domínio: Replicação e integrações

### 4.1 Cross-region, cross-account e serviços
- **4.1.1. Distribuição e consumo**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.8. Amazon ECR/4. Replicação e integrações/4.1 Cross-region, cross-account e serviços/4.1.1. Distribuição e consumo/4.1.1.1. Replicação e integrações do ECR — replicação cross-region e cross-account, ECS, EKS, Lambda, CodeBuild, CodePipeline e EventBridge|4.1.1.1. Replicação e integrações do ECR — replicação cross-region e cross-account, ECS, EKS, Lambda, CodeBuild, CodePipeline e EventBridge]]

---

## 5 Domínio: Segurança e governança

### 5.1 Políticas, scanning e assinatura
- **5.1.1. Proteção da supply chain**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.8. Amazon ECR/5. Segurança e governança/5.1 Políticas, scanning e assinatura/5.1.1. Proteção da supply chain/5.1.1.1. Segurança do ECR — repository policies e IAM, KMS, scanning básico e avançado com Inspector, assinatura de imagens, VPC endpoints e hardening|5.1.1.1. Segurança do ECR — repository policies e IAM, KMS, scanning básico e avançado com Inspector, assinatura de imagens, VPC endpoints e hardening]]

---

## 6 Domínio: Operação e custos

### 6.1 Quotas, erros e custos
- **6.1.1. Observabilidade e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.8. Amazon ECR/6. Operação e custos/6.1 Quotas, erros e custos/6.1.1. Observabilidade e troubleshooting/6.1.1.1. Operação do ECR — quotas, métricas e eventos, erros comuns de push e pull, custos de armazenamento e transferência e checklist de produção|6.1.1.1. Operação do ECR — quotas, métricas e eventos, erros comuns de push e pull, custos de armazenamento e transferência e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.3. Amazon ECS/0 Amazon ECS (Tópicos )|Amazon ECS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.4. Amazon EKS/0 Amazon EKS (Tópicos )|Amazon EKS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.2. AWS Lambda/0 AWS Lambda (Tópicos )|AWS Lambda]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.2. AWS CodeBuild/0 AWS CodeBuild (Tópicos )|AWS CodeBuild]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.4. AWS CodePipeline/0 AWS CodePipeline (Tópicos )|AWS CodePipeline]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.3. Amazon EventBridge/0 Amazon EventBridge (Tópicos )|Amazon EventBridge]]
