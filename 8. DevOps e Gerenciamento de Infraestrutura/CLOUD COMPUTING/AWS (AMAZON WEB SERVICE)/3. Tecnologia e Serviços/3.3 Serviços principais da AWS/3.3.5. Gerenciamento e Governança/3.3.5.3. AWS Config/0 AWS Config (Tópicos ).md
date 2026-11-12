# 📚 Guia de Estudos: AWS Config
#tag #aws #cloud #governanca #config #conformidade

> [!info] Visão Geral
> O AWS Config registra e avalia a configuração dos recursos AWS ao longo do tempo, respondendo como um recurso está configurado, como estava antes e se está em conformidade com as políticas. Este guia cobre os fundamentos (configuration items e diferença para CloudTrail/CloudWatch), a gravação (recorder, delivery channel, advanced queries, custo), as regras (managed, Lambda, Guard, conformance packs), a remediação (SSM Automation e EventBridge), a governança multi-conta (aggregators e organization packs) e a operação.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Conceitos e componentes**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.3. AWS Config/1. Fundamentos/1.1 Visão geral/1.1.1. Conceitos e componentes/1.1.1.1. O que é AWS Config — configuration items, histórico de configuração, avaliação de conformidade e diferença para CloudTrail e CloudWatch|1.1.1.1. O que é AWS Config — configuration items, histórico de configuração, avaliação de conformidade e diferença para CloudTrail e CloudWatch]]

---

## 2 Domínio: Gravação

### 2.1 Recorder e entrega
- **2.1.1. Recorder, delivery channel e consultas**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.3. AWS Config/2. Gravação/2.1 Recorder e entrega/2.1.1. Recorder, delivery channel e consultas/2.1.1.1. Gravação no AWS Config — configuration recorder, escopo de recursos, delivery channel, snapshots, advanced queries e custo por item|2.1.1.1. Gravação no AWS Config — configuration recorder, escopo de recursos, delivery channel, snapshots, advanced queries e custo por item]]

---

## 3 Domínio: Regras

### 3.1 Config rules
- **3.1.1. Managed rules, custom rules e Guard**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.3. AWS Config/3. Regras/3.1 Config rules/3.1.1. Managed rules, custom rules e Guard/3.1.1.1. Config rules — regras gerenciadas, custom com Lambda e Guard, gatilhos, escopo, avaliação de conformidade e conformance packs|3.1.1.1. Config rules — regras gerenciadas, custom com Lambda e Guard, gatilhos, escopo, avaliação de conformidade e conformance packs]]

---

## 4 Domínio: Remediação

### 4.1 Remediação e eventos
- **4.1.1. SSM Automation, EventBridge e notificações**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.3. AWS Config/4. Remediação/4.1 Remediação e eventos/4.1.1. SSM Automation, EventBridge e notificações/4.1.1.1. Remediação no AWS Config — SSM Automation, remediação automática e manual, EventBridge, notificações e limites da automação|4.1.1.1. Remediação no AWS Config — SSM Automation, remediação automática e manual, EventBridge, notificações e limites da automação]]

---

## 5 Domínio: Governança multi-conta

### 5.1 Aggregators e organização
- **5.1.1. Visão consolidada e implantação em escala**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.3. AWS Config/5. Governança multi-conta/5.1 Aggregators e organização/5.1.1. Visão consolidada e implantação em escala/5.1.1.1. Config em várias contas — aggregators, AWS Organizations, organization rules, Control Tower, Security Hub e relatórios de conformidade|5.1.1.1. Config em várias contas — aggregators, AWS Organizations, organization rules, Control Tower, Security Hub e relatórios de conformidade]]

---

## 6 Domínio: Operação

### 6.1 Custo e boas práticas
- **6.1.1. Custos, IAM e checklist**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.3. AWS Config/6. Operação/6.1 Custo e boas práticas/6.1.1. Custos, IAM e checklist/6.1.1.1. Operando o AWS Config — custos, permissões, investigação de mudanças, boas práticas e checklist de produção|6.1.1.1. Operando o AWS Config — custos, permissões, investigação de mudanças, boas práticas e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.1. AWS CloudWatch/0 AWS CloudWatch (Tópicos )|AWS CloudWatch]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.2. AWS CloudTrail/0 AWS CloudTrail (Tópicos )|AWS CloudTrail]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.1. Amazon S3/0 Amazon S3 (Tópicos )|Amazon S3]]
