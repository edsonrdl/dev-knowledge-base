# 📚 Guia de Estudos: AWS CloudFormation
#tag #aws #cloud #iac #cloudformation #infraestrutura-como-codigo

> [!info] Visão Geral
> O AWS CloudFormation é o serviço de infraestrutura como código da AWS: você descreve recursos em templates YAML/JSON e o serviço cria, atualiza e remove tudo como uma unidade chamada stack. Este guia cobre os fundamentos (template, stack, ciclo de vida, comparação com Terraform e CDK), a anatomia do template (parâmetros, condições, funções intrínsecas), as mudanças seguras (change sets, rollback, drift), a escala (nested stacks, StackSets, modules, macros), a qualidade e entrega (cfn-lint, Guard, Hooks, CDK, SAM, pipelines) e a operação (IAM, limites, custos, troubleshooting).

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Infraestrutura como código e stacks**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.5. AWS CloudFormation/1. Fundamentos/1.1 Visão geral/1.1.1. Infraestrutura como código e stacks/1.1.1.1. O que é AWS CloudFormation — infraestrutura como código, templates, stacks, ciclo de vida e comparação com Terraform, CDK e console|1.1.1.1. O que é AWS CloudFormation — infraestrutura como código, templates, stacks, ciclo de vida e comparação com Terraform, CDK e console]]

---

## 2 Domínio: Templates

### 2.1 Anatomia do template
- **2.1.1. Seções, funções intrínsecas e referências**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.5. AWS CloudFormation/2. Templates/2.1 Anatomia do template/2.1.1. Seções, funções intrínsecas e referências/2.1.1.1. Anatomia de um template — Parameters, Mappings, Conditions, Resources, Outputs, funções intrínsecas, pseudo parameters e referências dinâmicas|2.1.1.1. Anatomia de um template — Parameters, Mappings, Conditions, Resources, Outputs, funções intrínsecas, pseudo parameters e referências dinâmicas]]

---

## 3 Domínio: Mudanças e estado

### 3.1 Atualizações seguras
- **3.1.1. Change sets, rollback, drift e proteção**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.5. AWS CloudFormation/3. Mudanças e estado/3.1 Atualizações seguras/3.1.1. Change sets, rollback, drift e proteção/3.1.1.1. Mudanças seguras no CloudFormation — change sets, rollback, drift detection, stack policy, termination protection, import e retain|3.1.1.1. Mudanças seguras no CloudFormation — change sets, rollback, drift detection, stack policy, termination protection, import e retain]]

---

## 4 Domínio: Escala e reutilização

### 4.1 Nested stacks, StackSets e extensões
- **4.1.1. Modularização e multi-conta**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.5. AWS CloudFormation/4. Escala e reutilização/4.1 Nested stacks, StackSets e extensões/4.1.1. Modularização e multi-conta/4.1.1.1. CloudFormation em escala — nested stacks, cross-stack references, StackSets, modules, macros e custom resources|4.1.1.1. CloudFormation em escala — nested stacks, cross-stack references, StackSets, modules, macros e custom resources]]

---

## 5 Domínio: Qualidade e entrega

### 5.1 Validação e pipelines
- **5.1.1. Lint, Guard, Hooks, CI/CD, CDK e SAM**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.5. AWS CloudFormation/5. Qualidade e entrega/5.1 Validação e pipelines/5.1.1. Lint, Guard, Hooks, CI-CD, CDK e SAM/5.1.1.1. Qualidade e entrega contínua — cfn-lint, cfn-guard, Hooks, pipelines, TaskCat, AWS CDK, AWS SAM e ferramentas de apoio|5.1.1.1. Qualidade e entrega contínua — cfn-lint, cfn-guard, Hooks, pipelines, TaskCat, AWS CDK, AWS SAM e ferramentas de apoio]]

---

## 6 Domínio: Operação

### 6.1 Segurança, custos e diagnóstico
- **6.1.1. IAM, limites e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.5. AWS CloudFormation/6. Operação/6.1 Segurança, custos e diagnóstico/6.1.1. IAM, limites e troubleshooting/6.1.1.1. Operando o CloudFormation — IAM e service roles, limites, custos, troubleshooting de falhas de stack e checklist de produção|6.1.1.1. Operando o CloudFormation — IAM e service roles, limites, custos, troubleshooting de falhas de stack e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.3. AWS Config/0 AWS Config (Tópicos )|AWS Config]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.2. AWS CloudTrail/0 AWS CloudTrail (Tópicos )|AWS CloudTrail]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.4. AWS Systems Manager/0 AWS Systems Manager (Tópicos )|AWS Systems Manager]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.1. Amazon S3/0 Amazon S3 (Tópicos )|Amazon S3]]
