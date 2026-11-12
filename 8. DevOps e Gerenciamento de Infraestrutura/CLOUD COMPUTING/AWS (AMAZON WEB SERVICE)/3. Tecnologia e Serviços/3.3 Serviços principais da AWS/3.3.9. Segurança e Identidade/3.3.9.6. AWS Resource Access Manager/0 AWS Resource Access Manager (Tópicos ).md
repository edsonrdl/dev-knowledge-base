# 📚 Guia de Estudos: AWS Resource Access Manager (RAM)
#tag #aws #cloud #multiconta #ram #organizations #vpcsharing #governanca

> [!info] Visão Geral
> O AWS Resource Access Manager (RAM) compartilha recursos AWS de forma segura entre contas, OUs e a organização inteira, sem duplicá-los nem usar peering: subnets de VPC (VPC sharing), Transit Gateway, regras do Route 53 Resolver, políticas do Network Firewall, pools do License Manager, Glue, Capacity Reservations e outros. O serviço é gratuito; o dono mantém o recurso e os consumidores o usam conforme permissões gerenciadas. Este guia cobre fundamentos, resource shares e permissões, recursos compartilháveis e cenários, arquitetura multi-conta, segurança e governança (SCPs, bloqueio de compartilhamento externo) e operação.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Compartilhamento de recursos**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.6. AWS Resource Access Manager/1. Fundamentos/1.1 Visão geral/1.1.1. Compartilhamento de recursos/1.1.1.1. O que é AWS Resource Access Manager — compartilhamento de recursos entre contas sem duplicação, resource shares, dono e consumidor, Organizations e quando usar RAM em vez de peering ou cópia|1.1.1.1. O que é AWS Resource Access Manager — compartilhamento de recursos entre contas sem duplicação, resource shares, dono e consumidor, Organizations e quando usar RAM em vez de peering ou cópia]]

---

## 2 Domínio: Resource shares e permissões

### 2.1 Shares, principais e permissões gerenciadas
- **2.1.1. Modelo de compartilhamento**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.6. AWS Resource Access Manager/2. Resource shares e permissões/2.1 Shares, principais e permissões gerenciadas/2.1.1. Modelo de compartilhamento/2.1.1.1. Resource shares no RAM — recursos, principais, permissões gerenciadas, versões, convites, compartilhamento fora da organização e ciclo de vida do share|2.1.1.1. Resource shares no RAM — recursos, principais, permissões gerenciadas, versões, convites, compartilhamento fora da organização e ciclo de vida do share]]

---

## 3 Domínio: Recursos compartilháveis e cenários

### 3.1 Subnets, TGW, regras de DNS e outros
- **3.1.1. Cenários multi-conta**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.6. AWS Resource Access Manager/3. Recursos compartilháveis e cenários/3.1 Subnets, TGW, regras de DNS e outros/3.1.1. Cenários multi-conta/3.1.1.1. Recursos compartilháveis e cenários no RAM — subnets de VPC, Transit Gateway, regras do Route 53 Resolver, Network Firewall, License Manager, Glue, Aurora, Capacity Reservations e limites|3.1.1.1. Recursos compartilháveis e cenários no RAM — subnets de VPC, Transit Gateway, regras do Route 53 Resolver, Network Firewall, License Manager, Glue, Aurora, Capacity Reservations e limites]]

---

## 4 Domínio: Organizations e arquitetura

### 4.1 Compartilhamento organizacional e padrões
- **4.1.1. Landing zone e multi-conta**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.6. AWS Resource Access Manager/4. Organizations e arquitetura/4.1 Compartilhamento organizacional e padrões/4.1.1. Landing zone e multi-conta/4.1.1.1. Arquitetura multi-conta com RAM — landing zone, conta de rede compartilhada, VPC sharing, DNS centralizado, inspeção, AZ IDs, custos e responsabilidades|4.1.1.1. Arquitetura multi-conta com RAM — landing zone, conta de rede compartilhada, VPC sharing, DNS centralizado, inspeção, AZ IDs, custos e responsabilidades]]

---

## 5 Domínio: Segurança e governança

### 5.1 IAM, SCP e controle de compartilhamento
- **5.1.1. Controle e auditoria**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.6. AWS Resource Access Manager/5. Segurança e governança/5.1 IAM, SCP e controle de compartilhamento/5.1.1. Controle e auditoria/5.1.1.1. Segurança do RAM — controle de quem compartilha, SCPs e condition keys, bloqueio de compartilhamento externo, permissões mínimas, auditoria e governança|5.1.1.1. Segurança do RAM — controle de quem compartilha, SCPs e condition keys, bloqueio de compartilhamento externo, permissões mínimas, auditoria e governança]]

---

## 6 Domínio: Operação e troubleshooting

### 6.1 Monitoramento, quotas e erros
- **6.1.1. Observabilidade e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.6. AWS Resource Access Manager/6. Operação e troubleshooting/6.1 Monitoramento, quotas e erros/6.1.1. Observabilidade e troubleshooting/6.1.1.1. Operação do RAM — estados de share e recurso, monitoramento com CloudTrail e EventBridge, quotas, erros comuns, troubleshooting e checklist de produção|6.1.1.1. Operação do RAM — estados de share e recurso, monitoramento com CloudTrail e EventBridge, quotas, erros comuns, troubleshooting e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.1. Amazon VPC/0 Amazon VPC (Tópicos )|Amazon VPC]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.5. Gerenciamento e Governança/3.3.5.7. AWS Control Tower/0 AWS Control Tower (Tópicos )|AWS Control Tower]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.3. AWS Network Firewall/0 AWS Network Firewall (Tópicos )|AWS Network Firewall]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.4. AWS Firewall Manager/0 AWS Firewall Manager (Tópicos )|AWS Firewall Manager]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.5. AWS Directory Service/0 AWS Directory Service (Tópicos )|AWS Directory Service]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.5. Amazon Route 53/0 Amazon Route 53 (Tópicos )|Amazon Route 53]]
