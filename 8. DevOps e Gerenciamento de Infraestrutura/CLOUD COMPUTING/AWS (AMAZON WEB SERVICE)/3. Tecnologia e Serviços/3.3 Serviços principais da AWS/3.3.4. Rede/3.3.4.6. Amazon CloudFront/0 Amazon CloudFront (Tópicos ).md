# 📚 Guia de Estudos: Amazon CloudFront
#tag #aws #cloud #rede #cdn #cloudfront

> [!info] Visão Geral
> O Amazon CloudFront é a CDN da AWS: uma rede global de pontos de presença que serve conteúdo estático e dinâmico perto do usuário, reduz a carga da origem e adiciona segurança na borda (TLS, WAF, Shield, acesso privado). Este guia cobre arquitetura (edge, regional cache, origens), políticas de cache e invalidação, segurança (OAC, URLs assinadas, WAF), computação na borda (Functions e Lambda@Edge) e custo/operação.

---

## 1 Domínio: Fundamentos e Arquitetura

### 1.1 O que é CloudFront
- **1.1.1. CDN e fluxo de requisição**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.6. Amazon CloudFront/1. Fundamentos e Arquitetura/1.1 O que é CloudFront/1.1.1. CDN e fluxo de requisição/1.1.1.1. O que é CloudFront — CDN, edge locations, Regional Edge Caches e fluxo de uma requisição|1.1.1.1. O que é CloudFront — CDN, edge locations, Regional Edge Caches e fluxo de uma requisição]]

### 1.2 Origens e Comportamentos
- **1.2.1. Origens, behaviors e origin groups**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.6. Amazon CloudFront/1. Fundamentos e Arquitetura/1.2 Origens e Comportamentos/1.2.1. Origens, behaviors e origin groups/1.2.1.1. Origens e cache behaviors — S3, ALB, API Gateway, custom origins, path patterns e origin groups|1.2.1.1. Origens e cache behaviors — S3, ALB, API Gateway, custom origins, path patterns e origin groups]]

---

## 2 Domínio: Cache e Performance

### 2.1 Política de Cache
- **2.1.1. TTL, cache keys e invalidação**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.6. Amazon CloudFront/2. Cache e Performance/2.1 Política de Cache/2.1.1. TTL, cache keys e invalidação/2.1.1.1. Cache policies, TTL, cache keys e invalidação — como aumentar o cache hit ratio|2.1.1.1. Cache policies, TTL, cache keys e invalidação — como aumentar o cache hit ratio]]

---

## 3 Domínio: Segurança

### 3.1 Acesso Privado
- **3.1.1. OAC, signed URLs e HTTPS**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.6. Amazon CloudFront/3. Segurança/3.1 Acesso Privado/3.1.1. OAC, signed URLs e HTTPS/3.1.1.1. Acesso privado à origem e ao conteúdo — OAC, signed URLs, signed cookies e HTTPS|3.1.1.1. Acesso privado à origem e ao conteúdo — OAC, signed URLs, signed cookies e HTTPS]]

### 3.2 Proteção de Borda
- **3.2.1. WAF, Shield e restrição geográfica**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.6. Amazon CloudFront/3. Segurança/3.2 Proteção de Borda/3.2.1. WAF, Shield e restrição geográfica/3.2.1.1. Proteção de borda — AWS WAF, Shield, geo restriction e field-level encryption|3.2.1.1. Proteção de borda — AWS WAF, Shield, geo restriction e field-level encryption]]

---

## 4 Domínio: Edge Compute e Operação

### 4.1 Edge Compute
- **4.1.1. CloudFront Functions e Lambda@Edge**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.6. Amazon CloudFront/4. Edge Compute e Operação/4.1 Edge Compute/4.1.1. CloudFront Functions e Lambda@Edge/4.1.1.1. CloudFront Functions e Lambda@Edge — customização na borda e quando usar cada uma|4.1.1.1. CloudFront Functions e Lambda@Edge — customização na borda e quando usar cada uma]]

### 4.2 Custo e Monitoramento
- **4.2.1. Price classes, logs e métricas**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.6. Amazon CloudFront/4. Edge Compute e Operação/4.2 Custo e Monitoramento/4.2.1. Price classes, logs e métricas/4.2.1.1. Custo e operação — price classes, logs, métricas, Origin Shield e modelo de cobrança|4.2.1.1. Custo e operação — price classes, logs, métricas, Origin Shield e modelo de cobrança]]

---

## 5 Domínio: Recursos Avançados

### 5.1 Streaming, Erros e Logs
- **5.1.1. Mídia, error pages, deploy contínuo e troubleshooting**
  - [x] [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.6. Amazon CloudFront/5. Recursos Avançados/5.1 Streaming, Erros e Logs/5.1.1. Mídia, error pages, deploy contínuo e troubleshooting/5.1.1.1. CloudFront avançado — streaming de vídeo, páginas de erro personalizadas, continuous deployment, logs em tempo real, compressão e troubleshooting|5.1.1.1. CloudFront avançado — streaming de vídeo, páginas de erro personalizadas, continuous deployment, logs em tempo real, compressão e troubleshooting]]

---

> **Links Relacionados:**
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.4. Rede/3.3.4.5. Amazon Route 53/0 Amazon Route 53 (Tópicos )|Amazon Route 53]]
> [[8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/3. Tecnologia e Serviços/3.3 Serviços principais da AWS/3.3.2. Armazenamento/3.3.2.1. Amazon S3/0 Amazon S3 (Tópicos )|Amazon S3]]
