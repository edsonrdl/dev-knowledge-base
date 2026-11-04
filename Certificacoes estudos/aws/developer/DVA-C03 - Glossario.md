---
tags: [aws, certificacao, developer-associate, dva-c03, glossario]
exame: DVA-C03
fonte-oficial: https://docs.aws.amazon.com/aws-certification/latest/developer-associate-03/developer-associate-03.html
verificado-em: 2026-11-04
status: completo-v1
---

# 📘 Glossário AWS Certified Developer – Associate (DVA-C03)

> Mapa de tudo que é cobrado, organizado **exatamente** pela hierarquia do Exam Guide oficial (Domínio → Task → Skill). Cada item traz: o conceito técnico, os números que a prova cobra, a pegadinha clássica e **como a pergunta costuma ser feita**.
> **Papel desta nota:** guia de referência do que cai e como cai. Não é a nota de conteúdo dos serviços (essas ficam nas camadas `8. DevOps.../AWS (AMAZON WEB SERVICE)/`) e não terá notas filhas.
> Use junto com [[DVA-C03 - Prompts de Questoes]] para gerar questões por tópico/subtópico. Fontes em [[Referencias e Fontes]]. Plano geral em [[00 - Plano de Estudos e Indice AWS Certificacoes]].

## 0. Visão Geral do Exame

### 0.1 Fatos oficiais
- **Código:** DVA-C03 (substitui o DVA-C02; registro abriu em **27/10/2026**; último dia do C02: **30/11/2026**; C03 em vigor a partir de **01/12/2026**).
- **Questões:** 65 no total = **50 pontuadas + 15 não pontuadas** (não identificadas). Duração: 130 min. Nota: escala 100–1000, **mínimo 720**. Modelo **compensatório** (não precisa passar por domínio).
- **Tipos:** múltipla escolha (1 correta + 3 distratores) e **múltipla resposta** (2+ corretas entre 5+ opções; precisa marcar **todas** as corretas). Sem penalidade por chute.
- **Perfil:** 1+ ano de experiência desenvolvendo/mantendo apps na AWS.

### 0.2 Pesos dos domínios
| Domínio | Peso C03 | Peso C02 (referência) |
|---|---|---|
| 1. Development with AWS Services | **30%** | 32% |
| 2. Security | **26%** | 26% |
| 3. Testing and Deployment | **22%** | 24% (Deployment) |
| 4. Troubleshooting and Optimization | **22%** | 18% |

### 0.3 O que mudou do C02 para o C03 (estude isto com prioridade se vinha estudando material antigo)
- **Novo Task 2.3:** riscos de segurança ao usar/integrar **serviços de IA** (acesso, privacidade, guardrails, agentes, logs).
- **IA no desenvolvimento:** usar ferramentas de IA para gerar/revisar código, testes, CI/CD, troubleshooting e otimização; integrar serviços de IA gerenciados.
- **Novo:** presigned URLs (S3/CloudFront), build de **imagens de container** (ECR, Dockerfile, tags, lifecycle), deploy em **ECS/EKS/Fargate**, health checks (**liveness/readiness**).
- **Recategorizado:** teste unitário com SAM → Domínio 3; tuning de Lambda → Domínio 4; serialização → Task 1.1.
- **Consolidado:** DynamoDB virou uma única skill (1.3.4), mas continua pesado na prova.
- **Fora de escopo (importante):** escolher foundation models, engenharia de prompt, desenhar RAG, desenhar guardrails/governança de IA, desenhar ETL, desenhar rede, administrar IAM users/groups, desenhar pipelines CI/CD.

### 0.4 Serviços in-scope (lista oficial C03)
- **Analytics:** Athena, Data Firehose, Kinesis, OpenSearch Service.
- **Integração:** EventBridge, SNS, SQS, Step Functions.
- **Compute:** EC2, Elastic Beanstalk, Lambda.
- **Containers:** ECR, ECS, EKS.
- **Database:** Aurora, DynamoDB, ElastiCache, RDS.
- **Dev Tools:** Amplify, CloudShell, CodeArtifact, CodeBuild, CodeDeploy, CodePipeline, X-Ray.
- **ML/IA:** Amazon Bedrock, Bedrock AgentCore, Amazon Quick, Kiro.
- **Management:** AppConfig, CDK, CloudFormation, CloudTrail, CloudWatch (+ Logs), CLI, SAM, Systems Manager.
- **Rede/CDN:** API Gateway, CloudFront, ELB, PrivateLink, Route 53, VPC.
- **Segurança:** ACM, Cognito, IAM, KMS, Private CA, Secrets Manager, STS, WAF.
- **Storage:** EBS, EFS, S3, S3 Glacier.

### 0.5 Como as perguntas são feitas (padrão geral)
1. **Cenário curto (2–5 linhas)** com um papel ("A developer is building…") + restrição + pergunta.
2. A pergunta termina com um **qualificador** que decide a resposta: *LEAST operational overhead*, *MOST cost-effective*, *LEAST development effort*, *MOST secure*, *without changing application code*, *near real time*, *at-least-once / exactly-once*.
3. **Quatro opções plausíveis**: duas tecnicamente possíveis, mas uma delas viola o qualificador (mais código, mais custo, menos seguro).
4. Em **múltipla resposta**, o enunciado diz "Select TWO/THREE" e as opções são combinações de passos de uma solução.
5. Tipos recorrentes: **(a)** escolha de serviço, **(b)** configuração correta (parâmetro/valor), **(c)** leitura de erro/log/código e correção, **(d)** ordem/fluxo de eventos, **(e)** diferença entre duas features parecidas.
6. Palavras-gatilho: ver tabela em [[DVA-C03 - Glossario#9. Tabela de Palavras-Gatilho]].

---

## 1. DOMÍNIO 1 — Development with AWS Services (30%)

### 1.1 Task 1.1 — Desenvolver código para aplicações hospedadas na AWS

#### 1.1.1 Skill 1.1.1 — Acoplamento forte vs fraco e desacoplamento
- **Conceito:** acoplamento forte = produtor chama consumidor direto e espera (cai um, cai o outro). Acoplamento fraco = intermediário (fila, tópico, barramento, stream) absorve picos e falhas.
- **Serviços de desacoplamento:** SQS (fila, pull), SNS (pub/sub, push), EventBridge (barramento com regras de roteamento), Kinesis (stream ordenado, múltiplos consumidores), Step Functions (orquestração).
- **Stateless vs stateful:** aplicação *stateless* guarda estado fora do processo (DynamoDB, ElastiCache, S3) → escala horizontal e Lambda funcionam. Sessões em memória local quebram atrás de um ELB com várias instâncias (solução: sessão em ElastiCache/DynamoDB ou cookie/JWT).
- **Coreografia vs orquestração:** coreografia = cada serviço reage a eventos (EventBridge/SNS); orquestração = um coordenador central define o fluxo (Step Functions). Orquestração dá visibilidade e retry centralizado; coreografia dá menos acoplamento.
- **Como cai:** "Um serviço de pedidos chama sincronamente o de estoque e falha em picos. Qual mudança desacopla com MENOR esforço?" → SQS entre eles.
- **Pegadinha:** SNS **não** guarda mensagem para consumidor offline (push); SQS guarda. Para "fan-out + durabilidade" → **SNS → várias SQS**.

#### 1.1.2 Skill 1.1.2 — Síncrono vs assíncrono
- **Síncrono:** chamador espera resposta (API Gateway → Lambda `RequestResponse`; ALB → Lambda). Erros voltam ao cliente; timeout do API Gateway (29 s por padrão) limita.
- **Assíncrono:** chamador recebe `202`/ACK e segue (Lambda `InvocationType=Event`, SQS, SNS, EventBridge, S3 Events). Exige tratamento de falha (retry, DLQ, destinations) e **idempotência**.
- **Idempotência:** executar a mesma operação N vezes tem o mesmo efeito de 1. Técnicas: chave de idempotência (`MessageDeduplicationId` em FIFO), `ConditionExpression attribute_not_exists(pk)` no DynamoDB, token de cliente (`ClientToken`), Powertools for AWS Lambda *idempotency*.
- **Entrega:** SQS Standard e SNS = **at-least-once** (podem duplicar) → consumidor idempotente. SQS FIFO = **exactly-once processing** dentro da janela de deduplicação (5 min).
- **Como cai:** "Processamento de pedidos pode ser duplicado. O que garante efeito único?" → idempotency key + conditional write.

#### 1.1.3 Skill 1.1.3 — Aplicações tolerantes a falha
- **Retry com backoff exponencial + jitter:** espera cresce (`base * 2^n`) com aleatoriedade para evitar *thundering herd*. SDKs já implementam; modos: `legacy`, `standard`, `adaptive` (o adaptive ajusta taxa do cliente conforme throttling).
- **Dead-letter queue (DLQ):** destino de mensagens que falharam N vezes. SQS: `maxReceiveCount` na *redrive policy* (DLQ do tipo da fila de origem: Standard↔Standard, FIFO↔FIFO). Lambda assíncrona: DLQ (SQS/SNS) ou **Destinations**.
- **Degradação graciosa:** servir cache/stale ou resposta reduzida quando dependência cai. **Circuit breaker:** parar de chamar dependência doente.
- **Timeouts:** sempre definir timeout menor que o do chamador (senão retry em cascata).
- **Como cai:** "Chamadas ao DynamoDB retornam `ProvisionedThroughputExceededException` em picos. O que fazer?" → backoff exponencial com jitter (SDK) + revisar chave/capacidade.

#### 1.1.4 Skill 1.1.4 — Criar/estender/manter APIs (API Gateway)
- **Tipos:** **REST API** (mais recursos: caching, usage plans/API keys, request validation, WAF, canary, private), **HTTP API** (mais barata/rápida, JWT authorizer nativo, menos recursos), **WebSocket API** (bidirecional).
- **Integrações (REST):** **Lambda proxy** (`AWS_PROXY`, a Lambda recebe o request inteiro e **deve** devolver `{statusCode, headers, body}`), Lambda custom (mapping templates VTL), **HTTP**/HTTP_PROXY, **AWS** (outro serviço, ex.: DynamoDB direto), **MOCK** (resposta sem backend — usado para testes e CORS preflight).
- **Transformações:** *mapping templates* (VTL) transformam request/response; *method request/response* e *integration request/response*; **request validation** (modelos JSON Schema, parâmetros obrigatórios) devolve 400 sem invocar backend; *gateway responses* customizam erros (4XX/5XX).
- **Status:** 400 validação, 401 não autenticado (authorizer), 403 negado/WAF/API key inválida, 404 recurso, 429 throttling, 502 resposta inválida do backend (ex.: Lambda proxy devolvendo formato errado), 503 indisponível, 504 timeout de integração.
- **Throttling:** limite padrão por conta/região (10.000 rps, burst 5.000); configurável por stage/método e por *usage plan*.
- **Caching:** só em REST; por stage; TTL padrão 300 s (0–3600); resposta em cache até 1 MiB; chave de cache pode incluir parâmetros/headers.
- **Limites (doc oficial, REST):** timeout de integração **50 ms–29 s** (aumentável apenas em APIs *Regional* e *private*, não em *edge-optimized*; aumentar pode exigir reduzir o throttle da conta); payload **10 MB**; 10 stages por API; 100 variáveis de stage por stage.
- **CORS:** habilitar no método OPTIONS (mock) e retornar `Access-Control-Allow-Origin` na resposta real (em proxy, **a Lambda precisa devolver os headers**).
- **Como cai:** "API devolve 502 após integrar Lambda proxy. Causa?" → função não retornou o objeto no formato esperado.

#### 1.1.5 Skill 1.1.5 — Interagir com serviços via APIs e SDKs
- **Cadeia de credenciais do SDK/CLI (ordem típica):** variáveis de ambiente → arquivo de credenciais/config (perfil) → web identity/SSO → credenciais de container (ECS task role) → **instance profile (EC2)**. Em Lambda, usa a **execution role** (variáveis de ambiente temporárias).
- **Nunca** colocar access key no código/AMI/repo. Em compute AWS, usar **roles**.
- **Paginação:** operações `List*`/`Scan`/`Query` retornam `NextToken`/`LastEvaluatedKey`; usar paginators. `--page-size` e `--max-items` no CLI (client-side) vs `--starting-token`.
- **Operações em lote:** `BatchWriteItem` (até 25 itens/16 MB), `BatchGetItem` (100 itens/16 MB), `SendMessageBatch`/`DeleteMessageBatch` (10), `PutRecords` (500) — podem ter **falha parcial** (`UnprocessedItems`, `FailedRecordCount`) → reprocessar.
- **Filtros no servidor:** `--query` (JMESPath, client-side) vs `--filter-expression`/`--key-condition-expression` (server-side). Filtrar no servidor reduz tráfego.
- **Reutilizar clientes** fora do handler (Lambda) para aproveitar conexões.
- **Como cai:** "App em EC2 precisa acessar S3 sem armazenar credenciais" → IAM role + instance profile.

#### 1.1.6 Skill 1.1.6 — Dados em streaming
- **Kinesis Data Streams (KDS):** shards; cada shard = **1 MB/s ou 1.000 registros/s de escrita** e **2 MB/s de leitura**. Ordem garantida **por shard** (via *partition key*). Retenção 24 h (até 365 dias). Registro de até **10 MiB** (antes do Base64). Leitura por shard: **2 MB/s ou 2.000 registros/s**; `GetRecords` = 5 chamadas/s por shard (até 10 MB e 10.000 registros por chamada). Consumidores: KCL, Lambda (event source mapping), *enhanced fan-out* (2 MB/s dedicado por consumidor, push via HTTP/2; até **20** consumidores registrados por stream, 50 no modo On-demand Advantage). Modos: **provisionado** (você define shards) e **on-demand** (escala sozinho; padrão inicial 4 MB/s escrita e 8 MB/s leitura). `PutRecords`: até 500 registros por requisição.
- **Hot shard:** partition key de baixa cardinalidade → `ProvisionedThroughputExceededException`; solução: chave de maior cardinalidade / dividir shard (reshard) / modo on-demand.
- **Data Firehose:** entrega *near real time* (buffer por tamanho/tempo) para S3, Redshift, OpenSearch, Splunk, HTTP; transformação com Lambda; sem gerenciar shards; **não** é para múltiplos consumidores/replay.
- **KDS vs Firehose vs SQS:** replay + ordem + múltiplos consumidores → KDS; apenas entregar ao destino → Firehose; fila de tarefas sem ordem estrita → SQS.
- **Lambda + stream:** processa lotes por shard; erro **bloqueia o shard** até expirar/sucesso → usar `BisectBatchOnFunctionError`, `MaximumRetryAttempts`, `MaximumRecordAgeInSeconds` e **on-failure destination**.
- **Como cai:** "Entregar logs a S3 sem administrar infra, com atraso de ~1 min" → Firehose.

#### 1.1.7 Skill 1.1.7 — Serialização e desserialização
- **Conceito:** converter objetos em bytes/strings (JSON, Avro, Protobuf, Parquet) para persistir/transmitir e reconstruir ao ler.
- **DynamoDB:** formato com tipos (`{"S":"abc"}`, `{"N":"1"}`); atributos numéricos são strings no fio; SDK high-level (DocumentClient/Enhanced Client/Resource) faz marshalling automático.
- **S3 + Athena:** formato colunar (**Parquet/ORC**) e compressão reduzem custo de varredura; partição por prefixo (ex.: `year=/month=`).
- **Kinesis/SQS:** corpo é texto/bytes; Base64 em Kinesis no evento Lambda precisa ser decodificado; SQS limite de **1 MiB** por mensagem (era 256 KB até 2025; acima disso, Extended Client com S3, até 2 GB).
- **Como cai:** "Lambda lê Kinesis e `data` aparece ilegível" → decodificar Base64 e parsear JSON.

#### 1.1.8 Skill 1.1.8 — Padrões orientados a eventos
- **EventBridge:** barramento (default, custom, partner); **regras** com *event pattern* (filtro por campos) ou **schedule** (cron/rate); até 5 targets por regra; *input transformer*; **archive/replay**; **Schema Registry**; **Pipes** (fonte → filtro → enriquecimento → destino); **Scheduler** (agendamentos em larga escala, one-time).
- **S3 Event Notifications:** eventos `ObjectCreated:*`, `ObjectRemoved:*` para Lambda, SQS, SNS ou EventBridge. Garantia *at-least-once*; para um mesmo prefixo, evitar notificações sobrepostas.
- **SNS:** tópico Standard/FIFO; protocolos (SQS, Lambda, HTTP/S, e-mail, SMS, mobile push); **filter policy** (atributos ou corpo) decide quem recebe; **raw message delivery**.
- **SQS:** Standard (ilimitado, at-least-once, ordem best-effort) vs FIFO (ordem por `MessageGroupId`, 300 msg/s ou 3.000 com batch; modo *high throughput* maior; nome termina em `.fifo`).
- **Como cai:** "Rotear eventos de SaaS parceiro para Lambdas diferentes conforme campo do evento" → EventBridge com regras por padrão.

#### 1.1.9 Skill 1.1.9 — Ferramentas de desenvolvimento assistido por IA (NOVO)
- **Conceito:** usar IA para gerar, revisar e otimizar código: **geração orientada a especificação (spec-driven)**, revisão automatizada, completar código, sugestões de refatoração, **varredura de segurança**.
- **Serviços/ferramentas em escopo (lista C03):** **Kiro**, **Amazon Bedrock**, **Bedrock AgentCore**, **Amazon Quick**. (CodeGuru estava no C02 e **não** aparece na lista de escopo do C03.)
- **Kiro** *(doc oficial kiro.dev/docs conferida; nomes de arquivos vêm de artigos de terceiros)*: ambiente de desenvolvimento com IA do protótipo à produção; o mesmo *agent harness* alimenta **IDE, CLI, Web e Mobile**, e a configuração compartilhada fica em `.kiro/` no repositório.
  - **Specs:** planejam uma funcionalidade em requisitos → design → tarefas (tipicamente `requirements.md`, `design.md`, `tasks.md`; requisitos em notação EARS). Existem também **Bugfix Specs** (causa raiz e prevenção de regressão).
  - **Steering:** aplica padrões e contexto do projeto automaticamente.
  - **Hooks:** automações disparadas quando o agente altera arquivos, usa ferramentas ou conclui tarefas (ex.: atualizar testes, rodar scan de segurança).
  - **Agentic chat** (construir sem plano prévio), **MCP** (conectar ferramentas/APIs externas) e **CLI** (modo headless, sessões, integração com CI).
- **Amazon Quick** *(doc oficial conferida; antes "Quick Suite", evolução do QuickSight)*: serviço de IA para automatizar tarefas, analisar dados, criar apps web e pesquisar, via chat em linguagem natural com agentes. Componentes: **Quick Sight** (BI/dashboards, os APIs do QuickSight continuam), **Quick Flows** (workflows com IA), **Quick Automate** (automação de processos com agentes), **Quick Index** (documentos e dados da empresa para fundamentar respostas), **Quick Research** (relatórios com citações) e **Apps in Quick**. Conecta-se a sistemas via MCP e OpenAPI. Para a prova, trate-o como ferramenta de produtividade/analytics com IA, não de código.
- **Boas práticas cobradas:** revisar código gerado por IA, rodar testes/scans antes do merge, não enviar segredos/PII em prompts, usar spec/requisitos claros.
- **Como cai:** "Qual abordagem gera código a partir de requisitos formalizados e mantém rastreabilidade?" → desenvolvimento spec-driven.
- ⚠️ Domínio novo: priorizar leitura da página oficial de cada ferramenta (links em [[Referencias e Fontes]]).

#### 1.1.10 Skill 1.1.10 — Integrar serviços gerenciados de IA
- **Amazon Bedrock:** API unificada para foundation models. `InvokeModel` (payload específico do modelo) vs **`Converse`/`ConverseStream`** (API padronizada multi-modelo, histórico de mensagens, tool use). Streaming para baixa latência percebida.
- **Recursos:** Knowledge Bases (RAG gerenciado), Agents, Guardrails, Prompt Management. *(Escolher modelo e desenhar RAG está fora de escopo; **chamar** corretamente está dentro.)*
- **Bedrock AgentCore (doc oficial, módulos que podem ser usados juntos ou isolados, com qualquer framework/modelo):**
  - **Runtime:** execução serverless de agentes e ferramentas, cold start rápido, **isolamento real de sessão**, identidade embutida, suporte a MCP e A2A.
  - **Harness:** loop de agente gerenciado, definido por uma chamada de API (modelo + prompt + ferramentas); cada sessão em **microVM isolada**.
  - **Memory:** curto prazo (conversa) e longo prazo (entre sessões).
  - **Gateway:** converte APIs, Lambdas e serviços em ferramentas **MCP** para agentes.
  - **Identity:** identidade/autenticação de agentes, integra IdPs existentes (Cognito, Okta, Entra ID, Auth0).
  - **Code Interpreter** (sandbox de código) e **Browser** (navegador em nuvem).
  - **Observability** (OpenTelemetry/CloudWatch), **Evaluations** (qualidade do agente), **Optimization** (recomendações + testes A/B), **Policy** (regras determinísticas, compatíveis com Cedar, que interceptam cada chamada de ferramenta no Gateway), **Registry** (catálogo governado de agentes/ferramentas) e **Payments** (microtransações).
- **Padrão de integração:** SDK → `bedrock-runtime`; permissões `bedrock:InvokeModel`; tratar `ThrottlingException` com backoff; timeouts maiores para respostas longas; Lambda com streaming.
- **Como cai:** "Aplicação precisa trocar de modelo sem reescrever o formato do request" → `Converse` API.

### 1.2 Task 1.2 — Desenvolver código para AWS Lambda

#### 1.2.1 Skill 1.2.1 — Lambda acessando recursos privados em VPC
- Configurar **subnets privadas + security group**; Lambda cria ENIs (Hyperplane). Para internet/APIs públicas a partir da VPC → **NAT Gateway** (Lambda em subnet pública **não** ganha IP público). Para serviços AWS sem NAT → **VPC endpoints** (gateway: S3/DynamoDB; interface/PrivateLink: demais).
- Role precisa de `AWSLambdaVPCAccessExecutionRole` (ENI).
- **Como cai:** "Lambda em VPC perdeu acesso à internet" → falta NAT (ou endpoint). "Acessar RDS privado" → mesma VPC + SG liberando porta; considerar **RDS Proxy** para pool de conexões.

#### 1.2.2 Skill 1.2.2 — Configuração de funções
- **Memória:** 128 MB–10.240 MB; **CPU proporcional à memória** (~1 vCPU a 1.769 MB). Mais memória pode **reduzir custo** (termina mais rápido).
- **Timeout:** padrão 3 s, máx **900 s (15 min)**. Para >15 min → Step Functions/Fargate/Batch. *(A doc atual cita até 90 min apenas para Lambda Managed Instances em invocação assíncrona/ESM — a prova trata o limite como 15 min.)*
- **Payload:** síncrono **6 MB** (request e response); resposta com *streaming* até 200 MB; **assíncrono 1 MB**.
- **Escalonamento:** cada função cria até **1.000 ambientes de execução a cada 10 s**; concorrência padrão da conta **1.000** por região (aumentável).
- **Armazenamento:** `/tmp` 512 MB–10 GB (efêmero por ambiente de execução); **EFS** para persistente/compartilhado.
- **Variáveis de ambiente:** até 4 KB total; criptografadas em repouso com KMS; *encryption helpers* para criptografia adicional (client-side) de valores sensíveis.
- **Pacote:** .zip (50 MB zipado direto / 250 MB descompactado incluindo layers) ou **imagem de container** (até 10 GB, de ECR da mesma região).
- **Layers:** até 5 por função; compartilham dependências/bibliotecas; extraídas em `/opt`. **Extensions:** processos auxiliares (monitoramento, segredos).
- **Handler, runtime, arquitetura (x86_64 vs arm64/Graviton — mais barato e rápido em geral).**
- **Concorrência:** *unreserved* (pool da conta, padrão 1.000/região), **reserved** (garante e também limita), **provisioned** (instâncias pré-aquecidas → elimina cold start; cobra extra; usar com alias/versão).
- **SnapStart:** snapshot do ambiente inicializado (Java, e outros runtimes suportados) → reduz cold start sem pagar provisioned.
- **Cold start vs warm:** init (download, runtime, código fora do handler) ocorre uma vez por ambiente; **inicializar SDK clients/conexões fora do handler**.
- **Como cai:** "Cold start alto em função Java" → SnapStart ou provisioned concurrency; "função lenta de CPU" → aumentar memória.

#### 1.2.3 Skill 1.2.3 — Ciclo de vida de eventos e erros
- **Invocação:** síncrona (erro volta ao chamador, sem retry automático da Lambda), **assíncrona** (a Lambda enfileira internamente; **2 retries** automáticos; `MaximumRetryAttempts` 0–2; `MaximumEventAgeInSeconds` até 6 h), e **polling** (event source mapping).
- **Destinations (assíncrono):** *on success* e *on failure* → SQS, SNS, Lambda, EventBridge (inclui contexto da execução). Mais ricas que DLQ. DLQ clássico: só SQS/SNS e só falhas.
- **Event source mapping (ESM):** Lambda **faz polling** em SQS, Kinesis, DynamoDB Streams, MSK, etc. Permissões da *execution role* para ler a fonte.
  - **SQS:** `BatchSize` até 10 (Standard permite até 10.000 com *batch window*); **visibility timeout da fila ≥ 6× timeout da função**; retornar erro → mensagens voltam à fila; use **`ReportBatchItemFailures`** (resposta parcial) para não reprocessar o lote todo; DLQ configurada **na fila**, não na função.
  - **Streams (Kinesis/DynamoDB):** retry até sucesso ou expiração (bloqueia o shard) → configurar bisect, tentativas, idade máxima e destino de falha; `ParallelizationFactor` até 10 por shard.
  - **Filtros de evento** no ESM descartam registros antes de invocar (menos custo).
- **Idempotência:** como a entrega é at-least-once, o código deve tolerar duplicatas.
- **Como cai:** "Mensagens SQS são processadas em duplicidade e a Lambda expira" → visibility timeout menor que o timeout da função.

#### 1.2.4 Skill 1.2.4 — Integrar Lambda com serviços
- Gatilhos comuns: API Gateway, ALB, S3, SNS, EventBridge, SQS, Kinesis, DynamoDB Streams, Cognito triggers, CloudWatch Logs (subscription).
- **Function URLs:** endpoint HTTPS dedicado (auth `AWS_IAM` ou `NONE`).
- **Resource-based policy** da função autoriza **quem pode invocar** (ex.: S3, API Gateway); **execution role** autoriza **o que a função pode fazer**. Erro clássico: confundir os dois.
- **Versions e aliases:** versão = snapshot imutável (`$LATEST` é mutável); alias = ponteiro nomeado (`prod`) com **roteamento ponderado** entre duas versões (canary).
- **Como cai:** "S3 não consegue invocar a Lambda" → falta permissão na resource-based policy (`lambda:InvokeFunction` com principal `s3.amazonaws.com`).

### 1.3 Task 1.3 — Usar data stores no desenvolvimento

#### 1.3.1 Skill 1.3.1 — Ciclo de vida de dados
- **S3 Lifecycle:** regras de transição entre classes e expiração por prefixo/tag/idade; limpeza de *multipart uploads* incompletos; versões não atuais.
- **Classes S3:** Standard → Standard-IA (≥30 dias, mín. 128 KB) → One Zone-IA → Intelligent-Tiering (padrão de acesso desconhecido) → Glacier Instant Retrieval / Flexible Retrieval / **Deep Archive** (recuperação de horas). Transições têm ordem permitida (não volta de Glacier por lifecycle).
- **DynamoDB TTL:** atributo com epoch em segundos; exclusão **sem consumo de WCU**, assíncrona (até dias depois); itens expirados aparecem em Streams.
- **Retenção:** SQS 1 min–14 dias; Kinesis 24 h–365 dias; CloudWatch Logs retention configurável (padrão **nunca expira**); ECR lifecycle policies.
- **Como cai:** "Expirar sessões automaticamente sem custo de escrita" → TTL no DynamoDB.

#### 1.3.2 Skill 1.3.2 — Escolher data store por padrão de acesso
| Necessidade | Escolha |
|---|---|
| Chave-valor, milissegundos, escala massiva, serverless | **DynamoDB** |
| Joins/SQL, transações complexas, esquema relacional | **RDS / Aurora** |
| Objetos (arquivos, imagens, backups, data lake) | **S3** |
| Cache em memória, sessões, latência de microssegundos | **ElastiCache** (Redis/Valkey/Memcached) |
| Busca full-text/logs | **OpenSearch** |
| Arquivos compartilhados POSIX entre instâncias | **EFS** |
| Disco de uma instância EC2 | **EBS** |
- **Consistência:** DynamoDB leitura *eventually consistent* (padrão, metade do custo) vs *strongly consistent* (`ConsistentRead=true`; não em GSI nem Streams).

#### 1.3.3 Skill 1.3.3 — Cache conforme o data store
- **Estratégias:** **Lazy loading / cache-aside** (lê cache; miss → banco → popula; risco de dado velho, miss custa 3 idas), **write-through** (grava no cache e no banco; sem dado velho; cache cresce com dados nunca lidos), **TTL** (expira para limitar staleness). Combinar lazy + TTL é o mais comum.
- **ElastiCache Redis (Valkey):** estruturas ricas, persistência, replicação/Multi-AZ, pub/sub, *sorted sets*. **Memcached:** simples, multithread, sem persistência/replicação.
- **DAX:** cache **write-through, compatível com API do DynamoDB**, para leituras **eventually consistent**; sem mudar modelo de dados; não ajuda leitura *strongly consistent* nem cargas pesadas de escrita.
- **CloudFront:** cache de conteúdo no edge; **API Gateway cache** por stage.
- **Como cai:** "Acelerar leituras repetidas do DynamoDB mudando o mínimo de código" → DAX. "Sessões compartilhadas entre instâncias" → ElastiCache Redis.

#### 1.3.4 Skill 1.3.4 — Configurar DynamoDB (peso alto na prova)
- **Chaves:** *partition key* (hash) sozinha, ou partition + **sort key** (composta). **Alta cardinalidade** e acesso uniforme evitam *hot partition*.
- **Capacidade:** 
  - **RCU:** 1 leitura *strongly consistent* de até **4 KB**/s; *eventually* = 2 leituras/s; *transacional* = 1 leitura/2 RCU.
  - **WCU:** 1 escrita de até **1 KB**/s; transacional = 2 WCU. Arredonda para cima por item.
  - Exemplo: ler 10 itens de 6 KB strongly/s → ceil(6/4)=2 RCU × 10 = **20 RCU**; eventual = 10 RCU.
  - Modos: **Provisioned** (+ auto scaling) vs **On-demand** (picos imprevisíveis, paga por requisição).
- **Item:** máx **400 KB**.
- **Índices:**
  - **LSI:** mesma partition key, outra sort key; **só na criação da tabela**; máx 5; limite 10 GB por partição; aceita leitura strongly consistent; compartilha capacidade da tabela.
  - **GSI:** qualquer chaves; criado a qualquer momento; máx 20 (padrão); **só eventually consistent**; capacidade própria (throttling do GSI pode throttlar a tabela).
- **Query vs Scan:** `Query` usa a chave (eficiente, retorna itens de **uma** partition key); `Scan` lê a tabela inteira (caro; filtro é aplicado **depois** da leitura, cobra pelo lido). Preferir Query/índices; Scan paralelo e `Limit` para amenizar.
- **Expressões:** `KeyConditionExpression`, `FilterExpression`, `ProjectionExpression`, `ConditionExpression`, `UpdateExpression` (`SET`, `REMOVE`, `ADD`, atualização atômica de contador).
- **Concorrência:** *optimistic locking* com atributo de versão + `ConditionExpression`; `ConditionalCheckFailedException` quando falha.
- **Transações:** `TransactWriteItems`/`TransactGetItems` (até 100 itens), ACID.
- **Streams:** log ordenado de mudanças por 24 h → Lambda (CDC, replicação, agregações).
- **Global Tables:** multi-região ativo-ativo (last writer wins). **PITR** e backups on-demand.
- **Erros:** `ProvisionedThroughputExceededException` (backoff), `ThrottlingException`, `ValidationException`, `ConditionalCheckFailedException`, `TransactionCanceledException`.
- **Como cai:** "Query lenta e cara na tabela de pedidos por `customerId`" → criar GSI com `customerId`; "Tabela com hot partition" → melhorar cardinalidade (sufixo/shard na chave).

---

## 2. DOMÍNIO 2 — Security (26%)

### 2.1 Task 2.1 — Autenticação e autorização

#### 2.1.1 Skill 2.1.1 — Federação de identidade
- **Cognito User Pools:** diretório de usuários da **aplicação** (cadastro, login, MFA, social/SAML/OIDC) → emite **JWT** (ID, access, refresh). Autentica.
- **Cognito Identity Pools (federated identities):** troca token de um IdP (user pool, Google, SAML, OIDC) ou acesso anônimo por **credenciais AWS temporárias (STS)** → autoriza acesso a recursos AWS (S3, DynamoDB).
- **Regra de ouro:** *quer login e JWT para API?* → User Pool. *Quer que o usuário final acesse S3/DynamoDB direto?* → Identity Pool (geralmente com User Pool como IdP).
- **IAM Identity Center / SAML 2.0 / OIDC:** federação corporativa para console/CLI; `AssumeRoleWithSAML`, `AssumeRoleWithWebIdentity` (OIDC; preferir Cognito para mobile).
- **Como cai:** "App móvel deve subir fotos direto ao S3 com credenciais temporárias por usuário" → Cognito Identity Pool + política IAM com variável `${cognito-identity.amazonaws.com:sub}`.

#### 2.1.2 Skill 2.1.2 — Controle de acesso, tokens, MFA
- **Avaliação de políticas IAM:** **negação explícita sempre vence** → depois *allow* explícito → padrão negar. Tipos: identity-based, **resource-based**, **permissions boundary**, **SCP** (Organizations), session policy. Para acesso na mesma conta, *allow* em identity **ou** resource-based basta; entre contas, precisa dos dois lados.
- **Menor privilégio:** conceder somente ações/recursos necessários; usar `Condition` (`aws:SourceIp`, `aws:MultiFactorAuthPresent`, `aws:SecureTransport`, `aws:PrincipalOrgID`, `s3:prefix`).
- **Managed (AWS) vs Customer-managed vs Inline:** AWS managed = prontas, genéricas; customer managed = reutilizáveis e versionadas por você; inline = ligada a uma entidade.
- **Tokens bearer:** JWT (assinado; validar assinatura, `exp`, `aud`, `iss`), OAuth 2.0 scopes, STS temporário.
- **API Gateway authorizers:** **IAM (SigV4)**, **Cognito authorizer** (REST) / JWT authorizer (HTTP API), **Lambda authorizer** (token ou request; retorna política IAM; cache de resultado).
- **MFA:** exigir via condição de política; `GetSessionToken` com MFA para chamadas sensíveis.

#### 2.1.3 Skill 2.1.3 — Acesso programático
- Access keys (usuário IAM — evitar), **perfis nomeados**, **IAM Identity Center no CLI** (`aws sso login`), roles em compute, **variáveis de ambiente** (`AWS_ACCESS_KEY_ID`, `AWS_SESSION_TOKEN`).
- **Assinatura SigV4** para chamadas REST diretas; SDKs assinam automaticamente.

#### 2.1.4 Skill 2.1.4 — Presigned URLs (NOVO)
- **S3 presigned URL:** URL temporária assinada com as credenciais de quem gerou; concede **GET/PUT** de **um objeto** por tempo limitado. A permissão efetiva é a do **assinante** (se a role expira antes, a URL expira junto). Padrão para upload direto do navegador sem expor credenciais; também *presigned POST* com condições.
- **CloudFront:** **signed URLs** (um arquivo) e **signed cookies** (vários arquivos/HLS) com *trusted key groups*; restringir origem S3 com **OAC** (Origin Access Control).
- **Como cai:** "Permitir download de arquivo privado por 15 minutos para um cliente externo, sem criar usuário IAM" → presigned URL.

#### 2.1.5 Skill 2.1.5 — Chamadas autenticadas
- SigV4: assina método, caminho, headers e payload; falha por **relógio dessincronizado** (`SignatureDoesNotMatch`, `RequestTimeTooSkewed`), token expirado (`ExpiredToken`), região errada.

#### 2.1.6 Skill 2.1.6 — Permissões para principals e recursos
- Principals: usuários, roles, serviços (`lambda.amazonaws.com`), contas, identidades federadas.
- **Trust policy** (quem pode assumir a role) vs **permissions policy** (o que a role pode fazer).
- **Resource-based policies:** S3 bucket policy, SQS/SNS queue policy, Lambda policy, KMS key policy, ECR repository policy.
- **Como cai:** "Conta B precisa gravar na fila SQS da conta A" → queue policy na conta A permitindo o principal da B (+ permissão no lado da B).

#### 2.1.7 Skill 2.1.7 — Assumir uma role (STS)
- `AssumeRole` devolve credenciais temporárias (`AccessKeyId`, `SecretAccessKey`, `SessionToken`); duração 15 min–12 h (padrão 1 h). **ExternalId** protege contra *confused deputy* em acesso de terceiros. `AssumeRoleWithSAML` / `AssumeRoleWithWebIdentity`. `GetCallerIdentity` para ver "quem sou eu". `PassRole` exige permissão `iam:PassRole` para delegar uma role a um serviço.
- **Cross-account:** trust policy na conta destino + permissão `sts:AssumeRole` na origem.

### 2.2 Task 2.2 — Criptografia e dados sensíveis

#### 2.2.1 Skill 2.2.1 — Repouso e trânsito
- **Em trânsito:** TLS (ACM no ALB/CloudFront/API Gateway); impor com `aws:SecureTransport` em bucket policy; HTTPS-only em CloudFront.
- **Em repouso:** S3 (SSE-S3 padrão desde 2023, SSE-KMS, SSE-C, DSSE-KMS), EBS, RDS, DynamoDB (sempre criptografado; chave owned/AWS managed/CMK), SQS/SNS (SSE-KMS), Lambda env vars.

#### 2.2.2 Skill 2.2.2 — Certificados
- **ACM:** emite e **renova automaticamente** certificados públicos (DNS validation); só usa em serviços integrados (ELB, CloudFront, API Gateway) — **não exporta a chave privada** de certificados públicos. CloudFront exige certificado em **us-east-1**. **AWS Private CA:** CA privada para certificados internos (mTLS, dispositivos).

#### 2.2.3 Skill 2.2.3 — Client-side vs Server-side
- **Server-side:** o serviço criptografa ao gravar (SSE). Simples; o serviço vê o texto claro em memória.
- **Client-side:** a aplicação criptografa **antes** de enviar (AWS Encryption SDK / S3 Encryption Client). A AWS nunca vê o texto claro. Mais controle, mais complexidade.
- **Como cai:** "Dados devem chegar criptografados à AWS e a AWS não pode ver o conteúdo" → client-side.

#### 2.2.4 Skill 2.2.4 — Chaves (KMS) e criptografia de envelope
- **Tipos de chave:** AWS owned (invisível), **AWS managed** (`aws/s3`, rotação automática anual, você não controla a policy), **customer managed (CMK)** (você controla key policy, rotação, desabilitar/deletar).
- **Limite:** `Encrypt` direto aceita **até 4 KB**. Dados maiores → **envelope encryption**: `GenerateDataKey` devolve chave de dados em texto claro + versão criptografada; criptografa dados localmente, **descarta a chave em texto claro** e guarda a versão criptografada junto ao dado; `Decrypt` recupera a chave. (`GenerateDataKeyWithoutPlaintext` gera para uso futuro.)
- **Key policy** é a fonte primária de autorização (sem ela, IAM sozinho não basta); **grants** para delegar temporariamente. **Encryption context** (pares chave-valor autenticados, aparecem no CloudTrail).
- **Rotação (doc oficial):** 
  - **Automática:** opcional em CMK **simétrica com material gerado pelo KMS** (origem `AWS_KMS`). Padrão **365 dias**; dá para definir `RotationPeriodInDays` personalizado (restringível pela condição `kms:RotationPeriodInDays`). **AWS managed keys rotacionam sozinhas todo ano** (desde mai/2022; antes eram 3 anos) e você não controla.
  - **On-demand:** dispara rotação imediata (inclusive em chaves com material importado `EXTERNAL`), sem alterar o agendamento automático.
  - **Manual (nova chave + alias):** única opção para chaves **assimétricas**, **HMAC** e de **custom key store**.
  - Chaves antigas permanecem para decriptar; o **ID/ARN não muda**; a rotação **não re-criptografa** dados nem rotaciona data keys já geradas. Eventos `RotateKey` no CloudTrail/EventBridge.
- **Multi-region keys**, **alias**, `kms:ViaService`. Exclusão: janela de 7–30 dias.
- **Erros comuns:** `AccessDeniedException` (key policy/IAM), `KMSInvalidStateException` (chave desabilitada), `ThrottlingException` (cota → backoff, cache de data key).
- **Como cai:** "Criptografar arquivo de 1 GB com KMS" → envelope encryption (`GenerateDataKey`).

#### 2.2.5 Skill 2.2.5 — Certificados e chaves SSH para desenvolvimento
- Key pairs EC2 (`ec2 create-key-pair`; chave privada baixada **uma vez**), **EC2 Instance Connect** (chave temporária), Session Manager (sem SSH aberto). Certificados autoassinados só em dev.

#### 2.2.6 Skill 2.2.6 — Identificar, mascarar e limitar dados sensíveis (PII/PHI)
- **Amazon Macie** descobre PII em S3 (embora esteja fora da lista, é conceito comum). **CloudWatch Logs data protection policies** mascaram dados sensíveis em logs. **Bedrock Guardrails** redige PII em entradas/saídas de IA. Comprehend pode detectar PII.
- Práticas: tokenização, mascaramento, **não logar** dados sensíveis, mínimo necessário, S3 Object Lambda/Access Points para limitar visão.

#### 2.2.7 Skill 2.2.7 — Gerenciamento de segredos
| | **Secrets Manager** | **SSM Parameter Store** |
|---|---|---|
| Rotação automática | **Sim** (Lambda; RDS nativo) | Não nativa |
| Custo | Pago por segredo/mês + chamadas | Standard gratuito; Advanced pago |
| Criptografia | Sempre KMS | `SecureString` com KMS (opcional) |
| Replicação multi-região | Sim | Não nativa |
| Uso típico | Credenciais de banco, API keys com rotação | Configuração e segredos simples, hierarquia `/app/env/chave` |
- Acesso por role (`secretsmanager:GetSecretValue`, `ssm:GetParameter` + `kms:Decrypt`). **Nunca** segredo em código, env var em texto claro ou imagem de container.
- **Lambda:** buscar segredo na inicialização e **cachear** (Lambda extension para Parameter Store/Secrets Manager ou cache client) para reduzir latência/custo.
- **Como cai:** "Rotacionar senha do RDS automaticamente com mínimo esforço" → Secrets Manager.

### 2.3 Task 2.3 — Riscos de segurança com serviços de IA (NOVO)

#### 2.3.1 Skill 2.3.1 — Solicitar e gerenciar acesso a serviços de IA
- Acesso a modelos do Bedrock é controlado por **IAM** (`bedrock:InvokeModel`, `InvokeModelWithResponseStream`, `Converse`) com **restrição por ARN do modelo**; habilitar acesso aos modelos na conta/região; SCPs para limitar quais modelos/regiões.

#### 2.3.2 Skill 2.3.2 — Privacidade ao enviar dados à IA
- **VPC endpoints (PrivateLink)** para `bedrock-runtime` → tráfego não passa pela internet pública.
- Entradas/saídas **não são usadas para treinar** modelos base (garantia do Bedrock); logs de invocação são opcionais e vão para S3/CloudWatch sob seu controle (criptografar com KMS).
- **Como cai:** "Dados da aplicação não podem trafegar pela internet ao chamar o modelo" → interface VPC endpoint.

#### 2.3.3 Skill 2.3.3 — Filtrar entradas/saídas (Guardrails)
- **Bedrock Guardrails:** *content filters* (ódio, insultos, sexual, violência, má conduta), **prompt attack filter** (injeção/jailbreak), *denied topics*, *word filters*, **sensitive information filters** (PII: bloquear ou mascarar), *contextual grounding check* (alucinação). Aplicáveis também via API independente (`ApplyGuardrail`).
- **Prompt injection:** instruções maliciosas no input/dados recuperados; mitigar com guardrails, separar instruções de dados, mínimo privilégio nas ferramentas.

#### 2.3.4 Skill 2.3.4 — Proteger interações com agentes de IA
- **Autorização por ferramenta** (cada tool com permissões mínimas) → **AgentCore Policy** avalia regras determinísticas (compatíveis com Cedar) antes de cada chamada de ferramenta passando pelo **Gateway**. **Isolamento de sessão** (contexto de um usuário não vaza para outro) → sessões em **microVM** isolada no AgentCore Runtime/Harness. **Human-in-the-loop** para ações sensíveis (aprovação antes de apagar, pagar, enviar).
- Identidade do agente: **AgentCore Identity** (credenciais de entrada e saída, OAuth, integra IdPs existentes) e **Gateway** (expor APIs/Lambdas como ferramentas MCP com autenticação).
- **Como cai:** "Impedir que o agente execute `delete` sem aprovação" → política na ferramenta + aprovação humana; "Garantir que um usuário não veja a memória de outro" → isolamento de sessão.

#### 2.3.5 Skill 2.3.5 — Proteger conteúdo em logs de monitoramento
- Mascarar/redigir PII em logs de prompts e respostas; criptografar buckets/log groups com KMS; restringir quem lê; retenção mínima; CloudWatch Logs **data protection policies**.

---

## 3. DOMÍNIO 3 — Testing and Deployment (22%)

### 3.1 Task 3.1 — Preparar artefatos para deploy

#### 3.1.1 Skill 3.1.1 — Dependências de módulos
- Lambda: empacotar dependências no .zip ou em **layer**; manter pacote pequeno melhora cold start; variáveis de ambiente e arquivos de config por ambiente; `requirements.txt`/`package.json`/Maven/Gradle; compilar para a **arquitetura** correta (arm64/x86).

#### 3.1.2 Skill 3.1.2 — Imagens de container (NOVO)
- **Dockerfile:** imagem base enxuta, multi-stage build, camadas estáveis primeiro (cache), usuário não-root, sem segredos.
- **ECR:** registro privado/público; `aws ecr get-login-password | docker login`; `docker tag` + `docker push`; **tags** imutáveis (usar versão/commit SHA, evitar `latest` em produção); **image scanning** (básico/enhanced), **lifecycle policies** (expirar imagens antigas/sem tag), replicação, repository policy.
- **Lambda container:** usar imagens base da AWS ou implementar o Runtime Interface Client; até 10 GB.

#### 3.1.3 Skill 3.1.3 — Repositórios de código
- Git: branches (feature, main), tags/labels para releases, pull requests. Integração com CodePipeline (GitHub/GitLab/Bitbucket via CodeConnections, S3, ECR). **CodeArtifact:** repositório gerenciado de pacotes (npm, Maven, pip, NuGet) com *upstream* a repositórios públicos.

#### 3.1.4 Skill 3.1.4 — Configuração por ambiente
- **AppConfig** (parte do Systems Manager): configuração e **feature flags** com *deployment strategies* (linear, canary), validação (JSON Schema/Lambda) e **rollback automático** por alarme CloudWatch; Lambda extension para busca.
- **Parameter Store** (hierarquia por ambiente), **Secrets Manager** (segredos), **stage variables** no API Gateway (`${stageVariables.lambdaAlias}`), variáveis de ambiente Lambda por alias/stack.
- **Como cai:** "Alterar flag em produção sem novo deploy e com rollback se erros subirem" → AppConfig.

#### 3.1.5 Skill 3.1.5 — Recursos do API Gateway (stages, URLs)
- **Stage** = ambiente nomeado de um deployment (`dev`, `test`, `prod`); URL `https://{api-id}.execute-api.{region}.amazonaws.com/{stage}`. **Mudança na API só vale após novo *deployment* para o stage** (pegadinha clássica).
- **Stage variables**, **canary release** (% do tráfego para nova versão do deployment), **custom domain names** (ACM + base path mapping), tipos de endpoint (Edge-optimized, Regional, Private).

### 3.2 Task 3.2 — Implementar e automatizar testes

#### 3.2.1 Skill 3.2.1 — Desenvolver e validar testes
- **Pirâmide:** unitário (rápido, mocks) → integração → ponta a ponta. Para Lambda: separar lógica de negócio do handler; **mockar clientes AWS** (moto, `aws-sdk-client-mock`, Mockito); testes locais com **SAM CLI**.
- **SAM CLI:** `sam init`, `sam build`, `sam local invoke`, `sam local start-api`, `sam local generate-event`, `sam validate`, `sam sync` (hot reload na nuvem, dev), `sam deploy`, `sam logs`.
- **CDK:** testes de *assertion* em templates sintetizados (`Template.fromStack`) e *snapshot*. **CloudFormation:** `cfn-lint`, change sets.

#### 3.2.2 Skill 3.2.2 — APIs mock para dependências externas
- API Gateway **integração MOCK** devolve resposta fixa; útil para frontends antes do backend e para simular dependência externa.

#### 3.2.3 Skill 3.2.3 — Eventos de teste
- JSON de exemplo (console "Test", `sam local generate-event s3 put`, `aws lambda invoke --payload`). Lembrar `--cli-binary-format raw-in-base64-out` no CLI v2 para payload JSON.

#### 3.2.4 Skill 3.2.4 — Ambientes
- **Lambda aliases** (`dev`, `prod`) apontando para versões; **tags de imagem** ECR; **Amplify branches** (cada branch = ambiente com URL); **Copilot environments** (ECS/Fargate); **API Gateway stages**; stacks separadas por ambiente (parâmetros).

#### 3.2.5 Skill 3.2.5 — IA para testes (NOVO)
- Geração de testes unitários, análise de resultados, regressão automatizada, cobertura. Ferramentas: Kiro, Bedrock. Princípio: **humano revisa** os testes gerados.

### 3.3 Task 3.3 — Deploy com CI/CD

#### 3.3.1 Skill 3.3.1 — Empacotamento Lambda
- .zip (simples, dentro dos limites), **container image** (dependências grandes/ML, até 10 GB), **layers** (dependências compartilhadas, até 5).

#### 3.3.2 Skill 3.3.2 — Orquestração de containers (NOVO)
- **ECS:** *task definition* (imagem, CPU/memória, portas, env, logs `awslogs`, **task role** = permissões da aplicação; **task execution role** = puxar imagem do ECR e escrever logs). *Service* mantém N tasks, integra ALB, *rolling update* (`minimumHealthyPercent`/`maximumPercent`), deployment circuit breaker com rollback, **blue/green** via CodeDeploy.
- **Launch types:** **Fargate** (serverless, sem gerenciar instâncias) vs **EC2** (controle da instância, GPU, custo em escala).
- **EKS:** Kubernetes gerenciado; manifests (Deployment, Service), `kubectl apply`, *rolling updates*; permissões de pods via **IRSA / EKS Pod Identity**.
- **Elastic Beanstalk:** PaaS; políticas de deploy: *All at once*, *Rolling*, *Rolling with additional batch*, **Immutable**, *Traffic splitting* (canary) e **Blue/green** (troca de CNAME); `.ebextensions`; ambientes.

#### 3.3.3 Skill 3.3.3 — IaC (CloudFormation e SAM)
- **CloudFormation:** seções do template — `AWSTemplateFormatVersion`, `Parameters`, `Mappings`, `Conditions`, `Resources` (**única obrigatória**), `Outputs`, `Transform`. Funções intrínsecas: `!Ref`, `!GetAtt`, `!Sub`, `!Join`, `!ImportValue`, `!FindInMap`, `!If`.
- **Operações:** *stack*, **change set** (prévia), **stack set** (multi-conta/região), *nested stacks*, **drift detection**, `DeletionPolicy` (`Retain`, `Snapshot`), `UpdateReplacePolicy`, `DependsOn`, `CreationPolicy`/`cfn-signal`, `WaitCondition`. Falha em criação → **rollback automático**; falha de update → `UPDATE_ROLLBACK_COMPLETE`; `UPDATE_ROLLBACK_FAILED` → *continue update rollback*.
- **SAM:** extensão do CloudFormation com `Transform: AWS::Serverless-2016-10-31` e recursos `AWS::Serverless::Function`, `Api`, `HttpApi`, `SimpleTable`, `LayerVersion`, `StateMachine`. `sam deploy` empacota (S3) e cria change set. `AutoPublishAlias` + `DeploymentPreference` (Canary/Linear com CodeDeploy, **hooks** `PreTraffic`/`PostTraffic`, alarmes).
- **CDK:** IaC em linguagens de programação → `cdk synth` gera CloudFormation; `cdk bootstrap`, `cdk deploy`, `cdk diff`; *constructs* L1 (CFN puro), L2 (padrões), L3 (padrões completos).

#### 3.3.4 Skill 3.3.4 — CodeDeploy
- **Plataformas:** EC2/on-premises, **Lambda**, **ECS**. **In-place** (EC2/on-prem apenas) vs **Blue/Green**.
- **`appspec.yml`:** EC2 → `files` e hooks **ApplicationStop → BeforeInstall → AfterInstall → ApplicationStart → ValidateService**; Lambda → `BeforeAllowTraffic`/`AfterAllowTraffic`; ECS → hooks de teste de tráfego.
- **Configurações de tráfego (Lambda/ECS):** `AllAtOnce`, **Canary** (`Canary10Percent5Minutes`), **Linear** (`Linear10PercentEvery1Minute`). EC2: `AllAtOnce`, `HalfAtATime`, `OneAtATime`.
- **Agente CodeDeploy** nas instâncias EC2 (precisa estar instalado e com role). **Rollback automático** por falha de deploy ou **alarme CloudWatch**.

#### 3.3.5 Skill 3.3.5 — CodePipeline e CodeBuild
- **CodePipeline:** *stages* → *actions* (Source, Build, Test, Approval, Deploy, Invoke); **artefatos** trafegam via S3; **aprovação manual** (SNS notifica aprovador); transições; execução disparada por push (EventBridge/CodeConnections).
- **CodeBuild:** `buildspec.yml` — `version`, `env` (`variables`, `parameter-store`, `secrets-manager`), `phases` (**install → pre_build → build → post_build**), `artifacts`, `cache`, `reports`; roda em contêiner efêmero; logs no CloudWatch; VPC opcional; variáveis de ambiente (nunca segredo em texto claro).
- **Como cai:** "Rodar testes e só prosseguir se passarem" → stage Test (CodeBuild) antes do Deploy; "Exigir aprovação antes de produção" → manual approval action.

#### 3.3.6 Skill 3.3.6 — Estratégias de deploy
| Estratégia | Como funciona | Rollback | Custo/risco |
|---|---|---|---|
| **All-at-once** | Troca tudo de uma vez | Redeploy (lento) | Mais barato, maior risco/downtime |
| **Rolling** | Lotes de instâncias | Redeploy | Capacidade reduzida durante o deploy |
| **Rolling + batch extra** | Lote extra mantém capacidade | Redeploy | Pequeno custo extra |
| **Immutable** | Novo ASG, depois troca | Terminar novo ASG (rápido) | Dobra capacidade temporária |
| **Blue/Green** | Ambiente paralelo, troca de tráfego | **Instantâneo** (volta tráfego) | Dobra recursos |
| **Canary** | Pequena % do tráfego primeiro | Rápido | Complexidade/monitoramento |
| **Linear** | Aumenta % em passos iguais | Rápido | Mais lento |

#### 3.3.7 Skill 3.3.7 — Rollback
- CloudFormation: rollback automático em falha; **rollback triggers** com alarmes. CodeDeploy: rollback automático em falha/alarme, redeploy da última versão boa. Lambda: reapontar **alias** para versão anterior. Blue/green: reverter tráfego.

#### 3.3.8 Skill 3.3.8 — Controle de versão e releases
- Branching (GitFlow/trunk-based), **tags** para releases, labels, versionamento semântico, `git` commit SHA como tag de imagem.

#### 3.3.9 Skill 3.3.9 — IA em CI/CD (NOVO)
- Aprovações automatizadas assistidas por IA, provisionamento de ambientes, validação pós-deploy. Princípio: automação com *gates* humanos para produção.

---

## 4. DOMÍNIO 4 — Troubleshooting and Optimization (22%)

### 4.1 Task 4.1 — Análise de causa raiz

#### 4.1.1 Skill 4.1.1 — Depurar código e integrações
- **Códigos HTTP:** 400 requisição inválida; 401 não autenticado; 403 proibido (IAM, resource policy, WAF, KMS); 404 não encontrado; 408/timeout; 409 conflito; 413 payload grande (Lambda sync 6 MB); 429 throttling; 500 erro interno; 502 *bad gateway* (resposta inválida do backend); 503 indisponível; 504 *gateway timeout* (API Gateway 29 s).
- **Exceptions de SDK:** `AccessDenied(Exception)` (permissão), `ThrottlingException`/`TooManyRequestsException`, `ProvisionedThroughputExceededException`, `ResourceNotFoundException`, `ValidationException`, `ConditionalCheckFailedException`, `ExpiredTokenException`, `NoSuchKey`, `NoSuchBucket`, `InvalidParameterValue`, `ServiceUnavailable`, `RequestLimitExceeded`.
- **Erros Lambda clássicos:** `Task timed out after X seconds` (aumentar timeout/otimizar/chamada travada), `Runtime.OutOfMemory`/`Process exited before completing` (memória), `Unable to import module` (pacote/handler/dependência/arquitetura), `AccessDeniedException` (execution role), `429 TooManyRequestsException`/`Rate exceeded` (concorrência), throttling de **reserved concurrency = 0**.
- **Como cai:** log mostra `User: arn:aws:sts::...:assumed-role/fn-role is not authorized to perform: dynamodb:PutItem` → corrigir a *execution role*.

#### 4.1.2 Skill 4.1.2 — Interpretar métricas, logs e traces
- **CloudWatch metrics:** namespace → métrica → dimensões; resolução padrão 1 min, **alta resolução até 1 s**; retenção em camadas (1 s: 3 h; 1 min: 15 dias; 5 min: 63 dias; 1 h: 455 dias). Lambda: `Invocations`, `Errors`, `Duration`, `Throttles`, `ConcurrentExecutions`, `IteratorAge` (atraso em streams), `DeadLetterErrors`, `AsyncEventAge`. SQS: `ApproximateAgeOfOldestMessage`, `ApproximateNumberOfMessagesVisible`. API Gateway: `4XXError`, `5XXError`, `Latency`, `IntegrationLatency`, `Count`, `CacheHitCount`. DynamoDB: `ConsumedRead/WriteCapacityUnits`, `ThrottledRequests`, `UserErrors`, `SystemErrors`.
- **CloudTrail** = **quem** chamou **qual API** (auditoria) — não é métrica de performance. **X-Ray** = **onde** o tempo é gasto. **CloudWatch Logs** = **o que** a aplicação registrou.

#### 4.1.3 Skill 4.1.3 — Consultar logs
- **CloudWatch Logs Insights:** `fields @timestamp, @message | filter @message like /ERROR/ | stats count(*) by bin(5m) | sort @timestamp desc | limit 20`; campos descobertos em JSON; funções `parse`, `stats`, `pct()`. Para Lambda: `filter @type = "REPORT" | stats max(@maxMemoryUsed), avg(@duration)`.
- **Metric filters:** transformam padrões de log em métricas + alarmes. **Subscription filters:** enviam logs em tempo real para Lambda/Kinesis/Firehose/OpenSearch.
- **Athena** para logs em S3 (ex.: ALB, CloudTrail) com SQL.

#### 4.1.4 Skill 4.1.4 — Falhas de deploy via logs de saída
- CloudFormation: aba *Events* e `DescribeStackEvents` (primeira falha cronológica é a causa); CodeBuild: log por fase; CodeDeploy: `/opt/codedeploy-agent/deployment-root/.../logs/scripts.log` e log do agente; Beanstalk: `eb logs`; ECS: *stopped task reason* e logs `awslogs`.
- **Como cai:** "Stack em `ROLLBACK_COMPLETE` após criar" → ler o primeiro evento `CREATE_FAILED`; só dá para excluir e recriar.

#### 4.1.5 Skill 4.1.5 — IA para analisar erros (NOVO)
- Ferramentas de IA (Kiro, Bedrock, assistentes) para explicar stack traces e sugerir correções. Validar sugestão e não colar segredos.

### 4.2 Task 4.2 — Logging, monitoramento e observabilidade

#### 4.2.1 Skill 4.2.1 — Estratégia de logging
- **Logging estruturado (JSON)** com `requestId`, `correlationId`, nível; facilita Logs Insights. Níveis (DEBUG/INFO/WARN/ERROR). Evitar PII. **Powertools for AWS Lambda** (logger, tracer, metrics).
- **Observabilidade** = logs + métricas + traces (permite responder perguntas novas), além de monitoramento (alertas sobre perguntas conhecidas).

#### 4.2.2 Skill 4.2.2 — Métricas customizadas
- `PutMetricData` (custo por métrica/solicitação) vs **Embedded Metric Format (EMF)**: log JSON com bloco `_aws.CloudWatchMetrics` → CloudWatch extrai métricas **sem chamadas de API** (ideal em Lambda, alto volume e dimensões). Resolução padrão (60 s) ou alta (1 s).
- Cuidado com **alta cardinalidade de dimensões** (custo).

#### 4.2.3 Skill 4.2.3 — Alertas
- **CloudWatch Alarms** (estados `OK`/`ALARM`/`INSUFFICIENT_DATA`; avaliação por períodos; ações SNS, Auto Scaling, EC2); **composite alarms**; **EventBridge** para eventos de deploy (CodePipeline/CodeDeploy) → SNS; **Service Quotas** + alarme de uso; **AWS Budgets**.

#### 4.2.4 Skill 4.2.4 — Tracing (X-Ray)
- **Trace** (requisição ponta a ponta) → **segments** (por serviço) → **subsegments** (chamadas downstream). **Service map**. **Annotations** (pares chave-valor **indexados**, filtráveis) vs **Metadata** (não indexados, qualquer objeto). **Sampling rules** (padrão 1 req/s + 5%).
- **Habilitar:** Lambda → `TracingConfig Active` + role `AWSXRayDaemonWriteAccess`; EC2/ECS → **X-Ray daemon** (UDP 2000) / sidecar; instrumentar SDK (`aws-xray-sdk`) ou **ADOT/OpenTelemetry**; API Gateway: tracing por stage.
- **Header:** `X-Amzn-Trace-Id` propaga o trace.
- **Como cai:** "Identificar qual microsserviço causa a latência" → service map do X-Ray; "Filtrar traces por ID de cliente" → annotation.

#### 4.2.5 Skill 4.2.5 — Saúde da carga de trabalho (NOVO)
- **Health checks:** ELB (target group: caminho, intervalo, thresholds; instância *unhealthy* sai de rotação), Route 53 health checks, ECS `healthCheck` do container, **Kubernetes liveness** (reinicia o contêiner travado) vs **readiness** (retira do tráfego até estar pronto) vs *startup probe*.
- **Boas práticas:** endpoint `/health` leve (shallow) vs profundo (dependências); evitar que health check derrube tudo por falha de dependência opcional.

### 4.3 Task 4.3 — Otimização

#### 4.3.1 Skill 4.3.1 — Conceitos de concorrência
- **Lambda:** reserved (garante e limita), provisioned (pré-aquece), `ConcurrentExecutions`; fórmula aproximada: concorrência = invocações/s × duração (s). Throttle → 429 (sync) / retry (async).
- **EC2 Auto Scaling:** *target tracking*, *step*, *scheduled*, *predictive*; cooldown; health checks.
- **Pool de threads / pool de conexões:** reutilizar conexões; **RDS Proxy** para Lambda; `keep-alive`; dimensionar pool.

#### 4.3.2 Skill 4.3.2 — Memória e CPU
- **Lambda Power Tuning** (Step Functions) acha o ponto custo × desempenho; Lambda **Insights**; CloudWatch `max memory used` no REPORT. Graviton (arm64) melhora preço/desempenho.
- ECS/Fargate: combinações válidas de CPU/memória por task.

#### 4.3.3 Skill 4.3.3 — Mensageria otimizada
- **SQS:** *long polling* (`WaitTimeSeconds` até 20 s) reduz chamadas vazias e custo; **batching** (envio/recebimento/exclusão até 10); *delay queue* (até 15 min); *visibility timeout* (padrão 30 s, até 12 h) e `ChangeMessageVisibility`; Extended Client (payload grande via S3).
- **SNS fan-out + filter policies:** cada assinante recebe só o que interessa (evita lógica de descarte no consumidor).
- **Como cai:** "Reduzir custo de polling SQS" → long polling; "Evitar que consumidores processem eventos irrelevantes" → filter policy.

#### 4.3.4 Skill 4.3.4 — Cache (ElastiCache, DAX, CloudFront)
- **CloudFront:** TTL (min/default/max), `Cache-Control`/`Expires` da origem, **cache key** com headers/cookies/query strings (política de cache; incluir só o necessário aumenta *hit ratio*), invalidação (`/*`, custo após cota), **Origin Shield**, compressão. **Lambda@Edge/CloudFront Functions** para reescrita no edge.
- **Cache de resposta de API:** API Gateway cache por stage; `Cache-Control` no cliente.

#### 4.3.5 Skill 4.3.5 — Gargalos (CloudWatch, X-Ray)
- Métricas de latência, throttles, utilização, `IteratorAge`, filas crescendo (`ApproximateAgeOfOldestMessage`), CPU/memória; **Application Signals/Container Insights/Lambda Insights**; correlacionar com X-Ray.

#### 4.3.6 Skill 4.3.6 — IA para otimização (NOVO)
- Detecção de gargalos, uso de recursos, eficiência de código por assistentes de IA; **Compute Optimizer** (recomendações de dimensionamento). *(CodeGuru não consta na lista de serviços do C03.)*

---

## 5. Comparativos "Confrontos Clássicos" (dentro do escopo Developer)

| Confronto | Diferença decisiva |
|---|---|
| SQS vs SNS vs EventBridge vs Kinesis | Fila (pull, retenção) · Pub/sub (push, fan-out) · Roteamento por regras/SaaS · Stream ordenado com replay |
| SQS Standard vs FIFO | Throughput e at-least-once vs ordem + dedupe (exactly-once) |
| Lambda sync vs async vs ESM | Quem chama e quem trata erro/retry |
| DLQ vs Destinations | DLQ só falhas, SQS/SNS · Destinations sucesso e falha, mais alvos |
| Reserved vs Provisioned concurrency | Garante/limita vs elimina cold start |
| Cognito User Pool vs Identity Pool | Login/JWT vs credenciais AWS temporárias |
| Secrets Manager vs Parameter Store | Rotação nativa, pago vs simples/gratuito |
| SSE-S3 vs SSE-KMS vs SSE-C | Chave do S3 · Chave KMS com auditoria · Chave fornecida por você |
| AWS managed key vs CMK | Sem controle de policy/rotação vs controle total |
| LSI vs GSI | Só na criação, strongly consistent vs a qualquer momento, só eventual |
| Query vs Scan | Por chave, eficiente vs tabela inteira |
| Lazy loading vs Write-through | Dado velho possível vs cache sempre atual (custo de escrita) |
| Redis vs Memcached | Estruturas/persistência/replicação vs simples multithread |
| DAX vs ElastiCache | Cache transparente do DynamoDB vs cache genérico |
| REST API vs HTTP API | Recursos completos vs barato/simples |
| CloudFormation vs SAM vs CDK | JSON/YAML puro · Atalho serverless · Código real |
| In-place vs Blue/Green | Mesma infra vs ambiente paralelo (rollback rápido) |
| ECS task role vs execution role | Permissões do app vs puxar imagem/logs |
| Fargate vs EC2 launch type | Sem servidores vs controle da instância |
| X-Ray vs CloudWatch vs CloudTrail | Onde o tempo vai · métricas/logs · quem chamou qual API |
| Annotations vs Metadata (X-Ray) | Indexado/filtrável vs não indexado |
| PutMetricData vs EMF | Chamada de API vs métrica extraída de log |
| Liveness vs Readiness | Reiniciar vs tirar do tráfego |

---

## 6. Limites e Números para Decorar
| Item | Valor |
|---|---|
| Lambda timeout / memória / /tmp | 15 min / 128 MB–10 GB / 512 MB–10 GB |
| Lambda zip / unzip / imagem | 50 MB / 250 MB / 10 GB |
| Lambda payload síncrono | 6 MB |
| Lambda env vars | 4 KB |
| Lambda layers por função | 5 |
| Lambda retries assíncronos | 2 (até 6 h de idade do evento) |
| SQS msg / retenção / visibility | **1 MiB** (Extended Client até 2 GB) / 1 min–14 d (padrão 4 d) / 30 s (máx 12 h) |
| SQS delay / batch / atributos | até 15 min / 10 mensagens / 10 atributos |
| SQS FIFO | 300 TPS por partição (3.000 msg/s com batch); *high throughput* muito maior, varia por região |
| Lambda payload assíncrono | 1 MB (sync 6 MB; resposta *streaming* até 200 MB) |
| Lambda escalonamento | 1.000 ambientes de execução a cada 10 s por função |
| Kinesis registro / leitura por shard | até 10 MiB / 2 MB/s ou 2.000 rec/s |
| DynamoDB limites de índice | 5 LSI e 20 GSI por tabela (padrão) |
| DynamoDB Streams | até 2 leitores simultâneos por shard |
| API Gateway throttle da conta | 10.000 rps + burst 5.000 (2.500/1.250 em regiões mais novas) |
| KMS Encrypt direto | 4.096 bytes (chave simétrica) |
| SQS long polling | até 20 s |
| SQS batch | 10 |
| SQS FIFO throughput | 300 msg/s (3.000 com batch) |
| SNS | filtro por attributes/body |
| Kinesis shard | 1 MB/s ou 1.000 rec/s in · 2 MB/s out |
| Kinesis retenção | 24 h–365 d |
| DynamoDB item | 400 KB |
| DynamoDB RCU/WCU | 4 KB / 1 KB |
| DynamoDB Batch | 25 write / 100 get / 100 transact |
| DynamoDB Streams | 24 h |
| API Gateway timeout | 29 s |
| API Gateway cache TTL | 300 s padrão (máx 3600) |
| STS AssumeRole duração | 15 min–12 h (padrão 1 h) |
| KMS Encrypt direto | 4 KB |
| KMS deleção | 7–30 dias |
| S3 multipart | recomendado >100 MB, obrigatório >5 GB; máx objeto 5 TB |
| S3 requisições/prefixo | 3.500 PUT/POST/DELETE · 5.500 GET/HEAD por segundo |
| CloudWatch alta resolução | 1 s |
| Step Functions Standard / Express | até 1 ano, exactly-once / até 5 min, at-least-once |

> ⚠️ Cotas mudam. Para números críticos, confirmar na doc de cada serviço (links em [[Referencias e Fontes]]).

---

## 7. Step Functions e EventBridge (resumo de alta frequência)
- **Step Functions:** máquina de estados (ASL/JSON). Estados: `Task`, `Choice`, `Parallel`, `Map`, `Wait`, `Pass`, `Succeed`, `Fail`. **Retry** (com `IntervalSeconds`, `BackoffRate`, `MaxAttempts`) e **Catch** nativos. **Standard** (até 1 ano, auditável, exactly-once, workflows longos) vs **Express** (até 5 min, alto volume, at-least-once, barato). Integrações: otimizada (`arn:aws:states:::lambda:invoke`), SDK, **`.sync`** (espera job terminar), **`.waitForTaskToken`** (callback/humano).
- **EventBridge:** padrão de evento (`source`, `detail-type`, `detail`), operadores (`prefix`, `anything-but`, `numeric`, `exists`), DLQ por target, retry de target (até 24 h), **API destinations**.

## 8. S3 (resumo de alta frequência para Developer)
- Consistência forte *read-after-write* para todos os objetos. **Versioning** (delete marker), **MFA Delete**, **Object Lock** (WORM), **replicação** (CRR/SRR; exige versioning), **Transfer Acceleration**, **multipart upload**, **byte-range fetch**, **S3 Select/Athena**, **CORS** (cabeçalhos para acesso do navegador a outro domínio), **Event Notifications**, **Access Points**, **Block Public Access**, ACLs desativadas por padrão (Bucket owner enforced).
- Hospedagem estática: bucket + CloudFront (OAC) preferível a bucket público.

## 9. Tabela de Palavras-Gatilho
| Se a pergunta diz… | Pense em… |
|---|---|
| "decouple", "absorb spikes", "buffer" | SQS |
| "fan out", "notify multiple" | SNS (+ SQS) |
| "route events by content", "SaaS partner", "schedule" | EventBridge |
| "ordered", "replay", "multiple consumers", "real-time stream" | Kinesis Data Streams |
| "load data to S3/Redshift near real time" | Data Firehose |
| "long-running workflow", "orchestrate", "human approval" | Step Functions |
| "without managing servers" | Lambda / Fargate / DynamoDB |
| "single-digit millisecond", "key-value" | DynamoDB |
| "microsecond reads for DynamoDB, minimal code change" | DAX |
| "temporary credentials for mobile users to access AWS" | Cognito Identity Pool |
| "sign up/sign in, JWT" | Cognito User Pool |
| "rotate database credentials automatically" | Secrets Manager |
| "encrypt >4 KB", "envelope" | KMS GenerateDataKey |
| "time-limited access to a private object" | Presigned URL |
| "least operational overhead" | Serviço gerenciado/serverless |
| "without code changes" | Configuração/serviço intermediário (ex.: DAX, RDS Proxy, CloudFront) |
| "gradually shift traffic", "canary" | CodeDeploy / alias weighted / API Gateway canary |
| "instant rollback" | Blue/green |
| "trace requests across services" | X-Ray |
| "audit who called an API" | CloudTrail |
| "custom metrics from Lambda without API calls" | EMF |
| "feature flag without redeploy" | AppConfig |
| "deploy serverless app with IaC shorthand" | SAM |
| "model-agnostic request to Bedrock" | Converse API |
| "block PII/prompt attacks in AI I/O" | Bedrock Guardrails |
| "private connectivity to AI service" | VPC interface endpoint (PrivateLink) |

---

## 10. Checklist de Estudo por Domínio
- [ ] D1 Lambda (ESM, destinations, concorrência, VPC) — **prioridade máxima**
- [ ] D1 DynamoDB (chaves, índices, capacidade, Query/Scan, TTL, Streams)
- [ ] D1 SQS/SNS/EventBridge/Kinesis/Step Functions
- [ ] D1 API Gateway (integrações, stages, erros)
- [ ] D2 IAM (avaliação de política, trust vs permissions), STS, Cognito
- [ ] D2 KMS (envelope, key policy, rotação), Secrets Manager vs Parameter Store
- [ ] D2 Presigned URLs, ACM
- [ ] D2 IA: Bedrock Guardrails, VPC endpoints, agentes (AgentCore), logs
- [ ] D3 CloudFormation/SAM/CDK, CodeBuild/CodeDeploy/CodePipeline, estratégias de deploy
- [ ] D3 ECR/ECS/EKS/Fargate, AppConfig, ambientes (aliases/stages)
- [ ] D4 CloudWatch (Logs Insights, EMF, alarms), X-Ray, CloudTrail
- [ ] D4 Otimização (concorrência, memória, cache, long polling, filter policies)

*Próximo passo:* gerar questões com [[DVA-C03 - Prompts de Questoes]], domínio por domínio.
