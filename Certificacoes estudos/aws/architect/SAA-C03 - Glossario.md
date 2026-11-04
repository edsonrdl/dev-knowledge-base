---
tags: [aws, certificacao, solutions-architect-associate, saa-c03, glossario]
exame: SAA-C03
fonte-oficial: https://docs.aws.amazon.com/aws-certification/latest/solutions-architect-associate-03/solutions-architect-associate-03.html
verificado-em: 2026-11-04
status: completo-v1 (números conferidos nas docs oficiais em 2026-11-04)
---

# 📗 Glossário AWS Certified Solutions Architect – Associate (SAA-C03)

> Organizado pela hierarquia oficial (Domínio → Task Statement). Em cada item: conceito, números que caem, decisões "X vs Y" e **como a pergunta é feita**. Use com [[SAA-C03 - Prompts de Questoes]]. Fontes: [[Referencias e Fontes]]. Plano: [[00 - Plano de Estudos e Indice AWS Certificacoes]].
> Complementa a nota anterior [[Conteúdo de estudos Architect – Associate]].
> **Papel desta nota:** guia de referência do que cai e como cai. Não é a nota de conteúdo dos serviços (essas ficam nas camadas `8. DevOps.../AWS (AMAZON WEB SERVICE)/`) e não terá notas filhas.

## 0. Visão Geral

### 0.1 Fatos oficiais
- **SAA-C03** (guia v1.1): vigente; **nenhuma data de aposentadoria anunciada** nas fontes oficiais consultadas em 2026-11-04 (conferir a página da certificação antes de agendar).
- 65 questões (**50 pontuadas + 15 não pontuadas**), 130 min, nota **720/1000**, modelo compensatório, múltipla escolha e **múltipla resposta**, sem penalidade por chute.
- Valida: projetar soluções com base no **AWS Well-Architected Framework**, atendendo requisitos atuais e futuros; revisar soluções existentes e propor melhorias.

### 0.2 Pesos
| Domínio | Peso |
|---|---|
| 1. Design Secure Architectures | **30%** |
| 2. Design Resilient Architectures | **26%** |
| 3. Design High-Performing Architectures | **24%** |
| 4. Design Cost-Optimized Architectures | **20%** |

### 0.3 Como as perguntas são feitas
1. **Cenário de negócio** (empresa, carga de trabalho, requisito) → pede **a melhor arquitetura**.
2. Qualificadores: *MOST cost-effective*, *LEAST operational overhead*, *MOST secure*, *highly available*, *fault tolerant*, *without changing application code*, *near real time*, *minimum latency*, *meet RPO of X / RTO of Y*, *with minimal downtime*.
3. As opções costumam combinar 2–3 serviços; quase sempre há uma solução "funciona, mas é cara/manual/menos resiliente".
4. Domínio **decisório** (escolher entre serviços), muito menos "código" que o Developer.
5. Lógica-chave: identificar **o requisito que elimina opções** (ex.: "sem internet", "multi-região", "arquivo compartilhado Windows", "protocolo UDP").
6. Palavras-gatilho: [[SAA-C03 - Glossario#8. Tabela de Palavras-Gatilho]].

### 0.4 Os 6 pilares do Well-Architected (base de tudo)
Operational Excellence · Security · Reliability · Performance Efficiency · Cost Optimization · Sustainability.

---

## 1. DOMÍNIO 1 — Design Secure Architectures (30%)

### 1.1 Task 1.1 — Acesso seguro a recursos AWS

#### 1.1.1 Infraestrutura global e responsabilidade compartilhada
- **Região** (isolamento geográfico, residência de dados) → **AZs** (1+ data centers isolados, latência baixa entre si) → **Edge locations/PoPs** (CloudFront, Route 53, Global Accelerator). **Local Zones/Wavelength/Outposts** estendem para latência/local.
- **Responsabilidade compartilhada:** AWS = segurança **DA** nuvem (hardware, hypervisor, instalações); cliente = segurança **NA** nuvem (dados, IAM, SO convidado, firewall, criptografia). Em serviços gerenciados (RDS, Lambda) a AWS assume mais camadas (SO/patch); em EC2 o cliente corrige o SO.

#### 1.1.2 IAM — usuários root, MFA, usuários, grupos, roles, políticas
- **Root user:** uso mínimo, MFA obrigatória, sem access keys; criar admins nomeados. 
- **Usuários/grupos** (grupos não podem ser aninhados nem são principals); **roles** (credenciais temporárias, sem credencial fixa; para EC2/Lambda/ECS/cross-account/federação).
- **Políticas:** identity-based, resource-based, **permissions boundary**, **SCP**, session policy. **Deny explícito vence**. Elementos: `Effect`, `Action`, `Resource`, `Condition`, `Principal` (resource-based).
- **Menor privilégio**, **IAM Access Analyzer** (acesso externo e geração de política por atividade), **credential report**, rotação de chaves.
- **Como cai:** "Aplicação em EC2 precisa acessar S3" → **instance profile/role**, nunca access key.

#### 1.1.3 Estratégia multi-conta
- **AWS Organizations:** contas em OUs, faturamento consolidado, **SCPs** (limitam o máximo que contas podem fazer; **não concedem** permissão; não afetam a conta de gerenciamento).
- **Control Tower:** *landing zone* com guardrails (preventivos via SCP, detectivos via Config) e Account Factory.
- **IAM Identity Center (SSO):** acesso centralizado a múltiplas contas e apps SAML, com *permission sets*; integra AD/IdP externo.
- **AWS RAM:** compartilha recursos (subnets, Transit Gateway, License Manager) entre contas sem peering.
- **Cross-account:** role na conta destino (trust) + `sts:AssumeRole` na origem.
- **Como cai:** "Impedir que contas de desenvolvimento usem regiões fora da UE" → SCP com condição `aws:RequestedRegion`.

#### 1.1.4 Federação e serviços de diretório
- **SAML 2.0 / OIDC → IAM roles**, **Cognito** (usuários de apps), **IAM Identity Center** (força de trabalho).
- **AWS Directory Service:** **Managed Microsoft AD** (AD real gerenciado, relação de confiança com on-prem), **AD Connector** (proxy para AD on-prem, sem armazenar), **Simple AD** (básico compatível Samba).
- **Como cai:** "Usuários corporativos entram na console com credenciais do AD existente" → federação (SAML/Identity Center + AD).

#### 1.1.5 Resource policies
- S3 bucket policy, SQS/SNS policy, KMS key policy, Lambda policy, ECR, Secrets Manager, VPC endpoint policy. Uso típico: acesso cross-account, restringir por origem (`aws:SourceVpce`, `aws:SourceArn`), forçar TLS (`aws:SecureTransport`).

### 1.2 Task 1.2 — Cargas de trabalho e aplicações seguras

#### 1.2.1 VPC segura
- **Componentes:** CIDR (RFC 1918), subnets (por AZ), route tables, **Internet Gateway** (IPv4/IPv6), **NAT Gateway** (saída para internet de subnets privadas; zonal; HA = 1 por AZ), **Egress-only IGW** (IPv6 saída), **Elastic IP**.
- **Subnet pública** = rota `0.0.0.0/0` → IGW (+ IP público). **Privada** = sem rota direta ao IGW.
- **Security Group (SG):** nível de ENI/instância, **stateful**, apenas *allow*, pode referenciar outros SGs. **NACL:** nível de subnet, **stateless**, allow **e** deny, regras numeradas (menor número primeiro), precisa liberar portas efêmeras de retorno.
- **Bloquear um IP específico** → NACL (SG não nega). **Permitir só tráfego da camada web ao app** → SG referenciando SG.
- **VPC Endpoints:** **Gateway** (S3 e DynamoDB; sem custo; via route table) e **Interface/PrivateLink** (ENI com IP privado para demais serviços e serviços próprios/terceiros; cobra por hora/dado). Policy de endpoint.
- **Flow Logs:** tráfego IP aceito/rejeitado (VPC/subnet/ENI) → CloudWatch/S3. **Bastion/Session Manager** em vez de SSH aberto.
- **Como cai:** "EC2 em subnet privada precisa atualizar pacotes na internet" → NAT Gateway em subnet pública. "Acessar S3 sem passar pela internet e sem custo" → Gateway endpoint.

#### 1.2.2 Segmentação e camadas
- Padrão 3 camadas: web (pública/ALB) → app (privada) → dados (privada isolada). Múltiplas AZs. Dados nunca em subnet pública.

#### 1.2.3 Serviços de proteção de aplicações
| Serviço | Para quê |
|---|---|
| **AWS WAF** | Firewall L7 (SQL injection, XSS, rate-based, geo, IP sets); em CloudFront, ALB, API Gateway, AppSync, Cognito |
| **AWS Shield** | Standard (grátis, DDoS L3/L4); **Advanced** (resposta 24x7 DRT, proteção de custo, L7 com WAF) |
| **Network Firewall** | Firewall de rede gerenciado (inspeção stateful/IPS) na VPC |
| **Firewall Manager** | Política central de WAF/Shield/SG/Network Firewall em Organizations |
| **GuardDuty** | Detecção de ameaças (CloudTrail, VPC Flow Logs, DNS, S3, EKS, malware) |
| **Inspector** | Vulnerabilidades em EC2, ECR, Lambda |
| **Macie** | Descoberta de dados sensíveis (PII) em S3 |
| **Detective** | Investigação/causa raiz de achados |
| **Security Hub** | Painel central de achados e conformidade |
| **Config** | Histórico de configuração e regras de conformidade |
| **CloudTrail** | Auditoria de chamadas de API |
| **Secrets Manager** | Segredos com rotação |
| **Cognito** | Autenticação de usuários de apps |
- **DDoS** → CloudFront + Shield + WAF + Route 53; escalar horizontalmente. **SQL injection/XSS** → WAF.

#### 1.2.4 Conexões externas seguras
- **Site-to-Site VPN:** IPsec sobre internet, **2 túneis** por conexão (cada um em uma AZ; configurar os dois para redundância), rápido de subir, até **1,25 Gbps por túnel**; *Large Bandwidth Tunnel* até **5 Gbps** (só com Transit Gateway ou Cloud WAN); acima disso, **ECMP** com várias conexões. **Client VPN:** acesso remoto de usuários (OpenVPN).
- **Direct Connect:** link dedicado (1/10/100 Gbps), latência consistente, **não criptografa por padrão** (usar VPN sobre DX ou MACsec); demora semanas; **DX Gateway** para múltiplas VPCs/regiões; resiliência = 2 conexões em locais diferentes.
- **PrivateLink:** expor um serviço para outras VPCs/contas de forma privada, unidirecional, sem peering; **VPC Peering** (sem transitividade, CIDRs não sobrepostos) vs **Transit Gateway** (hub transitivo, escalável).
- **Como cai:** "Conectar 50 VPCs e on-prem de forma escalável" → Transit Gateway. "Expor SaaS a clientes sem expor a VPC inteira" → PrivateLink.

### 1.3 Task 1.3 — Controles de segurança de dados

#### 1.3.1 KMS e criptografia
- **KMS:** chaves AWS owned / AWS managed / **customer managed**; simétrica (AES-256) vs assimétrica; **envelope encryption** (limite de 4 KB para Encrypt direto); **key policy**; grants; rotação automática (anual) de CMK simétrica; **multi-region keys**; **CloudHSM** (HSM dedicado, FIPS 140-2 L3, você gerencia as chaves) vs KMS (gerenciado, HSMs compartilhados).
- **Em repouso:** S3 (SSE-S3 padrão, SSE-KMS, SSE-C, DSSE-KMS, client-side), **EBS** (KMS; snapshot de volume criptografado é criptografado), **RDS** (definida na criação; para criptografar um existente → snapshot, copiar criptografado, restaurar), DynamoDB, EFS, FSx, Redshift.
- **Em trânsito:** TLS; **ACM** (certificado público grátis, renovação automática, integra ELB/CloudFront/API Gateway; CloudFront exige us-east-1); forçar HTTPS no ALB/CloudFront; `aws:SecureTransport`.
- **Como cai:** "Cumprir norma que exige que a empresa controle o hardware das chaves" → CloudHSM. "Auditar uso de chaves" → KMS + CloudTrail.

#### 1.3.2 Dados: acesso, retenção, backups, recuperação
- **S3:** Block Public Access, ACLs desativadas, **versioning**, **MFA Delete**, **Object Lock** (WORM; governance vs compliance), **replicação** (CRR/SRR, exige versioning), Access Points, **S3 Glacier Vault Lock** (política imutável), Lifecycle.
- **AWS Backup:** política centralizada de backup (EBS, RDS, DynamoDB, EFS, FSx, EC2, S3...), cross-region/cross-account, **Backup Vault Lock**, relatórios de conformidade.
- **Snapshots:** EBS (incrementais, cópia entre regiões/contas), RDS (automáticos + manuais, PITR).
- **Classificação e governança:** Macie, tags, Config, Audit Manager, **AWS Artifact** (relatórios de conformidade e acordos), Lake Formation.
- **Como cai:** "Dados devem ser imutáveis por 7 anos (regulatório)" → S3 Object Lock modo **compliance** (ou Glacier Vault Lock).

---

## 2. DOMÍNIO 2 — Design Resilient Architectures (26%)

### 2.1 Task 2.1 — Arquiteturas escaláveis e fracamente acopladas

#### 2.1.1 Desacoplamento e mensageria
- **SQS** (fila; Standard vs FIFO; DLQ; long polling; visibility timeout; atrasa/absorve picos), **SNS** (pub/sub; fan-out SNS→SQS), **EventBridge** (barramento, regras, SaaS), **Kinesis** (streams ordenados), **Amazon MQ** (migração de ActiveMQ/RabbitMQ com protocolos padrão: JMS, AMQP, MQTT), **MSK** (Kafka gerenciado), **Step Functions** (orquestração), **AppFlow** (integração SaaS ↔ AWS).
- **Quando usar Amazon MQ:** migrar broker existente **sem reescrever** o código. Para app nova → SQS/SNS.
- **Stateless vs stateful:** sessões fora da instância (ElastiCache/DynamoDB), uploads para S3, para permitir escala horizontal.
- **Como cai:** "Processamento de pedidos falha em picos; precisa escalar workers independentemente" → SQS + Auto Scaling baseado em `ApproximateNumberOfMessages` por instância.

#### 2.1.2 Escalabilidade
- **Horizontal** (mais instâncias; preferível, elástico) vs **vertical** (instância maior; limite, geralmente com downtime). **Auto Scaling:** target tracking, step, scheduled, predictive.
- **Multi-tier:** ALB/NLB, camada web/app/dados independentes, cache, CDN.
- **Migração para containers:** App2Container, ECS/EKS/Fargate, ECR.

#### 2.1.3 Balanceadores de carga (ELB)
| Tipo | Camada | Quando |
|---|---|---|
| **ALB** | 7 (HTTP/HTTPS/gRPC) | Roteamento por path/host/header/query, WebSocket, Lambda como target, autenticação OIDC/Cognito, WAF |
| **NLB** | 4 (TCP/UDP/TLS) | Milhões de req/s, latência ultrabaixa, **IP estático/Elastic IP por AZ**, PrivateLink |
| **GWLB** | 3 (GENEVE) | Inserir appliances de terceiros (firewall/IDS) de forma transparente |
| **CLB** | legado | Evitar |
- **Cross-zone**, **sticky sessions**, **connection draining/deregistration delay**, health checks, SNI. **Preservação do IP do cliente:** ALB via `X-Forwarded-For`; NLB preserva o IP de origem.
- **Como cai:** "Requisito de IP fixo para allow-list do parceiro" → NLB com EIP (ou Global Accelerator). "Roteamento por caminho de URL a microsserviços" → ALB.

#### 2.1.4 API, serverless e containers
- **API Gateway** (REST/HTTP/WebSocket; throttling, cache, usage plans, authorizers), **AppSync** (GraphQL gerenciado), **Lambda** (15 min, event-driven), **Fargate** (containers sem servidor), **ECS** (orquestrador AWS) vs **EKS** (Kubernetes; portabilidade), **App Runner**, **Step Functions**.
- **Quando contêiner vs serverless:** Lambda para eventos curtos e picos; Fargate/ECS para processos longos/portáveis; EKS quando já usa Kubernetes.
- **Transfer Family:** SFTP/FTPS/FTP para S3/EFS — "manter clientes SFTP existentes".

#### 2.1.5 Armazenamento por tipo
| Tipo | Serviço | Notas |
|---|---|---|
| **Bloco** | **EBS** | 1 AZ, anexa a 1 instância (exceto io1/io2 Multi-Attach), snapshots |
| **Arquivo** | **EFS** (NFS/Linux, multi-AZ, elástico), **FSx** (Windows File Server/SMB, Lustre/HPC, NetApp ONTAP, OpenZFS) | |
| **Objeto** | **S3** | 11 noves de durabilidade |
| Instance store | Disco local efêmero, altíssimo IOPS, perde dados ao parar/terminar | |
- **Como cai:** "Compartilhar arquivos entre centenas de instâncias Linux" → EFS. "Compartilhar entre servidores Windows com AD" → FSx for Windows. "HPC com S3" → FSx for Lustre.

#### 2.1.6 Bancos e réplicas de leitura
- **Read replicas** (RDS/Aurora): escalam **leitura** (assíncronas), podem ser cross-region, promovíveis. **Não** substituem Multi-AZ (que é HA/síncrono). Aurora: até 15 réplicas, endpoint de leitura.

### 2.2 Task 2.2 — Alta disponibilidade e tolerância a falhas

#### 2.2.1 HA vs tolerância a falhas
- **Alta disponibilidade:** minimiza downtime (ex.: Multi-AZ com failover). **Tolerância a falhas:** continua sem interrupção mesmo com falha (redundância ativa). Eliminar **SPOF** em cada camada.

#### 2.2.2 Rede e DNS
- **Route 53:** políticas **Simple, Weighted, Latency, Failover (ativo-passivo com health check), Geolocation, Geoproximity, Multivalue**; **alias** (grátis, ponto de apex, para ELB/CloudFront/S3/API GW); health checks; **Resolver** (híbrido).
- **Global Accelerator:** 2 IPs anycast estáticos, roteia pela rede AWS, failover rápido (não depende de cache DNS), TCP/UDP. vs **CloudFront** (cache HTTP/S).
- **Como cai:** "Failover regional rápido sem esperar TTL do DNS, IPs fixos" → Global Accelerator.

#### 2.2.3 Banco de dados HA
- **RDS Multi-AZ:** standby **síncrono** em outra AZ, failover automático (DNS), **não** serve leitura (instância); **Multi-AZ DB cluster** (2 readable standbys). **Aurora:** armazenamento 6 cópias em 3 AZs, failover <~30 s, **Aurora Global Database** (1 região primária + até **10 secundárias** somente leitura; replicação por infraestrutura dedicada, latência típica **<1 s**; promover uma secundária em **<1 min**; *switchover* planejado sem perda de dados vs *failover* em caso de falha; *write forwarding* encaminha escritas ao primário; cada cluster secundário aceita até 16 réplicas), **Aurora Serverless v2**. **DynamoDB Global Tables.** **RDS Proxy:** pool de conexões e failover mais rápido (útil com Lambda).
- **ElastiCache:** Redis Multi-AZ com failover; Memcached não replica.

#### 2.2.4 Recuperação de desastres (DR)
| Estratégia | RPO/RTO | Custo | Descrição |
|---|---|---|---|
| **Backup & Restore** | horas | $ | Backups (inclusive cross-region); recria tudo após o desastre |
| **Pilot Light** | dezenas de min | $$ | Dados replicados continuamente + infraestrutura núcleo; servidores de aplicação **desligados** (precisam ser ligados/escalados). Não atende requisição sem ação prévia |
| **Warm Standby** | minutos | $$$ | Cópia **reduzida porém totalmente funcional e já ligada**; atende tráfego imediatamente (capacidade reduzida) e só precisa **escalar** |
| **Multi-site active-active** | ~zero | $$$$ | Capacidade total em ambas as regiões |
- **RPO** = quanto dado posso perder (tempo desde o último backup/replicação); **RTO** = quanto tempo posso ficar fora.
- Ferramentas: AWS Backup, S3 CRR, **AWS Elastic Disaster Recovery (DRS)**, Aurora Global DB, DynamoDB Global Tables, Route 53 failover, CloudFormation para recriar.
- **Como cai:** "RPO de minutos e RTO de minutos com menor custo possível" → warm standby/pilot light conforme valores; "RTO de horas, custo mínimo" → backup & restore.

#### 2.2.5 Outros conceitos
- **Infraestrutura imutável** (substituir em vez de patchear; AMIs douradas). **Service quotas** (planejar cotas na região de standby). **X-Ray** para visibilidade. **Serviços gerenciados para legado:** RDS Proxy, EFS, Application Migration Service, ALB com Auto Scaling para apps não-cloud-native, **EC2 Auto Recovery**.
- **Placement groups:** Cluster (baixa latência, mesma AZ), Spread (poucas instâncias críticas em hardware distinto), Partition (grandes sistemas distribuídos: Hadoop/Cassandra).

---

## 3. DOMÍNIO 3 — Design High-Performing Architectures (24%)

### 3.1 Task 3.1 — Armazenamento de alta performance/escalável
- **EBS tipos (valores da doc oficial):**
| Tipo | Tamanho | IOPS máx | Throughput máx | Observações |
|---|---|---|---|---|
| **gp3** | 1 GiB–64 TiB | 80.000 | 2.000 MiB/s | IOPS e throughput **independentes** do tamanho; boot ✔; Multi-Attach ✘ |
| **gp2** | 1 GiB–16 TiB | 16.000 | 250 MiB/s | IOPS atrelado ao tamanho; boot ✔ |
| **io2 Block Express** | 4 GiB–64 TiB | 256.000 | 4.000 MiB/s | Durabilidade **99,999%**, latência <500 µs; **Multi-Attach ✔** |
| **io1** | 4 GiB–16 TiB | 64.000 | 1.000 MiB/s | Multi-Attach ✔ |
| **st1** (HDD) | 125 GiB–16 TiB | 500 | 500 MiB/s | Big data, logs; **não** boot |
| **sc1** (HDD frio) | 125 GiB–16 TiB | 250 | 250 MiB/s | Mais barato; **não** boot |
  - Volumes gp2/gp3/io1 têm durabilidade 99,8–99,9%; **Multi-Attach só em io1/io2**. Apenas SSD pode ser volume de boot. Para aproveitar IOPS provisionado, usar instâncias *EBS-optimized* (Nitro).
- **S3 desempenho:** 3.500 PUT / 5.500 GET por segundo **por prefixo**; **multipart**, **Transfer Acceleration**, **byte-range fetch**, S3 Select; consistência forte.
- **EFS:** modos General Purpose vs Max I/O (legado), throughput Bursting/Provisioned/Elastic; classes Standard/IA.
- **FSx:** Windows (SMB, AD), Lustre (HPC, integra S3), NetApp ONTAP (multi-protocolo), OpenZFS.
- **Armazenamento híbrido:** **Storage Gateway** (File Gateway → S3 com NFS/SMB; Volume Gateway cached/stored → EBS snapshots; **Tape Gateway** → substitui fitas, S3 Glacier), **DataSync** (transferência agendada/acelerada on-prem ↔ S3/EFS/FSx), **Snow Family** (transferência/computação offline; *atenção:* a AWS informa que o **Snowball Edge não está mais disponível para novos clientes** — alternativas: DataSync online, Data Transfer Terminal, Outposts; o guia SAA-C03 v1.1 ainda lista a família Snow, então o conceito segue cobrável), **Transfer Family**.

### 3.2 Task 3.2 — Computação elástica de alto desempenho
- **EC2 famílias:** **T** (burstable), **M** (uso geral), **C** (compute), **R/X/z** (memória), **I/D** (storage), **P/G/Inf/Trn** (GPU/ML), **Graviton (arm64, sufixo g)** — melhor preço/desempenho. Nitro. Enhanced networking, **EFA**.
- **Auto Scaling:** grupos Multi-AZ, launch templates, políticas, health checks ELB, *warm pools*, scale por métrica customizada (ex.: backlog SQS por instância).
- **Containers e serverless:** ECS/EKS/Fargate, Lambda (memória define CPU), **Batch** (jobs em lote), **EMR** (Hadoop/Spark gerenciado), **Elastic Beanstalk** (PaaS), App Runner.
- **Desacoplar** para escalar independentemente: SQS/SNS/Kinesis/EventBridge.
- **Como cai:** "Job em lote com milhares de tarefas, custo baixo" → AWS Batch com **Spot**. "Escalar workers conforme fila" → Auto Scaling por backlog.

### 3.3 Task 3.3 — Bancos de dados de alta performance
| Necessidade | Serviço |
|---|---|
| Relacional OLTP, MySQL/PostgreSQL/Oracle/SQL Server | **RDS** |
| Relacional de alto desempenho/cloud-native (MySQL/PostgreSQL compat.), até 15 réplicas | **Aurora** |
| Carga variável/imprevisível relacional | **Aurora Serverless v2** |
| Chave-valor/documento ms, escala ilimitada | **DynamoDB** (+ **DAX**) |
| Cache em memória, sessões, leaderboards | **ElastiCache** (Redis/Memcached) |
| Durabilidade + microsegundos (primário em memória) | **MemoryDB for Redis** |
| Data warehouse colunar/OLAP | **Redshift** |
| Documentos MongoDB-compat. | **DocumentDB** |
| Grafos | **Neptune** |
| Cassandra | **Keyspaces** |
| Ledger imutável | **QLDB** *(descontinuado pela AWS; ainda aparece no guia)* |
| Busca/análise de logs | **OpenSearch** |
| Séries temporais | **Timestream** |
- **Padrões:** leitura intensiva → read replicas/cache; escrita intensiva → DynamoDB/sharding/Aurora; **RDS Proxy** para conexões; **Provisioned IOPS** (io1/io2) para latência de I/O previsível; Performance Insights.
- **Migração:** **DMS** (homogênea e heterogênea; CDC para mínima downtime) + **SCT** (converte esquema em heterogênea, ex.: Oracle → Aurora PostgreSQL). Aurora Babelfish p/ SQL Server.
- **DynamoDB:** capacidade provisionada vs on-demand, GSI/LSI, DAX (cache para leitura eventual), Global Tables, TTL, Streams, PITR.
- **Como cai:** "Leitura de milissegundos em milhões de req/s, sem gerenciar servidores" → DynamoDB. "Acelerar leitura do DynamoDB sem mudar app" → DAX. "Migrar Oracle on-prem para Aurora PostgreSQL" → SCT + DMS.

### 3.4 Task 3.4 — Arquiteturas de rede de alta performance
- **CloudFront:** CDN (conteúdo estático/dinâmico, streaming, HTTPS, OAC para S3, signed URLs/cookies, WAF, Lambda@Edge/CloudFront Functions, geo restriction, field-level encryption, Origin Groups para failover).
- **Global Accelerator** vs **CloudFront:** GA = IP anycast fixo, TCP/UDP, sem cache (jogos, VoIP, failover rápido); CloudFront = cache HTTP/S.
- **Conectividade:** VPN, DX, PrivateLink, Peering, Transit Gateway; **Enhanced networking/ENA**, **placement group cluster**.
- **Topologia:** subnets em múltiplas AZs, planejamento de CIDR e crescimento, roteamento, IPv6.
- **Balanceamento:** ALB/NLB/GWLB (ver 2.1.3).
- **Como cai:** "Usuários globais reclamam de latência em conteúdo estático" → CloudFront. "Jogo UDP multi-região" → Global Accelerator/NLB.

### 3.5 Task 3.5 — Ingestão e transformação de dados
- **Streaming:** **Kinesis Data Streams** (ordem por shard, replay), **Data Firehose** (entrega a S3/Redshift/OpenSearch, near real time, transforma com Lambda), **Kinesis Data Analytics / Managed Service for Apache Flink** (SQL/Flink em stream), **MSK** (Kafka), **Kinesis Video Streams**.
- **Data lake:** S3 + **Glue** (ETL serverless, **Data Catalog**, crawlers), **Lake Formation** (permissões finas e governança do lake), **Athena** (SQL serverless sobre S3; cobra por dado varrido → Parquet/ORC + partições + compressão), **EMR**, **Redshift Spectrum**, **QuickSight** (BI), **OpenSearch**.
- **Formatos:** CSV → Parquet/ORC (colunar, compactado) reduz custo e acelera consultas.
- **Transferência:** DataSync, Snow Family, Transfer Family, Storage Gateway, DMS, **AppFlow**; escolher por **volume × banda × prazo** (ex.: 100 TB com link de 100 Mbps → Snowball Edge).
- **Como cai:** "Consultas SQL ad hoc em logs no S3 sem servidores" → Athena (+ Glue Catalog). "Ingestão de milhões de eventos/s com replay" → Kinesis Data Streams.

---

## 4. DOMÍNIO 4 — Design Cost-Optimized Architectures (20%)

### 4.1 Task 4.1 — Armazenamento otimizado em custo
- **Classes S3 (doc oficial):**
| Classe | Disponib. | AZs | Duração mín. | Tam. mín. cobrado | Observação |
|---|---|---|---|---|---|
| Standard | 99,99% | ≥3 | — | — | Padrão, acesso frequente |
| **Intelligent-Tiering** | 99,9% | ≥3 | — | objetos <128 KB não são monitorados | Sem taxa de recuperação; taxa de monitoramento por objeto; 30 d → Infrequent, 90 d → Archive Instant; camadas opcionais Archive (90 d) e Deep Archive (180 d) |
| Standard-IA | 99,9% | ≥3 | 30 d | 128 KB | Taxa por GB recuperado |
| One Zone-IA | **99,5%** | **1** | 30 d | 128 KB | Não resiste à perda da AZ; bom para réplicas CRR e dados recriáveis |
| **Express One Zone** | 99,95% | 1 | — | — | Latência de ms de um dígito, directory buckets |
| Glacier Instant Retrieval | 99,9% | ≥3 | **90 d** | 128 KB | Acesso em ms, ~1x por trimestre |
| Glacier Flexible Retrieval | 99,99% (após restaurar) | ≥3 | 90 d | +40 KB de metadados | Minutos a horas; requer `RestoreObject` |
| **Glacier Deep Archive** | 99,99% (após restaurar) | ≥3 | **180 d** | +40 KB de metadados | Horas; mais barato |
  - Durabilidade de todas: 99,999999999% (11 noves). O RRS (Reduced Redundancy) é legado e **não recomendado**.
- **Lifecycle:** transições + expiração; limpar uploads multipart incompletos; versões antigas.
- **Requester Pays**, **S3 Storage Lens**, análise de classe.
- **EBS:** escolher tipo (gp3 mais barato que gp2 com mesmo desempenho; sc1/st1 para HDD), apagar snapshots/volumes órfãos, Data Lifecycle Manager.
- **EFS-IA / lifecycle** e **FSx** com deduplicação/compressão. **Backup:** AWS Backup com retenção. 
- **Transferência barata:** DataSync/Snow para volumes grandes; Transfer Acceleration só se compensa; uploads em lote/multipart.
- **Ferramentas de custo:** **Cost Explorer** (análise/previsão), **Budgets** (alertas/ações), **Cost and Usage Report** (detalhado → Athena), **Cost Allocation Tags**, **Consolidated Billing** (descontos por volume), **Trusted Advisor**, **Compute Optimizer**.
- **Como cai:** "Logs acessados por 30 dias e raramente depois, retenção 7 anos, custo mínimo" → lifecycle: Standard → IA → Glacier/Deep Archive.

### 4.2 Task 4.2 — Computação otimizada em custo
- **Modelos de compra:** On-Demand · **Reserved Instances** (1/3 anos; Standard vs Convertible) · **Savings Plans** (Compute: flexível entre famílias/regiões/Lambda/Fargate; EC2 Instance: família+região) · **Spot** (até ~90% off, **interrompível com aviso de 2 min** → cargas tolerantes a falhas: batch, CI, big data, stateless) · **Dedicated Hosts/Instances** (licenças/compliance) · **Capacity Reservations**.
- **Rightsizing:** Compute Optimizer, instâncias Graviton, burstable T para cargas leves.
- **Serverless para cargas esporádicas** (Lambda/Fargate); Auto Scaling para ajustar; **hibernação** (EC2 preserva RAM → retoma rápido); desligar não-produção fora do horário (Instance Scheduler).
- **Híbrido:** Outposts (infra AWS on-prem), Snowball Edge (edge compute).
- **Como cai:** "Carga previsível 24/7 por 3 anos" → Reserved/Savings Plans. "Processamento em lote que pode reiniciar" → Spot. "Workload variável entre famílias/serviços" → Compute Savings Plan.

### 4.3 Task 4.3 — Bancos de dados otimizados em custo
- **DynamoDB** on-demand (imprevisível) vs provisioned + auto scaling + **reserved capacity** (previsível); **Standard-IA table class**; TTL para apagar; DAX/ElastiCache reduzem leituras.
- **RDS/Aurora:** Reserved Instances, Aurora Serverless v2 (carga variável), Aurora I/O-Optimized (I/O pesado), read replicas vs cache, **parar** instâncias de dev, snapshots/retenção racionais, **RDS Proxy**.
- **Tipo certo de banco:** Timestream (séries temporais), Redshift (colunar OLAP), DocumentDB, Neptune.
- **Migração:** DMS/SCT, licenças (Bring-your-own-license vs License Included).

### 4.4 Task 4.4 — Redes otimizadas em custo
- **NAT Gateway:** cobra por hora **e por GB**; um por AZ (HA) vs um compartilhado (mais barato, mas cross-AZ e SPOF); **NAT instance** (mais barato em baixo volume, mas manual); preferir **VPC endpoints (Gateway grátis)** para S3/DynamoDB e reduzir tráfego via NAT.
- **Transferência de dados:** entrada grátis; saída para internet paga; **entre AZs paga**; entre regiões paga; mesma AZ por IP privado grátis → manter tráfego intenso na mesma AZ quando possível; **CloudFront** reduz custo de saída da origem.
- **Conectividade:** VPN (barata, internet) vs Direct Connect (previsível, custo fixo + dados mais baratos em alto volume); **Transit Gateway** (cobra por anexo e dado) vs **VPC Peering** (sem custo por hora; sem transitividade).
- **CDN/edge:** CloudFront price classes, cache hit ratio; Global Accelerator cobra por hora + DT.
- **Throttling/API:** API Gateway usage plans, limites.
- **Como cai:** "Reduzir custo do NAT Gateway para tráfego a S3" → Gateway endpoint. "Tráfego cross-AZ caro" → colocar componentes que conversam muito na mesma AZ (preservando HA).

---

## 5. Confrontos Clássicos (decisões mais cobradas)

| Confronto | Regra de decisão |
|---|---|
| S3 vs EBS vs EFS vs FSx | Objeto · Bloco de 1 instância · NFS Linux compartilhado · SMB/HPC/NetApp |
| SG vs NACL | Stateful/allow · Stateless/allow+deny/subnet |
| NAT Gateway vs NAT Instance | Gerenciado, escalável · Manual, barato em baixo volume |
| Gateway vs Interface endpoint | S3/DynamoDB grátis · Demais serviços/PrivateLink |
| VPC Peering vs Transit Gateway vs PrivateLink | Ponto a ponto · Hub transitivo · Expor serviço |
| VPN vs Direct Connect | Rápido/barato/criptografado · Dedicado/estável/semanas |
| ALB vs NLB vs GWLB | L7 · L4/IP fixo/UDP · Appliances |
| CloudFront vs Global Accelerator | Cache HTTP · IP anycast TCP/UDP |
| Multi-AZ vs Read Replica | HA síncrono · Escala leitura assíncrona |
| RDS vs Aurora vs DynamoDB | Engine padrão · Cloud-native relacional · NoSQL serverless |
| DAX vs ElastiCache | Cache DynamoDB · Cache genérico |
| SQS vs SNS vs EventBridge vs Kinesis vs MQ | Fila · Pub/sub · Regras/SaaS · Stream · Protocolos legados |
| Standard vs FIFO | Escala · Ordem + dedupe |
| KMS vs CloudHSM | Gerenciado · HSM dedicado, chaves suas |
| Secrets Manager vs Parameter Store | Rotação · Simples/barato |
| GuardDuty vs Inspector vs Macie | Ameaças · Vulnerabilidades · PII |
| WAF vs Shield | L7 regras · DDoS |
| Savings Plans vs Reserved vs Spot | Flexível · Específico · Interrompível |
| S3 IA vs One Zone-IA vs Glacier | Acesso raro · Recriável · Arquivo |
| Backup&Restore vs Pilot Light vs Warm Standby vs Active-Active | RTO/RPO × custo |
| DataSync vs Storage Gateway vs Snowball vs Transfer Family | Migração online agendada · Híbrido contínuo · Offline · SFTP |
| ECS vs EKS vs Fargate vs Lambda | AWS-nativo · Kubernetes · Sem servidor p/ containers · Eventos |
| Step Functions vs SQS vs SWF | Orquestração visual · Fila · Legado |
| Athena vs Redshift vs EMR | SQL serverless S3 · DW colunar · Hadoop/Spark |
| Kinesis Streams vs Firehose | Replay/ordem · Entrega a destino |
| Aurora Global vs Multi-AZ vs Read Replica cross-region | DR global RPO<1s · HA local · Leitura remota |

---

## 6. Números para Decorar
| Item | Valor |
|---|---|
| S3 durabilidade / disponibilidade Standard | 99,999999999% (11 noves) / 99,99% |
| S3 tamanho máx. de objeto / PUT único | 5 TB / 5 GB |
| S3 performance | 3.500 write / 5.500 read por prefixo/s |
| Spot aviso | 2 minutos |
| EBS Multi-Attach | só io1/io2 (confirmado na doc), mesma AZ, instâncias Nitro (limite de instâncias: conferir doc) |
| Aurora | 6 cópias / 3 AZs; até 15 réplicas |
| Read replicas | Aurora: até **15** (mesmo volume de storage) · RDS: depende do engine (conferir cota atual); replicação **assíncrona**; RDS **não** escala réplicas automaticamente (criação manual) |
| NLB | IP estático por AZ; milhões de req/s |
| Lambda | 15 min, 10 GB RAM |
| Direct Connect | 1/10/100 Gbps (hosted: 50 Mbps–25 Gbps) |
| VPN | 2 túneis por conexão; 1,25 Gbps/túnel (5 Gbps com Large Bandwidth Tunnel via TGW) |
| SQS | mensagem até **1 MiB**; retenção 1 min–14 d (padrão 4 d) |
| Snowball Edge Storage Optimized | 210 TB utilizáveis (NVMe) na doc atual; Compute Optimized: 104 vCPUs, 416 GB RAM utilizáveis, 28 TB NVMe. Materiais antigos citam ~80 TB |
| Spot | aviso de interrupção de **2 min** (via EventBridge e metadata; hibernação não recebe os 2 min) |
| CloudFront | invalidação, TTL padrão 24 h |
| Route 53 | health checks, TTL; alias grátis |
| DynamoDB item | 400 KB |
| KMS direto | 4 KB |
> ⚠️ Cotas mudam; confirme na doc oficial.

## 7. Outros serviços in-scope (resumo de 1 linha)
Amazon Comprehend (NLP), Polly (texto→voz), Rekognition (imagem/vídeo), Transcribe (voz→texto), Translate, Textract (OCR de documentos), Lex (chatbots), Kendra (busca inteligente), SageMaker (ML), Forecast (previsão), Fraud Detector — *saber qual IA gerenciada resolve qual problema.* · AppSync (GraphQL) · Amplify (full-stack web/mobile) · Pinpoint (marketing/engajamento) · Elastic Transcoder/MediaConvert (transcodificação, via Elastic Transcoder na lista) · CloudFormation (IaC) · Systems Manager (patch, Session Manager, Parameter Store) · Trusted Advisor (checks de custo/segurança/limites) · Health Dashboard · Proton · Service Catalog · License Manager · Well-Architected Tool · Managed Grafana/Prometheus · Data Exchange (dados de terceiros).

## 8. Tabela de Palavras-Gatilho
| Se a pergunta diz… | Pense em… |
|---|---|
| "decouple", "buffer spikes" | SQS |
| "fan-out", "multiple subscribers" | SNS → SQS |
| "ordered, exactly once" | SQS FIFO |
| "real-time streaming, replay" | Kinesis Data Streams |
| "serverless", "no servers to manage" | Lambda, Fargate, DynamoDB, Aurora Serverless |
| "static content global users, low latency" | CloudFront |
| "static anycast IP, UDP, fast regional failover" | Global Accelerator |
| "static IP load balancer" | NLB |
| "path-based routing" | ALB |
| "third-party firewall appliance" | GWLB |
| "private connection to AWS, consistent latency" | Direct Connect |
| "encrypted quickly over internet" | Site-to-Site VPN |
| "many VPCs and on-prem" | Transit Gateway |
| "expose service privately" | PrivateLink |
| "access S3 privately, no cost" | Gateway endpoint |
| "SQL injection, XSS" | WAF |
| "DDoS" | Shield (+ CloudFront/WAF) |
| "threat detection" | GuardDuty |
| "PII in S3" | Macie |
| "vulnerability scan EC2/ECR" | Inspector |
| "compliance/config history" | AWS Config |
| "who called API" | CloudTrail |
| "central multi-account governance" | Organizations + SCP + Control Tower |
| "federate corporate AD to console" | IAM Identity Center / SAML |
| "dedicated HSM" | CloudHSM |
| "immutable WORM" | S3 Object Lock / Vault Lock |
| "unknown access pattern" | S3 Intelligent-Tiering |
| "interruptible/fault tolerant, cheapest" | Spot |
| "steady-state 1–3 years" | Reserved / Savings Plans |
| "Linux shared file system" | EFS |
| "Windows SMB shared" | FSx for Windows |
| "HPC high throughput" | FSx for Lustre |
| "on-prem to S3 hybrid file" | Storage Gateway File |
| "bulk offline data transfer" | Snowball Edge |
| "ongoing online migration to S3/EFS" | DataSync |
| "SFTP to S3" | Transfer Family |
| "ad hoc SQL on S3" | Athena |
| "data warehouse" | Redshift |
| "ETL serverless" | Glue |
| "lowest RTO and RPO" | Multi-site active-active |
| "database failover automatic" | Multi-AZ / Aurora |
| "scale reads" | Read replicas / cache |
| "heterogeneous DB migration" | SCT + DMS |
| "least operational overhead" | Managed/serverless |

---

## 9. Checklist de Estudo
- [ ] D1: IAM/Organizations/SCP/Identity Center, VPC (SG/NACL/endpoints), KMS, proteções (WAF/Shield/GuardDuty)
- [ ] D2: SQS/SNS/EventBridge, ELB, Auto Scaling, Multi-AZ/Aurora, DR (4 estratégias), Route 53
- [ ] D3: EBS tipos, S3 performance, EFS/FSx, Aurora/DynamoDB/ElastiCache, CloudFront/GA, Kinesis/Glue/Athena
- [ ] D4: S3 classes/lifecycle, modelos de compra, NAT/transferência, ferramentas de custo
- [ ] Well-Architected: 6 pilares
- [ ] Simulados cronometrados (65 questões/130 min)

*Próximo passo:* gerar questões com [[SAA-C03 - Prompts de Questoes]].
