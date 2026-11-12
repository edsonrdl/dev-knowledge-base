# 📚 Guia de Estudos: AWS Transfer Family
#tag #aws #cloud #transferencia #sftp #ftps #as2 #b2b #s3

> [!info] Visão Geral
> O AWS Transfer Family oferece endpoints gerenciados de SFTP, FTPS, FTP e AS2 que gravam e leem diretamente no Amazon S3 ou no Amazon EFS, sem servidores para administrar, com multi-AZ, autenticação flexível (chaves SSH, Active Directory, Lambda/API Gateway), workflows pós-upload e conectores de envio. Este guia cobre fundamentos, servidores e endpoints, usuários e autenticação, armazenamento e automação (workflows, eventos, conectores, AS2), segurança e operação (métricas, custos, runbooks).

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Transferência de arquivos gerenciada**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.6. AWS Transfer Family/1. Fundamentos/1.1 Visão geral/1.1.1. Transferência de arquivos gerenciada/1.1.1.1. O que é AWS Transfer Family — SFTP, FTPS, FTP e AS2 gerenciados para S3 e EFS, componentes, casos de uso e quando usar em vez de DataSync, Storage Gateway e servidores próprios|1.1.1.1. O que é AWS Transfer Family — SFTP, FTPS, FTP e AS2 gerenciados para S3 e EFS, componentes, casos de uso e quando usar em vez de DataSync, Storage Gateway e servidores próprios]]

---

## 2 Domínio: Servidores e protocolos

### 2.1 SFTP, FTPS, FTP, AS2 e endpoints
- **2.1.1. Tipos de servidor e rede**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.6. AWS Transfer Family/2. Servidores e protocolos/2.1 SFTP, FTPS, FTP, AS2 e endpoints/2.1.1. Tipos de servidor e rede/2.1.1.1. Servidores do Transfer Family — protocolos, tipos de endpoint (público, VPC e internet-facing), IPs fixos, domínios customizados, security policies, portas e alta disponibilidade|2.1.1.1. Servidores do Transfer Family — protocolos, tipos de endpoint (público, VPC e internet-facing), IPs fixos, domínios customizados, security policies, portas e alta disponibilidade]]

---

## 3 Domínio: Usuários e autenticação

### 3.1 Service managed, Directory Service e identidade customizada
- **3.1.1. Identidade e mapeamento**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.6. AWS Transfer Family/3. Usuários e autenticação/3.1 Service managed, Directory Service e identidade customizada/3.1.1. Identidade e mapeamento/3.1.1.1. Usuários e autenticação no Transfer Family — service managed com chaves SSH, Directory Service, identidade customizada com Lambda e API Gateway, roles, diretórios lógicos e session policies|3.1.1.1. Usuários e autenticação no Transfer Family — service managed com chaves SSH, Directory Service, identidade customizada com Lambda e API Gateway, roles, diretórios lógicos e session policies]]

---

## 4 Domínio: Armazenamento e automação

### 4.1 S3, EFS, workflows e conectores
- **4.1.1. Integração e processamento**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.6. AWS Transfer Family/4. Armazenamento e automação/4.1 S3, EFS, workflows e conectores/4.1.1. Integração e processamento/4.1.1.1. Armazenamento, workflows e conectores no Transfer Family — S3 e EFS, workflows gerenciados, eventos, SFTP connectors, AS2 e automação de recebimento e envio de arquivos|4.1.1.1. Armazenamento, workflows e conectores no Transfer Family — S3 e EFS, workflows gerenciados, eventos, SFTP connectors, AS2 e automação de recebimento e envio de arquivos]]

---

## 5 Domínio: Segurança e governança

### 5.1 IAM, criptografia e logs
- **5.1.1. Controle e conformidade**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.6. AWS Transfer Family/5. Segurança e governança/5.1 IAM, criptografia e logs/5.1.1. Controle e conformidade/5.1.1.1. Segurança do Transfer Family — IAM por usuário, criptografia, chaves de host, security policies, rede, logs estruturados, auditoria e conformidade|5.1.1.1. Segurança do Transfer Family — IAM por usuário, criptografia, chaves de host, security policies, rede, logs estruturados, auditoria e conformidade]]

---

## 6 Domínio: Operação e custos

### 6.1 Monitoramento, quotas e troubleshooting
- **6.1.1. Observabilidade e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.6. AWS Transfer Family/6. Operação e custos/6.1 Monitoramento, quotas e troubleshooting/6.1.1. Observabilidade e troubleshooting/6.1.1.1. Operação do Transfer Family — métricas, logs, quotas, custos por protocolo e por GB, troubleshooting e checklist de produção|6.1.1.1. Operação do Transfer Family — métricas, logs, quotas, custos por protocolo e por GB, troubleshooting e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.8. Migração e Transferência/3.3.8.3. AWS DataSync/0 AWS DataSync (Tópicos )|AWS DataSync]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.1. Amazon S3/0 Amazon S3 (Tópicos )|Amazon S3]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.3. Amazon EFS/0 Amazon EFS (Tópicos )|Amazon EFS]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.4. AWS Storage Gateway/0 AWS Storage Gateway (Tópicos )|AWS Storage Gateway]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.5. AWS Directory Service/0 AWS Directory Service (Tópicos )|AWS Directory Service]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.3. Amazon EventBridge/0 Amazon EventBridge (Tópicos )|Amazon EventBridge]]
