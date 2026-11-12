# 📚 Guia de Estudos: AWS Directory Service
#tag #aws #cloud #seguranca #identidade #directoryservice #activedirectory #ldap #kerberos

> [!info] Visão Geral
> O AWS Directory Service oferece diretórios gerenciados (Active Directory ou compatíveis) na AWS: AWS Managed Microsoft AD, AD Connector (proxy para o AD on-premises) e Simple AD. Permite usar identidade corporativa com EC2, RDS, FSx for Windows, WorkSpaces e IAM Identity Center sem operar controladores de domínio. Este guia cobre fundamentos, os tipos de diretório e como escolher, integrações e trusts, implantação (VPC, DNS, multi-região, backup), segurança do diretório e operação (quotas, custos, runbooks).

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Diretórios gerenciados na AWS**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.5. AWS Directory Service/1. Fundamentos/1.1 Visão geral/1.1.1. Diretórios gerenciados na AWS/1.1.1.1. O que é AWS Directory Service — diretórios gerenciados na AWS, Active Directory, LDAP e Kerberos, os três tipos de diretório e quando usar cada um|1.1.1.1. O que é AWS Directory Service — diretórios gerenciados na AWS, Active Directory, LDAP e Kerberos, os três tipos de diretório e quando usar cada um]]

---

## 2 Domínio: Tipos de diretório

### 2.1 Managed Microsoft AD, AD Connector e Simple AD
- **2.1.1. Escolha e arquitetura**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.5. AWS Directory Service/2. Tipos de diretório/2.1 Managed Microsoft AD, AD Connector e Simple AD/2.1.1. Escolha e arquitetura/2.1.1.1. Tipos de diretório em profundidade — Managed Microsoft AD, AD Connector e Simple AD, edições, administração delegada, tamanhos, limites e como escolher|2.1.1.1. Tipos de diretório em profundidade — Managed Microsoft AD, AD Connector e Simple AD, edições, administração delegada, tamanhos, limites e como escolher]]

---

## 3 Domínio: Integrações e federação

### 3.1 Trusts, EC2, RDS, WorkSpaces e SSO
- **3.1.1. Integração com serviços e on-premises**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.5. AWS Directory Service/3. Integrações e federação/3.1 Trusts, EC2, RDS, WorkSpaces e SSO/3.1.1. Integração com serviços e on-premises/3.1.1.1. Integrações do Directory Service — trusts com AD on-premises, domain join de EC2, RDS, FSx, WorkSpaces, IAM Identity Center e federação com o console AWS|3.1.1.1. Integrações do Directory Service — trusts com AD on-premises, domain join de EC2, RDS, FSx, WorkSpaces, IAM Identity Center e federação com o console AWS]]

---

## 4 Domínio: Implantação e rede

### 4.1 VPC, DNS, multi-região e alta disponibilidade
- **4.1.1. Arquitetura e conectividade**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.5. AWS Directory Service/4. Implantação e rede/4.1 VPC, DNS, multi-região e alta disponibilidade/4.1.1. Arquitetura e conectividade/4.1.1.1. Implantação do Directory Service — VPC, subnets e AZs, DNS e DHCP options, security groups e portas, multi-região, compartilhamento, backup e recuperação|4.1.1.1. Implantação do Directory Service — VPC, subnets e AZs, DNS e DHCP options, security groups e portas, multi-região, compartilhamento, backup e recuperação]]

---

## 5 Domínio: Segurança e governança

### 5.1 Políticas, MFA, auditoria e proteção
- **5.1.1. Controle de acesso e logs**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.5. AWS Directory Service/5. Segurança e governança/5.1 Políticas, MFA, auditoria e proteção/5.1.1. Controle de acesso e logs/5.1.1.1. Segurança do Directory Service — administração delegada, políticas de senha, LDAPS, MFA com RADIUS, logs de segurança, IAM e endurecimento do diretório|5.1.1.1. Segurança do Directory Service — administração delegada, políticas de senha, LDAPS, MFA com RADIUS, logs de segurança, IAM e endurecimento do diretório]]

---

## 6 Domínio: Operação e custos

### 6.1 Quotas, custos e troubleshooting
- **6.1.1. Observabilidade e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.5. AWS Directory Service/6. Operação e custos/6.1 Quotas, custos e troubleshooting/6.1.1. Observabilidade e troubleshooting/6.1.1.1. Operação do Directory Service — quotas, custos por tipo e por DC, métricas e logs, troubleshooting, migração entre tipos e checklist de produção|6.1.1.1. Operação do Directory Service — quotas, custos por tipo e por DC, métricas e logs, troubleshooting, migração entre tipos e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.1. Amazon Cognito/0 Amazon Cognito (Tópicos )|Amazon Cognito]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.3. Banco de Dados/3.3.3.1. Amazon RDS/0 Amazon RDS (Tópicos )|Amazon RDS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.5. Amazon FSx/0 Amazon FSx (Tópicos )|Amazon FSx]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.1. Amazon VPC/0 Amazon VPC (Tópicos )|Amazon VPC]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.4. AWS Systems Manager/0 AWS Systems Manager (Tópicos )|AWS Systems Manager]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.5. Amazon Route 53/0 Amazon Route 53 (Tópicos )|Amazon Route 53]]
