# 📚 Guia de Estudos: AWS Systems Manager
#tag #aws #cloud #operacoes #systemsmanager #ssm #automacao

> [!info] Visão Geral
> O AWS Systems Manager é o hub operacional da AWS para visualizar e controlar a frota de servidores (EC2, on-premises e outras nuvens) sem SSH, executar comandos em massa, aplicar patches, guardar configurações e segredos, automatizar rotinas e responder a incidentes. Este guia cobre os fundamentos e o SSM Agent, o acesso e execução (Session Manager e Run Command), o Parameter Store, a manutenção da frota (Patch Manager, State Manager, Inventory), a automação e operações (Automation, Change Manager, OpsCenter, Incident Manager) e a operação segura e econômica.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Capacidades e arquitetura**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.4. AWS Systems Manager/1. Fundamentos/1.1 Visão geral/1.1.1. Capacidades e arquitetura/1.1.1.1. O que é AWS Systems Manager — hub operacional, SSM Agent, managed nodes, role IAM, hybrid activations e mapa de capacidades|1.1.1.1. O que é AWS Systems Manager — hub operacional, SSM Agent, managed nodes, role IAM, hybrid activations e mapa de capacidades]]

---

## 2 Domínio: Acesso e execução

### 2.1 Session Manager e Run Command
- **2.1.1. Acesso sem SSH e execução em massa**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.4. AWS Systems Manager/2. Acesso e execução/2.1 Session Manager e Run Command/2.1.1. Acesso sem SSH e execução em massa/2.1.1.1. Session Manager e Run Command — acesso sem SSH, port forwarding, logs de sessão, execução em massa, rate control e saída de comandos|2.1.1.1. Session Manager e Run Command — acesso sem SSH, port forwarding, logs de sessão, execução em massa, rate control e saída de comandos]]

---

## 3 Domínio: Configuração

### 3.1 Parameter Store
- **3.1.1. Parâmetros, SecureString e hierarquia**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.4. AWS Systems Manager/3. Configuração/3.1 Parameter Store/3.1.1. Parâmetros, SecureString e hierarquia/3.1.1.1. Parameter Store — tipos de parâmetro, hierarquia, SecureString com KMS, versões, políticas, integrações e comparação com Secrets Manager|3.1.1.1. Parameter Store — tipos de parâmetro, hierarquia, SecureString com KMS, versões, políticas, integrações e comparação com Secrets Manager]]

---

## 4 Domínio: Manutenção da frota

### 4.1 Patch, estado e inventário
- **4.1.1. Patch Manager, State Manager e Inventory**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.4. AWS Systems Manager/4. Manutenção da frota/4.1 Patch, estado e inventário/4.1.1. Patch Manager, State Manager e Inventory/4.1.1.1. Manutenção da frota — Patch Manager, patch baselines, maintenance windows, State Manager, Inventory e Compliance|4.1.1.1. Manutenção da frota — Patch Manager, patch baselines, maintenance windows, State Manager, Inventory e Compliance]]

---

## 5 Domínio: Automação e operações

### 5.1 Automation e OpsCenter
- **5.1.1. Runbooks, aprovações e itens operacionais**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.4. AWS Systems Manager/5. Automação e operações/5.1 Automation e OpsCenter/5.1.1. Runbooks, aprovações e itens operacionais/5.1.1.1. Automation e operações — runbooks, aprovação, execução multi-conta, Change Manager, OpsCenter, Explorer e Incident Manager|5.1.1.1. Automation e operações — runbooks, aprovação, execução multi-conta, Change Manager, OpsCenter, Explorer e Incident Manager]]

---

## 6 Domínio: Operação

### 6.1 Custo, segurança e troubleshooting
- **6.1.1. Segurança, custos e diagnóstico**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.4. AWS Systems Manager/6. Operação/6.1 Custo, segurança e troubleshooting/6.1.1. Segurança, custos e diagnóstico/6.1.1.1. Operando o Systems Manager — segurança, custos, Quick Setup, multi-conta, troubleshooting de nós offline e checklist de produção|6.1.1.1. Operando o Systems Manager — segurança, custos, Quick Setup, multi-conta, troubleshooting de nós offline e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.1. Computação/3.3.1.1. Amazon EC2/0 Amazon EC2 (Tópicos )|Amazon EC2]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.1. AWS CloudWatch/0 AWS CloudWatch (Tópicos )|AWS CloudWatch]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.2. AWS CloudTrail/0 AWS CloudTrail (Tópicos )|AWS CloudTrail]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.3. AWS Config/0 AWS Config (Tópicos )|AWS Config]]
