# 📚 Guia de Estudos: AWS Service Catalog
#tag #aws #cloud #governanca #servicecatalog #autoatendimento

> [!info] Visão Geral
> O AWS Service Catalog permite criar um catálogo de produtos de TI aprovados (templates de infraestrutura) e oferecê-los em autoatendimento, com governança embutida: launch roles de menor privilégio, parâmetros restritos, tags obrigatórias, versões e controle de custo. Este guia cobre os fundamentos, os produtos e seu ciclo de vida, a governança (constraints, TagOptions, acesso, budgets), o uso em várias contas (compartilhamento, AppRegistry, ServiceNow/Jira), o catálogo como código (pipelines, Terraform) e a operação.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Conceitos e arquitetura**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.6. AWS Service Catalog/1. Fundamentos/1.1 Visão geral/1.1.1. Conceitos e arquitetura/1.1.1.1. O que é AWS Service Catalog — catálogo de produtos aprovados, portfolios, products, autoatendimento governado e quando usar|1.1.1.1. O que é AWS Service Catalog — catálogo de produtos aprovados, portfolios, products, autoatendimento governado e quando usar]]

---

## 2 Domínio: Produtos

### 2.1 Products e versões
- **2.1.1. Criação, versionamento e ciclo de vida**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.6. AWS Service Catalog/2. Produtos/2.1 Products e versões/2.1.1. Criação, versionamento e ciclo de vida/2.1.1.1. Products no Service Catalog — templates, versões, provisioned products, atualização, encerramento, service actions e provisioned product plans|2.1.1.1. Products no Service Catalog — templates, versões, provisioned products, atualização, encerramento, service actions e provisioned product plans]]

---

## 3 Domínio: Governança

### 3.1 Constraints, acesso e tags
- **3.1.1. Launch roles, template rules e TagOptions**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.6. AWS Service Catalog/3. Governança/3.1 Constraints, acesso e tags/3.1.1. Launch roles, template rules e TagOptions/3.1.1.1. Governança no Service Catalog — constraints de launch, template, notification e StackSet, launch roles, TagOptions, acesso e budgets|3.1.1.1. Governança no Service Catalog — constraints de launch, template, notification e StackSet, launch roles, TagOptions, acesso e budgets]]

---

## 4 Domínio: Multi-conta

### 4.1 Compartilhamento e integrações
- **4.1.1. Share, Organizations, AppRegistry e ITSM**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.6. AWS Service Catalog/4. Multi-conta/4.1 Compartilhamento e integrações/4.1.1. Share, Organizations, AppRegistry e ITSM/4.1.1.1. Service Catalog em várias contas — compartilhamento de portfolios, Organizations, imports, AppRegistry e integrações com ServiceNow e Jira|4.1.1.1. Service Catalog em várias contas — compartilhamento de portfolios, Organizations, imports, AppRegistry e integrações com ServiceNow e Jira]]

---

## 5 Domínio: Automação e pipelines

### 5.1 Catálogo como código
- **5.1.1. IaC, CI-CD, Terraform e APIs**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.6. AWS Service Catalog/5. Automação e pipelines/5.1 Catálogo como código/5.1.1. IaC, CI-CD, Terraform e APIs/5.1.1.1. Catálogo como código — CloudFormation, pipelines de publicação, Terraform engines, CLI e API, testes e ciclo de vida de versões|5.1.1.1. Catálogo como código — CloudFormation, pipelines de publicação, Terraform engines, CLI e API, testes e ciclo de vida de versões]]

---

## 6 Domínio: Operação

### 6.1 Custo, segurança e diagnóstico
- **6.1.1. Segurança, custos e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.6. AWS Service Catalog/6. Operação/6.1 Custo, segurança e diagnóstico/6.1.1. Segurança, custos e troubleshooting/6.1.1.1. Operando o Service Catalog — segurança, custos, métricas de adoção, troubleshooting e checklist de produção|6.1.1.1. Operando o Service Catalog — segurança, custos, métricas de adoção, troubleshooting e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.5. AWS CloudFormation/0 AWS CloudFormation (Tópicos )|AWS CloudFormation]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.4. AWS Systems Manager/0 AWS Systems Manager (Tópicos )|AWS Systems Manager]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.3. AWS Config/0 AWS Config (Tópicos )|AWS Config]]
