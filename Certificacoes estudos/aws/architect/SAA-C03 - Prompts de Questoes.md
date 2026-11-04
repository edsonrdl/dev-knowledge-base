---
tags: [aws, certificacao, solutions-architect-associate, saa-c03, prompts, questoes]
exame: SAA-C03
verificado-em: 2026-11-04
status: completo-v1
---

# 🧪 Prompts para Gerar Questões — AWS Solutions Architect Associate (SAA-C03)

> Cole o prompt numa IA junto com [[SAA-C03 - Glossario]] como contexto. Os IDs de task (1.1, 2.2, 3.4…) são os do Exam Guide oficial.
> Mesma regra de ética do [[DVA-C03 - Prompts de Questoes]]: **nada de brain dumps**; gere questões originais e valide na documentação ([[Referencias e Fontes]]).

## 1. Anatomia da questão SAA (diferente do Developer)
- **Foco:** *decisão de arquitetura* sob restrições de negócio, não código.
- **Estrutura:** (1) cenário da empresa e da carga; (2) requisitos funcionais e não funcionais (RPO/RTO, latência, compliance, orçamento, equipe pequena); (3) pergunta com qualificador; (4) 4 opções ou 5–6 com "Select TWO/THREE".
- **Distratores típicos:** arquitetura que funciona porém (a) tem SPOF, (b) é mais cara, (c) exige gerenciar servidores, (d) não atende RPO/RTO, (e) usa o serviço "parecido" errado, (f) quebra um requisito escondido (ex.: UDP, IP fixo, Windows/SMB, cross-region).

### 1.1 Tipos (use em `{{TIPOS}}`)
| Código | Tipo |
|---|---|
| A1 | Escolha de serviço pelo requisito decisivo |
| A2 | Melhor arquitetura multi-serviço |
| A3 | Otimizar custo de arquitetura existente |
| A4 | Melhorar resiliência/HA/DR de arquitetura existente |
| A5 | Segurança: política, rede, criptografia, multi-conta |
| A6 | Migração (dados, banco, aplicação) |
| A7 | Múltipla resposta (Select TWO/THREE) |
| A8 | Desempenho (storage, banco, rede, compute) |
| A9 | Comparação X vs Y com requisito oculto |

### 1.2 Níveis
Básico (1 serviço) · Intermediário (2–3 serviços + qualificador) · Avançado (multi-conta/região, 3+ restrições).

---

## 2. PROMPT MESTRE
```text
Atue como examinador sênior da AWS elaborando questões para o
AWS Certified Solutions Architect – Associate (SAA-C03), baseado no Well-Architected Framework.

CONTEXTO
- Escopo: Exam Guide oficial SAA-C03 (glossário anexado). Não use serviços listados como fora de escopo.
- Domínio: {{DOMINIO}}   (ex.: Domain 2 – Design Resilient Architectures)
- Task Statement: {{TASK}} (ex.: 2.2 Design highly available and/or fault-tolerant architectures)
- Subtópicos: {{SUBTOPICOS}} (ex.: DR strategies, Route 53 failover, Aurora Global Database)

TAREFA
Gere {{QTD}} questões ORIGINAIS, nível {{NIVEL}}, tipos {{TIPOS}}, em inglês estilo prova e depois em português.

REGRAS
1. Cenário de negócio realista (2–6 linhas) com requisitos mensuráveis (RPO/RTO, latência, custo, equipe).
2. Pergunta com qualificador (MOST cost-effective / LEAST operational overhead / MOST secure /
   highly available / minimal downtime / without changing the application).
3. Um requisito "oculto" que elimina duas opções (ex.: protocolo, IP estático, SMB, imutabilidade).
4. 4 opções (A–D) ou 5–6 com Select TWO/THREE. Distratores plausíveis. Sem "All of the above".
5. Balancear a posição da resposta correta. Não copiar questões reais ou de dumps.

SAÍDA por questão
- Questão + opções
- Gabarito
- Por que a correta atende TODOS os requisitos
- Por que cada incorreta falha (qual requisito ela viola)
- Pilar do Well-Architected envolvido
- Palavra-gatilho
- Pegadinha
- Task coberta + link da doc AWS que valida
- Tradução em português
Finalize com tabela: ID | Task | Tipo | Nível | Gabarito.
```

---

## 3. PROMPTS POR DOMÍNIO

### 3.1 Domínio 1 — Design Secure Architectures (30%)

#### Task 1.1 — Acesso seguro
```text
Aplique o PROMPT MESTRE. Domínio 1, Task 1.1. Gere 15 questões A2/A5/A7/A9.
Cubra: root user e MFA, roles vs usuários, avaliação de políticas (deny explícito),
permissions boundary, Organizations + SCP (o que SCP faz e NÃO faz), Control Tower, IAM Identity Center,
acesso cross-account com STS, federação SAML/OIDC, Directory Service (Managed AD vs AD Connector vs Simple AD),
resource policies, RAM, Access Analyzer, responsabilidade compartilhada.
```

#### Task 1.2 — Workloads e aplicações seguras
```text
Aplique o PROMPT MESTRE. Domínio 1, Task 1.2. Gere 20 questões A1/A2/A5/A7/A9.
Cubra: VPC pública/privada, SG vs NACL (stateful x stateless, bloquear IP), NAT Gateway por AZ,
Gateway vs Interface endpoints, PrivateLink, Peering vs Transit Gateway, VPN vs Direct Connect (+ cripto),
WAF, Shield, Network Firewall, Firewall Manager, GuardDuty vs Inspector vs Macie vs Detective vs Security Hub,
Cognito, Secrets Manager, mitigação de DDoS e SQL injection, Flow Logs, bastion vs Session Manager.
```

#### Task 1.3 — Segurança de dados
```text
Aplique o PROMPT MESTRE. Domínio 1, Task 1.3. Gere 15 questões A1/A5/A6/A7.
Cubra: KMS (tipos de chave, key policy, rotação, multi-region), CloudHSM vs KMS, criptografia de EBS/RDS/S3
(incl. criptografar RDS existente via snapshot), ACM e TLS, Object Lock compliance vs governance,
Vault Lock, versioning/MFA Delete, replicação CRR/SRR, AWS Backup (cross-account, Vault Lock),
classificação com Macie, AWS Artifact, retenção e lifecycle de compliance.
```

### 3.2 Domínio 2 — Design Resilient Architectures (26%)

#### Task 2.1 — Escaláveis e desacopladas
```text
Aplique o PROMPT MESTRE. Domínio 2, Task 2.1. Gere 20 questões A1/A2/A7/A9.
Cubra: SQS (Standard/FIFO/DLQ/visibility), SNS fan-out, EventBridge, Kinesis, Amazon MQ (migração sem reescrever),
MSK, Step Functions, API Gateway vs AppSync, ALB vs NLB vs GWLB, stateless/sessões, escala horizontal x vertical,
Fargate/ECS/EKS/Lambda (quando usar cada), S3 vs EBS vs EFS vs FSx, Transfer Family, read replicas.
```

#### Task 2.2 — HA e tolerância a falhas
```text
Aplique o PROMPT MESTRE. Domínio 2, Task 2.2. Gere 20 questões A2/A4/A7 (ênfase em A4 e DR).
Cubra: Multi-AZ x Read Replica, Aurora (6 cópias, Global Database), RDS Proxy, DynamoDB Global Tables,
Route 53 (todas as políticas e failover com health check), Global Accelerator vs CloudFront,
quatro estratégias de DR com RPO/RTO numéricos, Elastic Disaster Recovery, AWS Backup cross-region,
infraestrutura imutável, service quotas na região de standby, X-Ray, placement groups,
EC2 auto recovery, SPOFs em arquiteturas apresentadas.
```

### 3.3 Domínio 3 — Design High-Performing Architectures (24%)

#### Tasks 3.1 e 3.2 — Storage e compute
```text
Aplique o PROMPT MESTRE. Domínio 3, Tasks 3.1 e 3.2. Gere 20 questões A1/A8/A9.
Cubra: tipos de EBS (gp3, io2, st1, sc1) e quando cada um, instance store, S3 performance (prefixos, multipart,
Transfer Acceleration), EFS vs FSx (Windows, Lustre, NetApp, OpenZFS), Storage Gateway (File/Volume/Tape),
DataSync, Snow Family, famílias de instância EC2 (C/M/R/I/G/P/T, Graviton), Auto Scaling (políticas e
métricas, backlog de fila), placement groups, Batch, EMR, Lambda memória e Fargate.
```

#### Tasks 3.3, 3.4 e 3.5 — Banco, rede e dados
```text
Aplique o PROMPT MESTRE. Domínio 3, Tasks 3.3, 3.4 e 3.5. Gere 25 questões A1/A2/A6/A8/A9.
Cubra: escolha de banco (RDS, Aurora, Aurora Serverless, DynamoDB+DAX, ElastiCache Redis/Memcached,
MemoryDB, Redshift, DocumentDB, Neptune, Keyspaces, Timestream, OpenSearch), Provisioned IOPS, read replicas,
DMS+SCT, CloudFront vs Global Accelerator, Direct Connect/VPN/PrivateLink/Transit Gateway, topologia multi-camada,
Kinesis Streams vs Firehose, Glue, Athena (Parquet/partições), Lake Formation, EMR, QuickSight,
formatos CSV→Parquet, escolha de transferência por volume × banda.
```

### 3.4 Domínio 4 — Design Cost-Optimized Architectures (20%)
```text
Aplique o PROMPT MESTRE. Domínio 4, Tasks 4.1 a 4.4. Gere 25 questões com ênfase em A3/A1/A7/A9.
Cubra: classes S3 e lifecycle (mínimos de dias/tamanho), EBS gp3 vs gp2, snapshots, EFS-IA, AWS Backup retenção,
Reserved vs Savings Plans (Compute vs EC2 Instance) vs Spot vs On-Demand vs Dedicated, rightsizing
(Compute Optimizer), hibernação, serverless vs EC2, DynamoDB on-demand vs provisioned/reserved,
Aurora Serverless v2 e I/O-Optimized, NAT Gateway (um por AZ vs compartilhado), VPC endpoints para reduzir NAT,
custos de transferência (entre AZs/regiões/internet), VPN vs Direct Connect, Transit Gateway vs Peering,
CloudFront price classes, Cost Explorer vs Budgets vs CUR vs Trusted Advisor, tags de alocação, Organizations.
```

---

## 4. PROMPTS ESPECIAIS

### 4.1 Simulado completo (65 questões)
```text
Monte um simulado SAA-C03 com 65 questões originais na proporção 30/26/24/20
(≈20 D1, 17 D2, 16 D3, 12 D4), ~15% múltipla resposta. Entregue só questões e opções.
Quando eu enviar "GABARITO", envie respostas comentadas e análise por domínio/task.
```

### 4.2 "Revise esta arquitetura" (tipo A3/A4, muito cobrado)
```text
Descreva 8 arquiteturas existentes com falhas (SPOF, custo alto, segurança fraca, performance ruim).
Para cada uma, formule a questão "Which change will ... with the LEAST effort?" e comente as alternativas,
indicando o pilar do Well-Architected violado.
```

### 4.3 Desenho por requisito oculto
```text
Gere 10 questões onde TODAS as opções parecem corretas até que um requisito oculto
(UDP, IP estático, SMB/AD, imutabilidade, mínima mudança de código, cross-account, on-prem híbrido, RTO < 5 min)
elimine as demais. Marque o requisito oculto no gabarito.
```

### 4.4 Matriz de DR
```text
Para 6 combinações de RPO/RTO (ex.: RPO 24h/RTO 24h; RPO 1h/RTO 4h; RPO 5min/RTO 15min; ~0/~0),
gere uma questão cada pedindo a estratégia (Backup&Restore, Pilot Light, Warm Standby, Active-Active)
e os serviços AWS usados na replicação de dados e no failover de tráfego.
```

### 4.5 Comparativo (X vs Y)
```text
Para {{A}} vs {{B}} gere tabela de diferenças decisivas e 6 questões A9 em que o requisito oculto
decide. Exemplos: EFS vs FSx for Windows, Aurora Global vs Cross-Region Read Replica, CloudFront vs Global Accelerator,
ALB vs NLB, SQS vs Amazon MQ, DataSync vs Storage Gateway.
```

### 4.6 Loop de erros e flashcards
```text
Vou colar questões que errei. Para cada uma: conceito que faltou (task), explicação curta, 2 questões gêmeas,
e flashcards "Q:: / A::" focados no requisito decisivo. Ranqueie meus pontos fracos por domínio.
```

---

## 5. EXEMPLOS DE QUESTÕES (originais, formato esperado)

### Exemplo 1 — A2/A4 · Task 2.2 (DR)
**Questão:** A company runs a three-tier web application in us-east-1 with an Amazon Aurora MySQL database. The business requires an RPO of 5 minutes and an RTO of 15 minutes if the Region fails, at the LOWEST cost that still meets the requirements. Which solution should a solutions architect recommend?

- A. Take hourly snapshots and copy them to another Region.
- B. Deploy an Aurora Global Database with a secondary Region, a scaled-down (warm standby) application stack there, and Route 53 failover routing.
- C. Run a full active-active deployment in two Regions with DynamoDB global tables.
- D. Use an RDS read replica in the same Region and promote it on failure.

**Gabarito: B.** A viola o RPO (1 h). C atende, porém é mais caro. D não protege contra falha regional.
- Pilar: Reliability. **Gatilho:** "RPO 5 min / RTO 15 min / Region fails / lowest cost" → warm standby.

### Exemplo 2 — A1/A9 · Task 3.1
**Questão:** A company migrating Windows file servers needs a shared file system that supports SMB, NTFS ACLs, and integrates with the company's Active Directory. Which service should be used with the LEAST operational overhead?

- A. Amazon EFS  B. Amazon FSx for Windows File Server  C. Amazon S3 with File Gateway on EC2  D. Amazon EBS Multi-Attach

**Gabarito: B.** EFS é NFS/Linux; S3+gateway exige gerenciar; EBS Multi-Attach não é file system compartilhado SMB.

### Exemplo 3 — A5 · Task 1.2
**Questão:** A security team needs to block traffic from a specific malicious IP address to an application tier. Which control should be used?

- A. Add a deny rule to the instance security group.
- B. Add a deny rule to the subnet network ACL.
- C. Remove the route to the internet gateway.
- D. Attach an IAM policy to the instances.

**Gabarito: B.** Security groups só têm regras *allow*; NACLs permitem *deny*.

### Exemplo 4 — A3 · Task 4.4
**Questão:** EC2 instances in private subnets download large datasets from Amazon S3 through a NAT gateway, producing high data-processing charges. What is the MOST cost-effective change?

- A. Move the instances to public subnets.
- B. Create an S3 gateway VPC endpoint and update the route tables.
- C. Create an S3 interface endpoint in each AZ.
- D. Use a NAT instance instead.

**Gabarito: B.** Gateway endpoints para S3 não têm custo por hora nem por dado; interface endpoints cobram.

### Exemplo 5 — A7 · Task 4.2 (múltipla resposta)
**Questão:** A company runs a nightly batch processing job that can be interrupted and restarted. The job runs on EC2 for ~6 hours. Which TWO actions reduce cost the MOST? (Select TWO.)

- A. Purchase a 3-year Standard Reserved Instance.
- B. Use Spot Instances with diversified instance types.
- C. Use an Auto Scaling group or AWS Batch to terminate capacity when the job completes.
- D. Use Dedicated Hosts.
- E. Keep instances running 24/7 for faster start.

**Gabarito: B e C.**

### Exemplo 6 — A8 · Task 3.3
**Questão:** An application running on Amazon RDS for MySQL has a read-heavy workload that slows during reporting. The team wants to improve performance with minimal application changes. Which solutions are appropriate? (Select TWO.)

- A. Create read replicas and direct reporting queries to them.
- B. Enable Multi-AZ and send reads to the standby.
- C. Add an Amazon ElastiCache layer for frequently read data.
- D. Increase the backup retention period.
- E. Switch to Amazon S3.

**Gabarito: A e C.** O standby do Multi-AZ clássico não aceita leitura.

---

## 6. Rubrica de validação
- [ ] A task existe no guia oficial e o serviço está no escopo SAA-C03?
- [ ] Há um requisito oculto/qualificador que decide?
- [ ] A resposta correta atende **todos** os requisitos; cada distrator viola pelo menos um?
- [ ] RPO/RTO/limites conferem com a doc?
- [ ] Mapeado a um pilar do Well-Architected?

## 7. Cronograma de geração sugerido
D1 (IAM/VPC/KMS) → D2 (desacoplar + DR) → D3 (storage/banco/rede/dados) → D4 (custos) → simulados completos → revisão de erros.
