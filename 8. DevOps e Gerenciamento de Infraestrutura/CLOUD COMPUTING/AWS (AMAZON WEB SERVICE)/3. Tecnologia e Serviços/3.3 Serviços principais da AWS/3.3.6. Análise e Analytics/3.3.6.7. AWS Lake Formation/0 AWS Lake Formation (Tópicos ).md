# 📚 Guia de Estudos: AWS Lake Formation
#tag #aws #cloud #analytics #lakeformation #datalake #governanca #lftags #seguranca

> [!info] Visão Geral
> O AWS Lake Formation é a camada central de governança de data lakes sobre o Amazon S3 e o Glue Data Catalog: permissões estilo banco de dados (GRANT/REVOKE) em bancos, tabelas, colunas, linhas e células, LF-Tags (controle por atributos), credential vending para serviços integrados (Athena, EMR, Glue, Redshift Spectrum, QuickSight), compartilhamento multi-conta sem cópia e auditoria no CloudTrail. Este guia cobre fundamentos, modelo de autorização, ingestão e integrações, compartilhamento multi-conta e data mesh, segurança e operação.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Data lake governado**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.7. AWS Lake Formation/1. Fundamentos/1.1 Visão geral/1.1.1. Data lake governado/1.1.1.1. O que é AWS Lake Formation — data lake governado sobre S3 e Glue Data Catalog, permissões centralizadas, credential vending, serviços integrados e quando usar em vez de IAM e políticas de bucket|1.1.1.1. O que é AWS Lake Formation — data lake governado sobre S3 e Glue Data Catalog, permissões centralizadas, credential vending, serviços integrados e quando usar em vez de IAM e políticas de bucket]]

---

## 2 Domínio: Catálogo e permissões

### 2.1 Databases, tabelas, grants e LF-Tags
- **2.1.1. Modelo de autorização**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.7. AWS Lake Formation/2. Catálogo e permissões/2.1 Databases, tabelas, grants e LF-Tags/2.1.1. Modelo de autorização/2.1.1.1. Modelo de autorização do Lake Formation — grants em bancos, tabelas e colunas, filtros de linha e célula, LF-Tags, administradores, modos de acesso e permissões híbridas|2.1.1.1. Modelo de autorização do Lake Formation — grants em bancos, tabelas e colunas, filtros de linha e célula, LF-Tags, administradores, modos de acesso e permissões híbridas]]

---

## 3 Domínio: Ingestão e integrações

### 3.1 Blueprints, Glue, Athena, EMR e Redshift
- **3.1.1. Fontes e consumo**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.7. AWS Lake Formation/3. Ingestão e integrações/3.1 Blueprints, Glue, Athena, EMR e Redshift/3.1.1. Fontes e consumo/3.1.1.1. Ingestão e integrações do Lake Formation — registro de locais no S3, blueprints, Glue, Athena, EMR, Redshift Spectrum, QuickSight e fluxo de credenciais|3.1.1.1. Ingestão e integrações do Lake Formation — registro de locais no S3, blueprints, Glue, Athena, EMR, Redshift Spectrum, QuickSight e fluxo de credenciais]]

---

## 4 Domínio: Compartilhamento multi-conta

### 4.1 Cross-account, RAM e Organizations
- **4.1.1. Compartilhamento e data mesh**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.7. AWS Lake Formation/4. Compartilhamento multi-conta/4.1 Cross-account, RAM e Organizations/4.1.1. Compartilhamento e data mesh/4.1.1.1. Compartilhamento multi-conta no Lake Formation — grants cross-account, RAM, LF-Tags, resource links, Organizations e data mesh|4.1.1.1. Compartilhamento multi-conta no Lake Formation — grants cross-account, RAM, LF-Tags, resource links, Organizations e data mesh]]

---

## 5 Domínio: Segurança e governança

### 5.1 Acesso fino, auditoria e criptografia
- **5.1.1. Controle e conformidade**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.7. AWS Lake Formation/5. Segurança e governança/5.1 Acesso fino, auditoria e criptografia/5.1.1. Controle e conformidade/5.1.1.1. Segurança do Lake Formation — administração, criptografia, auditoria no CloudTrail, privilégio mínimo, migração de IAM para LF e conformidade|5.1.1.1. Segurança do Lake Formation — administração, criptografia, auditoria no CloudTrail, privilégio mínimo, migração de IAM para LF e conformidade]]

---

## 6 Domínio: Operação e troubleshooting

### 6.1 Monitoramento, quotas e erros
- **6.1.1. Observabilidade e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.7. AWS Lake Formation/6. Operação e troubleshooting/6.1 Monitoramento, quotas e erros/6.1.1. Observabilidade e troubleshooting/6.1.1.1. Operação do Lake Formation — monitoramento, erros comuns de permissão, quotas, custos, troubleshooting e checklist de produção|6.1.1.1. Operação do Lake Formation — monitoramento, erros comuns de permissão, quotas, custos, troubleshooting e checklist de produção]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.4. AWS Glue/0 AWS Glue (Tópicos )|AWS Glue]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.1. Amazon Athena/0 Amazon Athena (Tópicos )|Amazon Athena]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.6. Análise e Analytics/3.3.6.5. Amazon EMR/0 Amazon EMR (Tópicos )|Amazon EMR]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.1. Amazon S3/0 Amazon S3 (Tópicos )|Amazon S3]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.6. AWS Resource Access Manager/0 AWS Resource Access Manager (Tópicos )|AWS Resource Access Manager]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.2. Amazon Macie/0 Amazon Macie (Tópicos )|Amazon Macie]]
