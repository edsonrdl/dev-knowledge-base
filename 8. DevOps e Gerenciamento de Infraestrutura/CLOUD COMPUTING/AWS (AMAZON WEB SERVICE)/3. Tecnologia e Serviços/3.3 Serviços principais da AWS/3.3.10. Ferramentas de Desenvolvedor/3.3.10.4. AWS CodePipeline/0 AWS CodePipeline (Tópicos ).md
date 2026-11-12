# 📚 Guia de Estudos: AWS CodePipeline
#tag #aws #cloud #devtools #codepipeline #cd #pipeline #cicd

> [!info] Visão Geral
> O AWS CodePipeline é o serviço gerenciado de entrega contínua da AWS: orquestra estágios e ações (Source, Build, Test, Deploy, Approval) com artefatos no S3, integrando CodeBuild, CodeDeploy, CloudFormation, ECS, Lambda e fontes como CodeCommit, GitHub, GitLab e Bitbucket. O tipo V2 traz gatilhos por branch, tag e caminho, variáveis, modos de execução, condições de estágio, rollback e ação Commands. Este guia cobre fundamentos, estrutura de ações, pipelines V2, padrões de entrega (multi-conta, multi-região, IaC, CDK Pipelines), segurança e operação.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Entrega contínua orquestrada**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.4. AWS CodePipeline/1. Fundamentos/1.1 Visão geral/1.1.1. Entrega contínua orquestrada/1.1.1.1. O que é AWS CodePipeline — pipelines, stages, actions e artefatos, tipos V1 e V2, modos de execução, integrações e quando usar em vez de GitHub Actions, GitLab CI e Jenkins|1.1.1.1. O que é AWS CodePipeline — pipelines, stages, actions e artefatos, tipos V1 e V2, modos de execução, integrações e quando usar em vez de GitHub Actions, GitLab CI e Jenkins]]

---

## 2 Domínio: Estrutura e ações

### 2.1 Source, Build, Test, Deploy e Approval
- **2.1.1. Categorias de ação e artefatos**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.4. AWS CodePipeline/2. Estrutura e ações/2.1 Source, Build, Test, Deploy e Approval/2.1.1. Categorias de ação e artefatos/2.1.1.1. Estágios e ações no CodePipeline — fontes, build, teste, deploy e aprovação, artefatos e variáveis, runOrder, namespaces, ações customizadas e exemplos de pipelines|2.1.1.1. Estágios e ações no CodePipeline — fontes, build, teste, deploy e aprovação, artefatos e variáveis, runOrder, namespaces, ações customizadas e exemplos de pipelines]]

---

## 3 Domínio: V2, gatilhos e execução

### 3.1 Triggers, variáveis e modos
- **3.1.1. Pipeline V2**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.4. AWS CodePipeline/3. V2, gatilhos e execução/3.1 Triggers, variáveis e modos/3.1.1. Pipeline V2/3.1.1.1. Pipelines V2 no CodePipeline — gatilhos por branch, tag e caminho, variáveis de pipeline, modos superseded, queued e parallel, condições de estágio, rollback e ação Commands|3.1.1.1. Pipelines V2 no CodePipeline — gatilhos por branch, tag e caminho, variáveis de pipeline, modos superseded, queued e parallel, condições de estágio, rollback e ação Commands]]

---

## 4 Domínio: Padrões de entrega

### 4.1 Ambientes, multi-conta e IaC
- **4.1.1. Pipelines de aplicação e de infraestrutura**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.4. AWS CodePipeline/4. Padrões de entrega/4.1 Ambientes, multi-conta e IaC/4.1.1. Pipelines de aplicação e de infraestrutura/4.1.1.1. Padrões de pipelines no CodePipeline — dev, homologação e produção, multi-conta e multi-região, CloudFormation e CDK Pipelines, imagens e serverless e pipelines de pipelines|4.1.1.1. Padrões de pipelines no CodePipeline — dev, homologação e produção, multi-conta e multi-região, CloudFormation e CDK Pipelines, imagens e serverless e pipelines de pipelines]]

---

## 5 Domínio: Segurança e governança

### 5.1 Roles, artefatos e aprovações
- **5.1.1. Controle de acesso e supply chain**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.4. AWS CodePipeline/5. Segurança e governança/5.1 Roles, artefatos e aprovações/5.1.1. Controle de acesso e supply chain/5.1.1.1. Segurança do CodePipeline — roles por ação, bucket de artefatos e KMS, aprovações e segregação de funções, conexões e segredos, supply chain e hardening de pipelines|5.1.1.1. Segurança do CodePipeline — roles por ação, bucket de artefatos e KMS, aprovações e segregação de funções, conexões e segredos, supply chain e hardening de pipelines]]

---

## 6 Domínio: Operação e custos

### 6.1 Monitoramento, falhas e custos
- **6.1.1. Observabilidade e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.4. AWS CodePipeline/6. Operação e custos/6.1 Monitoramento, falhas e custos/6.1.1. Observabilidade e troubleshooting/6.1.1.1. Operação do CodePipeline — execuções e estados, eventos e notificações, falhas comuns, reexecução, quotas, custos V1 vs V2, métricas DORA e checklist de produção|6.1.1.1. Operação do CodePipeline — execuções e estados, eventos e notificações, falhas comuns, reexecução, quotas, custos V1 vs V2, métricas DORA e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.1. AWS CodeCommit/0 AWS CodeCommit (Tópicos )|AWS CodeCommit]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.2. AWS CodeBuild/0 AWS CodeBuild (Tópicos )|AWS CodeBuild]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.3. AWS CodeDeploy/0 AWS CodeDeploy (Tópicos )|AWS CodeDeploy]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.5. AWS CloudFormation/0 AWS CloudFormation (Tópicos )|AWS CloudFormation]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.3. Amazon EventBridge/0 Amazon EventBridge (Tópicos )|Amazon EventBridge]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.4. AWS Step Functions/0 AWS Step Functions (Tópicos )|AWS Step Functions]]
