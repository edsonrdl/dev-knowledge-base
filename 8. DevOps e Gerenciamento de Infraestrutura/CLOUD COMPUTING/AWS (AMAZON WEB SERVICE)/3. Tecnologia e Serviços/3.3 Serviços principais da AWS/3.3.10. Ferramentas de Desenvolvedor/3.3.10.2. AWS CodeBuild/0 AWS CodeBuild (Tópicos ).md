# 📚 Guia de Estudos: AWS CodeBuild
#tag #aws #cloud #devtools #codebuild #ci #buildspec #docker

> [!info] Visão Geral
> O AWS CodeBuild é o serviço gerenciado de build e integração contínua da AWS: executa o buildspec em ambientes efêmeros (contêineres, Lambda compute ou frotas reservadas), com cache, artefatos no S3, relatórios de teste e cobertura, e cobrança por minuto. Este guia cobre fundamentos, ambientes e compute, o buildspec.yml, integrações (webhooks, CodePipeline, ECR, CodeArtifact, runners de GitHub Actions), segurança da cadeia de suprimentos e operação (logs, métricas, custos e debugging).

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. CI gerenciado**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.2. AWS CodeBuild/1. Fundamentos/1.1 Visão geral/1.1.1. CI gerenciado/1.1.1.1. O que é AWS CodeBuild — projetos de build, ambientes efêmeros, fontes e artefatos, modelo de preço e quando usar em vez de Jenkins, GitHub Actions ou GitLab CI|1.1.1.1. O que é AWS CodeBuild — projetos de build, ambientes efêmeros, fontes e artefatos, modelo de preço e quando usar em vez de Jenkins, GitHub Actions ou GitLab CI]]

---

## 2 Domínio: Projetos e ambientes

### 2.1 Compute, imagens e rede
- **2.1.1. Ambientes de build**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.2. AWS CodeBuild/2. Projetos e ambientes/2.1 Compute, imagens e rede/2.1.1. Ambientes de build/2.1.1.1. Ambientes do CodeBuild — tipos de compute, imagens gerenciadas e customizadas, Lambda compute, frotas reservadas, VPC, privileged mode, cache e concorrência|2.1.1.1. Ambientes do CodeBuild — tipos de compute, imagens gerenciadas e customizadas, Lambda compute, frotas reservadas, VPC, privileged mode, cache e concorrência]]

---

## 3 Domínio: buildspec

### 3.1 Fases, variáveis e artefatos
- **3.1.1. Sintaxe do buildspec.yml**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.2. AWS CodeBuild/3. buildspec/3.1 Fases, variáveis e artefatos/3.1.1. Sintaxe do buildspec.yml/3.1.1.1. buildspec.yml em profundidade — fases, variáveis, segredos, artefatos, cache, relatórios de teste e cobertura, batch builds e exemplos por linguagem|3.1.1.1. buildspec.yml em profundidade — fases, variáveis, segredos, artefatos, cache, relatórios de teste e cobertura, batch builds e exemplos por linguagem]]

---

## 4 Domínio: Integrações e pipelines

### 4.1 Fontes, webhooks e CodePipeline
- **4.1.1. Triggers e integração**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.2. AWS CodeBuild/4. Integrações e pipelines/4.1 Fontes, webhooks e CodePipeline/4.1.1. Triggers e integração/4.1.1.1. Integrações do CodeBuild — fontes e webhooks, CodePipeline, ECR e builds Docker, CodeArtifact, runners de GitHub Actions, agendamentos e notificações|4.1.1.1. Integrações do CodeBuild — fontes e webhooks, CodePipeline, ECR e builds Docker, CodeArtifact, runners de GitHub Actions, agendamentos e notificações]]

---

## 5 Domínio: Segurança e rede

### 5.1 Roles, segredos e isolamento
- **5.1.1. Menor privilégio e cadeia de suprimentos**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.2. AWS CodeBuild/5. Segurança e rede/5.1 Roles, segredos e isolamento/5.1.1. Menor privilégio e cadeia de suprimentos/5.1.1.1. Segurança do CodeBuild — service role mínima, segredos, VPC e isolamento, imagens confiáveis, cache e artefatos, SBOM e assinatura, e hardening de pipelines de build|5.1.1.1. Segurança do CodeBuild — service role mínima, segredos, VPC e isolamento, imagens confiáveis, cache e artefatos, SBOM e assinatura, e hardening de pipelines de build]]

---

## 6 Domínio: Operação e custos

### 6.1 Logs, métricas, custos e troubleshooting
- **6.1.1. Observabilidade e otimização**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.2. AWS CodeBuild/6. Operação e custos/6.1 Logs, métricas, custos e troubleshooting/6.1.1. Observabilidade e otimização/6.1.1.1. Operação do CodeBuild — logs, métricas e alarmes, quotas, otimização de tempo e custo, debugging com sessão interativa, falhas comuns e checklist de produção|6.1.1.1. Operação do CodeBuild — logs, métricas e alarmes, quotas, otimização de tempo e custo, debugging com sessão interativa, falhas comuns e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.1. AWS CodeCommit/0 AWS CodeCommit (Tópicos )|AWS CodeCommit]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.3. AWS CodeDeploy/0 AWS CodeDeploy (Tópicos )|AWS CodeDeploy]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.4. AWS CodePipeline/0 AWS CodePipeline (Tópicos )|AWS CodePipeline]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.3. Amazon ECS/0 Amazon ECS (Tópicos )|Amazon ECS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.5. AWS CloudFormation/0 AWS CloudFormation (Tópicos )|AWS CloudFormation]]
