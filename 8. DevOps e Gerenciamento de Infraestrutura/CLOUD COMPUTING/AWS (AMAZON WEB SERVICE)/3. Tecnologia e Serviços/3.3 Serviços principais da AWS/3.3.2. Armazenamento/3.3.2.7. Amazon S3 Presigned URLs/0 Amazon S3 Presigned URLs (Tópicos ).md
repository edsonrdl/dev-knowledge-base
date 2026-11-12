# 📚 Guia de Estudos: Amazon S3 Presigned URLs
#tag #aws #cloud #s3 #presigned #sigv4 #upload #download #cors #seguranca

> [!info] Visão Geral
> Uma presigned URL é um link temporário, assinado com SigV4 na query string, que permite a quem o possui executar uma operação específica (GET, PUT, POST, multipart) em um objeto do S3 sem credenciais AWS, com as permissões de quem assinou. Este guia cobre fundamentos e alternativas (CloudFront, Cognito, proxy), geração e uso (SDKs, CLI, presigned POST, multipart, checksums), validade por tipo de credencial e cenários (upload/download direto, CORS), arquiteturas com eventos e validação, segurança (URL portadora, bucket policy, KMS, revogação, auditoria) e troubleshooting.

---

## 1 Domínio: Fundamentos

### 1.1 Visão geral
- **1.1.1. Acesso temporário a objetos**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.7. Amazon S3 Presigned URLs/1. Fundamentos/1.1 Visão geral/1.1.1. Acesso temporário a objetos/1.1.1.1. O que são presigned URLs do Amazon S3 — acesso temporário a objetos sem credenciais, SigV4 na query string, GET e PUT, casos de uso e quando usar em vez de CloudFront signed URLs, Cognito e proxy|1.1.1.1. O que são presigned URLs do Amazon S3 — acesso temporário a objetos sem credenciais, SigV4 na query string, GET e PUT, casos de uso e quando usar em vez de CloudFront signed URLs, Cognito e proxy]]

---

## 2 Domínio: Geração e uso

### 2.1 SDKs, CLI, PUT, POST e multipart
- **2.1.1. Criação e consumo**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.7. Amazon S3 Presigned URLs/2. Geração e uso/2.1 SDKs, CLI, PUT, POST e multipart/2.1.1. Criação e consumo/2.1.1.1. Gerando e usando presigned URLs — SDKs e CLI, GET, PUT, presigned POST com policy, multipart, parâmetros assinados, content-type, checksums e exemplos|2.1.1.1. Gerando e usando presigned URLs — SDKs e CLI, GET, PUT, presigned POST com policy, multipart, parâmetros assinados, content-type, checksums e exemplos]]

---

## 3 Domínio: Validade e cenários

### 3.1 Expiração, credenciais e padrões de aplicação
- **3.1.1. Upload e download diretos**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.7. Amazon S3 Presigned URLs/3. Validade e cenários/3.1 Expiração, credenciais e padrões de aplicação/3.1.1. Upload e download diretos/3.1.1.1. Validade e cenários de presigned URLs — expiração por tipo de credencial, roles e sessões, upload direto do navegador, downloads, CORS e padrões de aplicação|3.1.1.1. Validade e cenários de presigned URLs — expiração por tipo de credencial, roles e sessões, upload direto do navegador, downloads, CORS e padrões de aplicação]]

---

## 4 Domínio: Arquitetura e integração

### 4.1 Eventos, validação, CloudFront e rede
- **4.1.1. Fluxos completos**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.7. Amazon S3 Presigned URLs/4. Arquitetura e integração/4.1 Eventos, validação, CloudFront e rede/4.1.1. Fluxos completos/4.1.1.1. Arquiteturas com presigned URLs — eventos S3, validação e antivírus, CloudFront, VPC endpoints, Transfer Acceleration, reconciliação, limites e custos|4.1.1.1. Arquiteturas com presigned URLs — eventos S3, validação e antivírus, CloudFront, VPC endpoints, Transfer Acceleration, reconciliação, limites e custos]]

---

## 5 Domínio: Segurança e governança

### 5.1 Permissões, condições e auditoria
- **5.1.1. Controle e conformidade**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.7. Amazon S3 Presigned URLs/5. Segurança e governança/5.1 Permissões, condições e auditoria/5.1.1. Controle e conformidade/5.1.1.1. Segurança de presigned URLs — URL como portador, privilégio mínimo do assinante, bucket policy e condições, KMS, revogação, CloudTrail e conformidade|5.1.1.1. Segurança de presigned URLs — URL como portador, privilégio mínimo do assinante, bucket policy e condições, KMS, revogação, CloudTrail e conformidade]]

---

## 6 Domínio: Operação e troubleshooting

### 6.1 Erros, CORS e diagnóstico
- **6.1.1. Observabilidade e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.7. Amazon S3 Presigned URLs/6. Operação e troubleshooting/6.1 Erros, CORS e diagnóstico/6.1.1. Observabilidade e troubleshooting/6.1.1.1. Troubleshooting de presigned URLs — SignatureDoesNotMatch, AccessDenied, Request has expired, ExpiredToken, CORS, redirects 307, KMS, diagnóstico passo a passo e checklist|6.1.1.1. Troubleshooting de presigned URLs — SignatureDoesNotMatch, AccessDenied, Request has expired, ExpiredToken, CORS, redirects 307, KMS, diagnóstico passo a passo e checklist]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.1. Amazon S3/0 Amazon S3 (Tópicos )|Amazon S3]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.10. Ferramentas de Desenvolvedor/3.3.10.5. AWS SDKs, CLI e SigV4/0 AWS SDKs, CLI e SigV4 (Tópicos )|AWS SDKs, CLI e SigV4]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.9. Segurança e Identidade/3.3.9.1. Amazon Cognito/0 Amazon Cognito (Tópicos )|Amazon Cognito]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.7. Integração de Aplicações/3.3.7.5. Amazon API Gateway/0 Amazon API Gateway (Tópicos )|Amazon API Gateway]]
