---
tags: [aws, certificacao, developer-associate, dva-c03, prompts, questoes]
exame: DVA-C03
verificado-em: 2026-11-04
status: completo-v1
---

# 🧪 Prompts para Gerar Questões — AWS Developer Associate (DVA-C03)

> Como usar: copie um prompt, troque os campos `{{...}}`, cole numa IA (com o glossário [[DVA-C03 - Glossario]] anexado ou colado como contexto) e gere questões por **domínio → task → skill**.
> Os códigos (ex.: `1.2.3`) são os IDs de skill do Exam Guide oficial e existem no glossário, então a IA consegue ancorar cada questão.

## ⚠️ Regra de ouro (ética e qualidade)
- **Não use "brain dumps"/"exam dumps"** (questões vazadas de provas reais). Violam o acordo de certificação da AWS, podem invalidar sua certificação e frequentemente estão **erradas ou desatualizadas**.
- Gere questões **originais** a partir do guia oficial + documentação. Valide as respostas na doc (links em [[Referencias e Fontes]]).
- Questões de IA podem conter erros: peça **justificativa com a fonte** e confira números/limites.

---

## 1. Anatomia de uma questão de prova (o que a IA deve imitar)

### 1.1 Estrutura obrigatória
1. **Cenário** (2–5 linhas): papel + sistema + problema/necessidade.
2. **Restrição decisiva** (custo, esforço operacional, segurança, latência, sem mudar código).
3. **Pergunta** terminando com o qualificador: *"Which solution will meet these requirements with the LEAST operational overhead?"*
4. **Opções A–D** (múltipla escolha) ou **A–E/F** com "Select TWO/THREE" (múltipla resposta).
5. **Distratores plausíveis**: serviço certo com configuração errada, serviço parecido, solução que funciona mas viola o qualificador, mais código/custo/risco.

### 1.2 Tipos de pergunta mais frequentes (use como `{{TIPO}}`)
| Código | Tipo | Exemplo de enunciado |
|---|---|---|
| T1 | Escolha de serviço | "Which service should the developer use to…" |
| T2 | Configuração correta | "Which configuration will resolve the throttling?" |
| T3 | Diagnóstico por log/erro | "The Lambda logs show `Task timed out`. What is the cause?" |
| T4 | Leitura de código/política | "What does this IAM policy / buildspec / template do?" |
| T5 | Ordem/fluxo | "In what order does CodeDeploy run lifecycle hooks?" |
| T6 | Comparação | "What is the difference between X and Y?" |
| T7 | Múltipla resposta | "Which TWO actions will…?" |
| T8 | Otimização de custo/desempenho | "Which change reduces latency/cost the MOST?" |
| T9 | Segurança | "Which approach is MOST secure?" |

### 1.3 Níveis de dificuldade (use como `{{NIVEL}}`)
- **Básico:** um conceito, uma resposta clara.
- **Intermediário (nível da prova):** cenário + 2 serviços plausíveis + qualificador.
- **Avançado:** cenário com 3+ restrições, distratores quase corretos, múltipla resposta.

---

## 2. PROMPT MESTRE (gerador por tópico/subtópico)

```text
Atue como um examinador sênior da AWS que elabora questões para a certificação
AWS Certified Developer – Associate (DVA-C03).

CONTEXTO
- Use EXCLUSIVAMENTE o escopo do Exam Guide oficial DVA-C03 (anexado como glossário).
- Domínio: {{DOMINIO}}            (ex.: Domain 1 – Development with AWS Services)
- Task: {{TASK}}                  (ex.: Task 1.2 – Develop code for AWS Lambda)
- Skill(s): {{SKILL_IDS}}         (ex.: 1.2.3 – Handle event lifecycles and errors)
- Subtópico(s) de foco: {{SUBTOPICOS}}  (ex.: SQS event source mapping, visibility timeout, DLQ)

TAREFA
Gere {{QTD}} questões ORIGINAIS, nível {{NIVEL}}, tipos {{TIPOS}}
(ex.: T1,T2,T3,T7), em inglês técnico estilo prova (e depois a tradução em português).

REGRAS DE FORMATO
1. Cada questão tem: ID (Q1…), cenário curto, pergunta com qualificador
   (LEAST operational overhead / MOST cost-effective / MOST secure / etc.),
   4 opções (A–D) para escolha única OU 5–6 opções com "Select TWO/THREE".
2. Apenas UMA alternativa correta (ou o número exato indicado). Distratores devem ser
   plausíveis: serviço parecido, configuração errada, solução que viola o qualificador.
3. Distribua a posição da resposta correta de forma equilibrada. Não use "All of the above".
4. Não copie questões reais de prova nem de "dumps". Crie cenários novos.
5. Use apenas serviços e recursos dentro do escopo do DVA-C03; se citar algo fora, avise.

SAÍDA (para cada questão, nesta ordem)
- **Questão** (EN) + opções
- **Gabarito**
- **Por que a correta está correta** (explicação técnica curta, com o mecanismo interno)
- **Por que cada incorreta está errada** (uma linha por opção)
- **Palavra-gatilho** que levaria o candidato à resposta
- **Pegadinha / erro comum**
- **Skill coberta** (ID do guia) e **link da documentação AWS** que valida a resposta
- **Tradução em português** da questão e das opções

Ao final, faça uma tabela-resumo: ID | Skill | Tipo | Nível | Gabarito.
```

---

## 3. PROMPTS PRONTOS POR DOMÍNIO (cole e execute)

### 3.1 Domínio 1 — Development with AWS Services (30%)

#### 3.1.1 Task 1.1 — Código para apps na AWS
```text
Aplique o PROMPT MESTRE. Domínio 1, Task 1.1, skills 1.1.1 a 1.1.8.
Gere 15 questões nível intermediário, mix T1/T2/T6/T7.
Cubra obrigatoriamente: acoplamento fraco com SQS/SNS/EventBridge, síncrono vs assíncrono,
idempotência, retry com backoff e jitter, DLQ, API Gateway (integração proxy, 502/504,
request validation, mapping templates, caching, throttling), SDK (credential chain,
paginação, batch com falha parcial), Kinesis (shard, hot partition, enhanced fan-out) vs Firehose,
serialização, filter policies do SNS, padrões de evento do EventBridge, S3 Event Notifications.
```

#### 3.1.2 Task 1.1 — IA (skills 1.1.9 e 1.1.10, NOVO no C03)
```text
Aplique o PROMPT MESTRE. Domínio 1, Task 1.1, skills 1.1.9 e 1.1.10.
Gere 8 questões nível intermediário focadas em: desenvolvimento assistido por IA
(spec-driven, revisão, scanning), Amazon Bedrock (InvokeModel vs Converse/ConverseStream,
streaming, permissões IAM, tratamento de ThrottlingException), Bedrock AgentCore (conceito de
runtime/gateway/identidade/memória), Kiro. NÃO cobrar seleção de modelos, engenharia de prompt
nem desenho de RAG (fora de escopo).
```

#### 3.1.3 Task 1.2 — Lambda
```text
Aplique o PROMPT MESTRE. Domínio 1, Task 1.2, skills 1.2.1 a 1.2.4.
Gere 20 questões (10 intermediárias, 10 avançadas), mix T2/T3/T4/T7/T8.
Cubra: Lambda em VPC (NAT vs VPC endpoint), memória/CPU/timeout/ephemeral storage,
layers e extensions, versions/aliases/weighted routing, reserved vs provisioned concurrency,
SnapStart, invocação síncrona vs assíncrona (2 retries), Destinations vs DLQ,
event source mapping (SQS batch, visibility timeout >= 6x, ReportBatchItemFailures,
streams: bisect/retry/on-failure destination/IteratorAge), resource-based policy vs execution role,
Function URLs, cold start e inicialização fora do handler.
```

#### 3.1.4 Task 1.3 — Data stores
```text
Aplique o PROMPT MESTRE. Domínio 1, Task 1.3, skills 1.3.1 a 1.3.4.
Gere 20 questões, mix T1/T2/T4/T6/T8 incluindo CÁLCULOS de RCU/WCU (consistência eventual,
forte e transacional, itens de 3KB, 6KB, 9KB etc.).
Cubra: chave de partição de alta cardinalidade e hot partition, LSI vs GSI, Query vs Scan,
Filter/Projection/Condition expressions, optimistic locking, TTL, Streams, transações,
on-demand vs provisioned, DAX, ElastiCache (lazy loading, write-through, TTL), S3 lifecycle e
classes de armazenamento, escolha de data store por padrão de acesso.
```

### 3.2 Domínio 2 — Security (26%)

#### 3.2.1 Task 2.1 — Autenticação e autorização
```text
Aplique o PROMPT MESTRE. Domínio 2, Task 2.1, skills 2.1.1 a 2.1.7.
Gere 15 questões, mix T1/T4/T6/T7/T9.
Cubra: Cognito User Pool vs Identity Pool, JWT, authorizers do API Gateway (IAM, Cognito, Lambda),
STS AssumeRole/AssumeRoleWithWebIdentity/SAML, ExternalId, cross-account, trust policy vs
permissions policy, avaliação de políticas (deny explícito, SCP, permissions boundary),
managed vs customer-managed vs inline, MFA em condições, presigned URLs do S3 e signed URLs/cookies
do CloudFront, SigV4 e erros de credencial (ExpiredToken, SignatureDoesNotMatch), iam:PassRole.
Inclua leitura de políticas JSON (T4).
```

#### 3.2.2 Task 2.2 — Criptografia e dados sensíveis
```text
Aplique o PROMPT MESTRE. Domínio 2, Task 2.2, skills 2.2.1 a 2.2.7.
Gere 15 questões, mix T1/T2/T6/T9.
Cubra: SSE-S3/SSE-KMS/SSE-C, client-side vs server-side, KMS (envelope encryption,
GenerateDataKey, limite de 4KB, AWS managed vs customer managed, key policy, grants,
rotação, encryption context, uso cross-account), ACM (renovação, us-east-1 para CloudFront) e
Private CA, aws:SecureTransport, Secrets Manager vs Parameter Store (rotação, custo, SecureString),
cache de segredos em Lambda, variáveis de ambiente criptografadas, mascaramento de PII/PHI em logs.
```

#### 3.2.3 Task 2.3 — Segurança com IA (NOVO no C03)
```text
Aplique o PROMPT MESTRE. Domínio 2, Task 2.3, skills 2.3.1 a 2.3.5.
Gere 12 questões nível intermediário/avançado, mix T1/T2/T7/T9.
Cubra: permissões IAM para Bedrock com restrição por modelo, VPC interface endpoint (PrivateLink),
dados não usados para treinar modelos, logs de invocação com KMS, Bedrock Guardrails
(content filters, prompt attack, denied topics, word filters, PII, contextual grounding, ApplyGuardrail),
prompt injection, autorização por ferramenta em agentes, isolamento de sessão,
human-in-the-loop, mascaramento de PII em logs.
```

### 3.3 Domínio 3 — Testing and Deployment (22%)

#### 3.3.1 Tasks 3.1 e 3.2 — Artefatos e testes
```text
Aplique o PROMPT MESTRE. Domínio 3, Tasks 3.1 e 3.2, skills 3.1.1 a 3.2.5.
Gere 15 questões, mix T1/T2/T4/T5.
Cubra: layers e dependências, Dockerfile/multi-stage, ECR (tags, scanning, lifecycle),
AppConfig (feature flags, estratégias, rollback por alarme) vs Parameter Store vs Secrets Manager,
stage variables do API Gateway e deploy obrigatório para publicar mudanças, canary release,
SAM CLI (build/local invoke/start-api/generate-event/sync/deploy), eventos de teste,
integração MOCK, aliases/Amplify branches/Copilot environments, testes assistidos por IA.
```

#### 3.3.2 Task 3.3 — Deploy CI/CD
```text
Aplique o PROMPT MESTRE. Domínio 3, Task 3.3, skills 3.3.1 a 3.3.9.
Gere 20 questões (10 intermediárias, 10 avançadas), mix T2/T3/T4/T5/T6/T7.
Cubra: buildspec.yml (fases, env, artifacts, cache), appspec.yml (EC2 hooks em ordem,
Lambda e ECS), CodeDeploy (in-place vs blue/green, Canary/Linear/AllAtOnce, rollback por alarme),
CodePipeline (stages, actions, manual approval), CloudFormation (seções, intrínsecas, change sets,
rollback, DeletionPolicy, stack sets, estados de falha), SAM (Transform, AutoPublishAlias,
DeploymentPreference, hooks), CDK (synth/deploy/bootstrap), ECS (task role vs execution role,
rolling update, Fargate vs EC2), EKS (manifests, rolling), Elastic Beanstalk (políticas de deploy),
estratégias de deploy e rollback.
```

### 3.4 Domínio 4 — Troubleshooting and Optimization (22%)

#### 3.4.1 Tasks 4.1 e 4.2 — Diagnóstico e observabilidade
```text
Aplique o PROMPT MESTRE. Domínio 4, Tasks 4.1 e 4.2, skills 4.1.1 a 4.2.5.
Gere 20 questões, FORTE ênfase em T3 (diagnóstico por log/erro/consulta) e T4.
Inclua trechos de logs reais simulados (Lambda REPORT, mensagens de AccessDenied, stack events do
CloudFormation, X-Ray trace summary, CloudWatch Logs Insights queries a completar).
Cubra: códigos HTTP (400/401/403/429/502/504), exceptions de SDK, CloudWatch Logs Insights,
metric filters e subscription filters, EMF vs PutMetricData, alarms (estados, composite),
X-Ray (segments, subsegments, annotations vs metadata, sampling, daemon, service map),
CloudTrail vs CloudWatch vs X-Ray, logging estruturado, health checks, liveness vs readiness.
```

#### 3.4.2 Task 4.3 — Otimização
```text
Aplique o PROMPT MESTRE. Domínio 4, Task 4.3, skills 4.3.1 a 4.3.6.
Gere 15 questões, mix T2/T3/T8.
Cubra: concorrência Lambda (fórmula invocações/s x duração), provisioned vs reserved,
Lambda Power Tuning, Graviton, pool de conexões e RDS Proxy, SQS (long polling, batching,
visibility timeout, delay), SNS fan-out + filter policies, DAX vs ElastiCache vs CloudFront,
cache key e TTL no CloudFront, Auto Scaling policies, detecção de gargalos com CloudWatch/X-Ray.
```

---

## 4. PROMPTS DE ESTUDO ESPECIAIS

### 4.1 Simulado completo (65 questões, proporção oficial)
```text
Monte um simulado do DVA-C03 com 65 questões ORIGINAIS na proporção oficial dos domínios
(30% / 26% / 22% / 22%): aproximadamente 20 de D1, 17 de D2, 14 de D3, 14 de D4.
Inclua ~15% de múltipla resposta. Distribua por tasks e skills do glossário (sem concentrar).
Entregue PRIMEIRO só as questões e opções (sem gabarito). Quando eu enviar
"GABARITO", entregue respostas com explicações e uma análise de desempenho por domínio/skill.
```

### 4.2 Subtópico em profundidade (ex.: DynamoDB)
```text
Quero dominar {{SUBTOPICO}} para o DVA-C03.
1) Liste os 10 pontos que a prova mais cobra, em ordem de frequência.
2) Para cada ponto, gere 2 questões (uma básica e uma avançada) com gabarito comentado.
3) Termine com 5 pegadinhas e 5 "se a pergunta diz X, pense em Y".
Use o glossário como fonte de verdade e cite a documentação oficial.
```

### 4.3 Comparativos (confrontos clássicos)
```text
Para o par {{A}} vs {{B}} (ex.: Secrets Manager vs Parameter Store), gere:
- tabela de diferenças decisivas; 
- 6 questões T6 onde ambos parecem corretos, mas apenas um atende ao qualificador;
- explicação do porquê o outro é o distrator.
```

### 4.4 Diagnóstico de logs (domínio 4)
```text
Gere 8 questões T3. Cada uma com um log/erro realista (CloudWatch, CloudFormation events,
CodeBuild, CodeDeploy, API Gateway execution logs, X-Ray) e pergunta "qual a causa raiz / qual a correção".
Em cada gabarito, aponte a linha exata do log que denuncia a causa.
```

### 4.5 Leitura de artefatos (YAML/JSON)
```text
Gere 8 questões T4 com trechos de: buildspec.yml, appspec.yml, template SAM, template
CloudFormation, task definition do ECS, política IAM, key policy do KMS, política de bucket.
Cada trecho tem 1 erro sutil ou um comportamento a prever. A pergunta pede corrigir ou explicar.
```

### 4.6 Revisão dos meus erros (loop de estudo)
```text
Vou colar as questões que errei. Para cada uma:
1) diga o conceito que me faltou (skill ID); 
2) explique de forma curta com analogia só se o conceito for muito abstrato;
3) gere 2 questões novas "gêmeas" testando o mesmo conceito com cenário diferente;
4) sugira o link da doc oficial para ler.
No fim, ranqueie meus pontos fracos por domínio.
```

### 4.7 Flashcards (Anki/Obsidian)
```text
Converta o trecho do glossário abaixo em flashcards (pergunta/resposta curtas) no formato
"Q:: ...  A:: ...", priorizando limites numéricos, diferenças decisivas e palavras-gatilho.
[cole o trecho]
```

### 4.8 Novidades do C03 (IA) — revisão relâmpago
```text
Liste tudo que é NOVO no DVA-C03 em relação ao DVA-C02 (Task 2.3, IA no dev/teste/CI-CD/troubleshooting/
otimização, presigned URLs, containers/ECR/ECS/EKS, liveness/readiness). Para cada item,
gere 2 questões e um resumo de 3 linhas, mantendo apenas o que o Exam Guide cobra.
```

---

## 5. EXEMPLOS DE QUESTÕES (modelo do formato esperado — originais)

### Exemplo 1 — Lambda + SQS (T2, intermediário) · Skill 1.2.3
**Questão:** A developer configured an AWS Lambda function (timeout: 60 seconds) as an event source for an Amazon SQS standard queue (visibility timeout: 30 seconds). The function sometimes takes 50 seconds, and the team notices that some messages are processed more than once. Which change will resolve the issue with the LEAST operational overhead?

- A. Convert the queue to a FIFO queue.
- B. Increase the queue visibility timeout to at least six times the function timeout.
- C. Decrease the function timeout to 25 seconds.
- D. Configure a dead-letter queue on the Lambda function.

**Gabarito:** **B**
- **Por quê:** enquanto a Lambda processa, as mensagens ficam invisíveis; se o *visibility timeout* expira antes do término, a mensagem reaparece e é entregue de novo. A recomendação é ≥ 6× o timeout da função.
- **A:** FIFO não resolve visibilidade; além disso exige migração. **C:** quebraria a função de 50 s. **D:** DLQ de SQS é configurada na **fila**, e não corrige duplicidade.
- **Gatilho:** "processed more than once" + SQS + Lambda. **Pegadinha:** confundir DLQ da função com DLQ da fila.

### Exemplo 2 — DynamoDB cálculo (T2, intermediário) · Skill 1.3.4
**Questão:** An application performs 80 strongly consistent reads per second of items that are 6 KB each from a DynamoDB table in provisioned mode. How many read capacity units (RCUs) must be provisioned?

- A. 80  B. 120  C. 160  D. 240

**Gabarito:** **C (160)** — 6 KB arredonda para 2 blocos de 4 KB → 2 RCU × 80 = 160. (Eventually consistent seria 80; transacional seria 320.)
- **Pegadinha:** esquecer de arredondar para cima ou de considerar o tipo de consistência.

### Exemplo 3 — Segurança de upload (T1, intermediário) · Skills 2.1.4/2.1.1
**Questão:** A mobile app must let authenticated users upload photos directly to Amazon S3 without routing files through backend servers and without embedding long-term credentials. Which solution is MOST secure?

- A. Embed an IAM user access key in the app with `s3:PutObject` permission.
- B. Have the backend generate an S3 presigned PUT URL with a short expiration after validating the user.
- C. Make the bucket public-write and restrict by file extension.
- D. Store the access key in the app's encrypted SharedPreferences.

**Gabarito:** **B** (também seria válida a variante com Cognito Identity Pool + política por prefixo). A, C, D expõem credenciais ou o bucket.

### Exemplo 4 — Múltipla resposta (T7, avançado) · Skill 3.3.4
**Questão:** A team deploys a Lambda function with AWS CodeDeploy and wants to shift 10% of traffic first, validate, and automatically roll back if errors increase. Which TWO actions should the developer take? (Select TWO.)

- A. Use the `Canary10Percent5Minutes` deployment configuration.
- B. Use the `AllAtOnce` deployment configuration.
- C. Configure a CloudWatch alarm on function errors and associate it with the deployment group to enable automatic rollback.
- D. Use an in-place deployment type.
- E. Replace the alias with `$LATEST`.

**Gabarito:** **A e C.** In-place não existe para Lambda; AllAtOnce não faz validação gradual; `$LATEST` é mutável e quebra o controle de versão.

### Exemplo 5 — Diagnóstico (T3, intermediário) · Skill 4.1.1
**Questão:** An API Gateway REST API uses Lambda proxy integration. Clients receive `502 Bad Gateway`; the Lambda logs show a successful run that returns `"hello"` as a plain string. What is the cause?

- A. API Gateway throttling was exceeded.
- B. The function did not return a response in the proxy format (`statusCode`, `headers`, `body`).
- C. The integration timeout of 29 seconds was reached.
- D. The stage was not deployed.

**Gabarito:** **B.** Timeout seria 504; throttling 429; stage não deployado daria erro de recurso/403 (missing authentication token).

### Exemplo 6 — IA (T9, intermediário) · Skill 2.3.2/2.3.3
**Questão:** A company calls Amazon Bedrock from an application running in private subnets. The security team requires that traffic not traverse the public internet and that responses be screened for PII. Which combination will meet these requirements? (Select TWO.)

- A. Create an interface VPC endpoint for Bedrock Runtime.
- B. Deploy a NAT gateway and restrict outbound traffic to Bedrock IP ranges.
- C. Apply a Bedrock Guardrail with sensitive information filters.
- D. Enable AWS CloudTrail data events on the model.
- E. Fine-tune the model with a PII-free dataset.

**Gabarito:** **A e C.**

### Exemplo 7 — Observabilidade (T6, intermediário) · Skill 4.2.4
**Questão:** A developer needs to find, in AWS X-Ray, all traces that belong to a specific customer ID. What should the developer add to the code?

- A. Segment metadata with the customer ID.
- B. A trace annotation with the customer ID.
- C. A CloudWatch custom metric dimension with the customer ID.
- D. A sampling rule on the customer ID header.

**Gabarito:** **B** — annotations são indexadas e filtráveis; metadata não.

---

## 6. Rubrica para validar as questões geradas
- [ ] A skill (ID) existe no glossário e no guia oficial?
- [ ] O qualificador decide a resposta (existe uma segunda opção "funcional" porém pior)?
- [ ] Números/limites conferem com a documentação atual?
- [ ] O serviço está no escopo do DVA-C03 (não está na lista fora de escopo)?
- [ ] Gabarito e explicação não contradizem a doc? Cada distrator tem motivo claro?
- [ ] Cenário é realista (não "mágico")?

## 7. Cronograma sugerido de geração
1. D1 Lambda → D1 DynamoDB → D1 mensageria/API Gateway.
2. D2 IAM/Cognito → KMS/segredos → IA.
3. D3 CI/CD/IaC → artefatos/testes.
4. D4 logs/X-Ray → otimização.
5. Simulados completos de 65 questões; revisão de erros (prompt 4.6).
