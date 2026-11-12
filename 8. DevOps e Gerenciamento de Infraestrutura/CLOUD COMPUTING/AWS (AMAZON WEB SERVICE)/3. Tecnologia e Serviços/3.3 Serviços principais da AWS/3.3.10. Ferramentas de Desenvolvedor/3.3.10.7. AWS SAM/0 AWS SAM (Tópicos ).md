# 📚 Guia de Estudos: AWS SAM
#tag #aws #cloud #devtools #sam #serverless #cloudformation #lambda #iac #cicd
 
> [!info] Visão Geral
> O AWS Serverless Application Model (SAM) é uma extensão do CloudFormation para aplicações serverless: um template curto (Transform `AWS::Serverless-2016-10-31`) que o CloudFormation expande em recursos nativos, mais a SAM CLI para criar, compilar, testar localmente, implantar e depurar. Este guia cobre fundamentos e comparação com CDK/CloudFormation, o template em detalhe (Globals, Function, Api, HttpApi, SimpleTable, políticas), a SAM CLI (init, build, deploy, samconfig.toml, sync, logs, pipeline), eventos, APIs e deploy gradual (AutoPublishAlias, DeploymentPreference, CodeDeploy), segurança e governança (privilégio mínimo, boundary, segredos, cfn-guard, drift) e operação (erros, rollback, limites).

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Conceito e ecossistema**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.7. AWS SAM/1. Fundamentos/1.1 Visão geral/1.1.1. Conceito e ecossistema/1.1.1.1. AWS SAM — o que é, Transform serverless sobre CloudFormation, SAM CLI, recursos principais e quando usar SAM versus CDK e CloudFormation puro|1.1.1.1. AWS SAM — o que é, Transform serverless sobre CloudFormation, SAM CLI, recursos principais e quando usar SAM versus CDK e CloudFormation puro]]

---

## 2 Domínio: Template SAM

### 2.1 Recursos e propriedades
- **2.1.1. Anatomia do template**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.7. AWS SAM/2. Template SAM/2.1 Recursos e propriedades/2.1.1. Anatomia do template/2.1.1.1. Template SAM em detalhe — Globals, Function, Api e HttpApi, SimpleTable, LayerVersion, StateMachine, eventos, políticas gerenciadas, parâmetros, Outputs e funções intrínsecas|2.1.1.1. Template SAM em detalhe — Globals, Function, Api e HttpApi, SimpleTable, LayerVersion, StateMachine, eventos, políticas gerenciadas, parâmetros, Outputs e funções intrínsecas]]

---

## 3 Domínio: SAM CLI

### 3.1 Ciclo de desenvolvimento e deploy
- **3.1.1. Comandos principais**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.7. AWS SAM/3. SAM CLI/3.1 Ciclo de desenvolvimento e deploy/3.1.1. Comandos principais/3.1.1.1. SAM CLI no dia a dia — init, build, validate, deploy, samconfig.toml, sync e accelerate, logs, traces, delete e pipelines|3.1.1.1. SAM CLI no dia a dia — init, build, validate, deploy, samconfig.toml, sync e accelerate, logs, traces, delete e pipelines]]

---

## 4 Domínio: Eventos, API e deploy gradual

### 4.1 Integrações e releases seguros
- **4.1.1. Fontes de evento e deployment preferences**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.7. AWS SAM/4. Eventos, API e deploy gradual/4.1 Integrações e releases seguros/4.1.1. Fontes de evento e deployment preferences/4.1.1.1. Eventos, API e deploy gradual no SAM — fontes de evento, autorizadores, CORS, layers, AutoPublishAlias, DeploymentPreference, hooks do CodeDeploy e alarmes de rollback|4.1.1.1. Eventos, API e deploy gradual no SAM — fontes de evento, autorizadores, CORS, layers, AutoPublishAlias, DeploymentPreference, hooks do CodeDeploy e alarmes de rollback]]

---

## 5 Domínio: Segurança e governança

### 5.1 IAM, segredos e conformidade
- **5.1.1. Controle de infraestrutura serverless**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.7. AWS SAM/5. Segurança e governança/5.1 IAM, segredos e conformidade/5.1.1. Controle de infraestrutura serverless/5.1.1.1. Segurança e governança no SAM — políticas mínimas, capabilities, boundary, segredos, assinatura de código, validação com cfn-lint e cfn-guard, drift e contas separadas|5.1.1.1. Segurança e governança no SAM — políticas mínimas, capabilities, boundary, segredos, assinatura de código, validação com cfn-lint e cfn-guard, drift e contas separadas]]

---

## 6 Domínio: Operação e troubleshooting

### 6.1 Erros, limites e boas práticas
- **6.1.1. Diagnóstico e manutenção**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.7. AWS SAM/6. Operação e troubleshooting/6.1 Erros, limites e boas práticas/6.1.1. Diagnóstico e manutenção/6.1.1.1. Operação e troubleshooting do SAM — erros de build e deploy, rollback, change sets, limites do template, sam sync em produção, logs e checklist de equipe|6.1.1.1. Operação e troubleshooting do SAM — erros de build e deploy, rollback, change sets, limites do template, sam sync em produção, logs e checklist de equipe]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.6. Testes e mocks para aplicações AWS/0 Testes e mocks para aplicações AWS (Tópicos )|Testes e mocks para aplicações AWS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.8. AWS X-Ray/0 AWS X-Ray (Tópicos )|AWS X-Ray]]
