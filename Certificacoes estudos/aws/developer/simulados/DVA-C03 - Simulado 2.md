---
tags: [aws, certificacao, developer-associate, dva-c03, simulado]
exame: DVA-C03
simulado: 2
data: 2026-11-04
questoes: 65
---

# 📝 Simulado 2 — AWS Certified Developer – Associate (DVA-C03)

**Data de elaboração:** 04/11/2026 · **Tempo sugerido:** 130 min · **Questões:** 65 · **Meta:** ~47 acertos (≈72%)

> **Instruções:** questões originais no estilo da prova. "Selecione DUAS" indica múltipla resposta (marque todas). Questões agrupadas por domínio para estudo; na prova elas são misturadas. Abra o **Gabarito** só no final.
> Base: [[DVA-C03 - Glossario]] · Prompts: [[DVA-C03 - Prompts de Questoes]] · Simulado anterior: [[DVA-C03 - Simulado 1]].

---

## Domínio 1 — Development with AWS Services

**Q1.** Uma rotina de processamento em lote leva cerca de 40 minutos e hoje roda em uma função Lambda, que expira. A equipe quer a MENOR reescrita de código e nenhum servidor para gerenciar. O que usar?
- A. Aumentar o timeout da função para 40 minutos.
- B. Dividir manualmente o código em 3 funções encadeadas por e-mail.
- C. Empacotar o código em um contêiner e executá-lo como tarefa no AWS Fargate (ECS), disparada por um evento.
- D. Aumentar a memória da Lambda para 10 GB.

**Q2.** Quando uma função Lambda, invocada de forma assíncrona, conclui com sucesso, o resultado deve ser publicado em um barramento do Amazon EventBridge sem código adicional. O que configurar?
- A. Uma DLQ do tipo SNS.
- B. Um *destination* de sucesso (on-success) apontando para o EventBridge.
- C. Um alarme do CloudWatch em `Invocations`.
- D. Uma layer com o SDK do EventBridge.

**Q3.** Um desenvolvedor define *reserved concurrency* = 0 em uma função Lambda. O que acontece?
- A. A função passa a usar concorrência ilimitada.
- B. A função usa apenas concorrência provisionada.
- C. A função escala para 1.000 execuções simultâneas.
- D. Todas as invocações da função são limitadas (*throttled*) e nenhuma é executada.

**Q4.** Vinte funções Lambda usam a mesma biblioteca interna de 30 MB. Como evitar duplicar a biblioteca em cada pacote?
- A. Publicar a biblioteca como *Lambda layer* e associá-la às funções.
- B. Colocar a biblioteca em variável de ambiente.
- C. Baixar a biblioteca do S3 a cada invocação.
- D. Aumentar o limite do pacote .zip para 500 MB.

**Q5.** Cada mensagem enviada a uma fila SQS só deve ficar visível para consumo 5 minutos depois de enviada. Qual configuração usar?
- A. `VisibilityTimeout` = 300 na fila.
- B. `MessageRetentionPeriod` = 300.
- C. `DelaySeconds` = 300 (fila de atraso).
- D. `WaitTimeSeconds` = 300.

**Q6.** Uma mensagem que falhar em 3 recebimentos deve ser movida automaticamente para outra fila para análise. Como configurar?
- A. Na DLQ, definir `maxReceiveCount` = 3.
- B. Na fila de origem, definir a *redrive policy* com `maxReceiveCount` = 3 apontando para a DLQ.
- C. Na função Lambda, definir `MaximumRetryAttempts` = 3 para qualquer fila.
- D. Habilitar *long polling*.

**Q7.** Uma aplicação precisa enviar mensagens de 5 MB por SQS. Qual abordagem funciona?
- A. SQS Extended Client Library, que guarda o payload no S3 e envia a referência.
- B. Aumentar o limite da fila para 5 MB nas configurações.
- C. Compactar a mensagem em Base64.
- D. Dividir a mensagem em 4 KB.

**Q8.** Um evento de pedido deve ser entregue a três filas SQS independentes (faturamento, estoque, notificação), de forma durável e desacoplada. Qual arquitetura usar?
- A. Três chamadas síncronas do produtor.
- B. Uma fila única com três consumidores.
- C. Um stream Kinesis com um shard.
- D. Um tópico SNS com as três filas SQS como assinaturas (*fan-out*).

**Q9.** Uma tabela DynamoDB existente tem chave composta (`customerId`, `orderDate`). Precisa-se consultar os pedidos de um cliente ordenados por `status` (outro atributo). O que fazer?
- A. Adicionar um LSI à tabela existente.
- B. Criar um GSI com `customerId` como chave de partição e `status` como chave de ordenação.
- C. Alterar a chave de ordenação da tabela.
- D. Usar `Scan` com filtro.

**Q10.** Uma operação deve debitar um saldo e registrar um lançamento em duas tabelas, tudo ou nada. Qual API do DynamoDB usar?
- A. `BatchWriteItem`
- B. `PutItem` duas vezes
- C. `TransactWriteItems`
- D. `UpdateItem` com `ReturnValues`

**Q11.** Sessões de usuário em uma tabela DynamoDB devem expirar automaticamente, sem consumir capacidade de gravação para a exclusão. O que usar?
- A. TTL com um atributo de epoch (segundos).
- B. Uma Lambda agendada que faz `DeleteItem`.
- C. `Scan` diário.
- D. DynamoDB Streams.

**Q12.** Um valor agregado (total de vendas por loja) deve ser atualizado sempre que um item é inserido em uma tabela DynamoDB. Qual padrão usar?
- A. `Scan` periódico.
- B. Trigger de banco relacional.
- C. Polling de 1 segundo.
- D. DynamoDB Streams acionando uma função Lambda que atualiza o agregado.

**Q13.** Uma aplicação lê 40 itens de 5 KB por segundo com leitura **fortemente consistente**. Quantas RCUs?
- A. 40
- B. 80
- C. 100
- D. 160

**Q14.** Uma aplicação faz 20 gravações **transacionais** por segundo de itens de 3 KB. Quantas WCUs?
- A. 60
- B. 80
- C. 120
- D. 240

**Q15.** Uma chamada `BatchWriteItem` retorna `UnprocessedItems` não vazio. O que fazer?
- A. Reenviar apenas os itens não processados com backoff exponencial.
- B. Ignorar, pois o lote foi concluído.
- C. Reenviar todo o lote imediatamente em loop.
- D. Trocar para `Scan`.

**Q16.** Um API Gateway REST tem stages `dev` e `prod`; cada stage deve chamar o alias correspondente (`dev`/`prod`) da mesma função Lambda. Qual recurso usar?
- A. Duas APIs separadas obrigatoriamente.
- B. Variáveis de stage referenciadas na integração (por exemplo, `${stageVariables.alias}`).
- C. Variáveis de ambiente da Lambda.
- D. Um custom domain por alias.

**Q17.** Como rejeitar com `400` requisições sem o parâmetro obrigatório `orderId`, sem invocar a Lambda?
- A. Validar no código da Lambda.
- B. Usar um WAF.
- C. Habilitar *request validation* no método com parâmetro/modelo obrigatório.
- D. Usar cache.

**Q18.** Qual tipo de API do Amazon API Gateway oferece cache de respostas integrado por stage?
- A. HTTP API
- B. WebSocket API
- C. REST API
- D. Todos os tipos

**Q19.** Três aplicações consomem o mesmo stream Kinesis e cada uma precisa de 2 MB/s por shard sem competir entre si. O que usar?
- A. Aumentar a retenção.
- B. Registrar cada consumidor com *enhanced fan-out*.
- C. Usar `GetRecords` em loop mais rápido.
- D. Trocar para SQS FIFO.

**Q20.** Uma fila SQS Standard entrega mensagens ao menos uma vez e às vezes duplica. Selecione DUAS formas de garantir efeito único no processamento.
- A. Gravar um identificador único do pedido no DynamoDB com `ConditionExpression attribute_not_exists` antes de processar.
- B. Usar uma fila FIFO com `MessageDeduplicationId`.
- C. Aumentar o *visibility timeout* para 12 horas.
- D. Remover a DLQ.
- E. Reduzir o tamanho do lote para 1.

---

## Domínio 2 — Security

**Q21.** Uma aplicação web precisa de cadastro, login, recuperação de senha e emissão de tokens JWT para seus usuários. Qual serviço atende?
- A. Amazon Cognito User Pool.
- B. AWS IAM Identity Center.
- C. AWS STS.
- D. AWS Directory Service.

**Q22.** Um Lambda authorizer é executado em toda requisição e aumenta a latência. Como reduzir mantendo a autorização?
- A. Remover o authorizer.
- B. Trocar para chave de API.
- C. Habilitar o cache do resultado do authorizer com TTL adequado.
- D. Aumentar a memória da Lambda do backend.

**Q23.** Uma empresa quer que desenvolvedores criem roles IAM para suas aplicações, mas sem poder conceder mais permissões do que um teto definido. O que usar?
- A. SCPs apenas para a conta de gerenciamento.
- B. *Permissions boundary* aplicado aos desenvolvedores.
- C. Grupos IAM aninhados.
- D. Políticas inline sem restrições.

**Q24.** A exclusão de objetos em um bucket só deve ser permitida a usuários autenticados com MFA. O que adicionar à política?
- A. `Condition` com `aws:SourceIp`.
- B. `Condition` com `s3:prefix`.
- C. `Condition` com `aws:SecureTransport`.
- D. `Condition` com `aws:MultiFactorAuthPresent` = `true`.

**Q25.** Objetos em um bucket da conta A estão criptografados com SSE-KMS usando uma CMK da conta A. A role da conta B recebe `AccessDenied` ao ler. O que corrigir?
- A. Permitir a role da conta B na *key policy* da CMK e conceder `kms:Decrypt` na política da role.
- B. Trocar para SSE-S3 e manter a CMK.
- C. Habilitar versionamento no bucket.
- D. Aumentar a duração da sessão da role.

**Q26.** Uma chamada ao KMS retorna `KMSInvalidStateException`. Qual causa é mais provável?
- A. Payload acima de 4 KB.
- B. A chave está desabilitada ou pendente de exclusão.
- C. A região do cliente está errada.
- D. O relógio do cliente está dessincronizado.

**Q27.** Segredos no Secrets Manager precisam estar disponíveis em outra Região para recuperação de desastre. O que usar?
- A. Replicação de segredos para a Região secundária (réplicas do segredo).
- B. Copiar manualmente a cada mês.
- C. Exportar para um bucket S3.
- D. Usar Parameter Store Standard.

**Q28.** Uma Lambda busca um segredo a cada invocação, aumentando latência e custo. Qual melhoria é recomendada?
- A. Aumentar o timeout.
- B. Armazenar o segredo em uma variável global no código-fonte.
- C. Reduzir a memória.
- D. Usar a Lambda extension (ou cache em memória fora do handler) para reutilizar o segredo.

**Q29.** Um site de vídeo (HLS) com centenas de segmentos privados no CloudFront deve liberar acesso a um usuário autenticado. O que usar?
- A. Uma *presigned URL* do S3 por segmento.
- B. Bucket público.
- C. *Signed cookies* do CloudFront.
- D. Chave de API.

**Q30.** Um navegador precisa enviar um arquivo grande diretamente ao S3, sem expor credenciais. O que o backend deve gerar?
- A. Uma chave de acesso temporária do root.
- B. Uma *presigned URL* para `PUT` (ou *presigned POST*) com expiração curta.
- C. Uma bucket policy pública de escrita.
- D. Um usuário IAM por upload.

**Q31.** Uma aplicação em EC2 acessa o S3. Para reduzir o risco de roubo de credenciais via SSRF, selecione DUAS ações.
- A. Exigir o IMDSv2 nas instâncias.
- B. Usar uma role de instância (*instance profile*) em vez de chaves de acesso.
- C. Gravar as chaves em variáveis de ambiente do `.bashrc`.
- D. Abrir a porta 22 para o mundo.
- E. Desativar o CloudTrail.

**Q32.** Um ALB precisa de um certificado TLS público que se renove automaticamente, sem manutenção. O que usar?
- A. Certificado autoassinado no ALB.
- B. Certificado público do AWS Certificate Manager (ACM) com validação DNS.
- C. Certificado importado manualmente a cada ano.
- D. Certificado gerado pelo OpenSSL na instância.

**Q33.** Serviços internos precisam de TLS mútuo (mTLS) usando uma autoridade certificadora privada gerenciada. Qual serviço usar?
- A. AWS KMS
- B. AWS WAF
- C. AWS Secrets Manager
- D. AWS Private CA

**Q34.** Como mascarar automaticamente dados sensíveis (como números de documentos) nos logs do CloudWatch Logs?
- A. *Data protection policy* no grupo de logs.
- B. Reduzir a retenção.
- C. Habilitar o X-Ray.
- D. Habilitar o CloudTrail.

**Q35.** Uma política IAM deve permitir invocar apenas um modelo específico do Amazon Bedrock. O que configurar?
- A. `Resource: "*"` em `bedrock:InvokeModel`.
- B. Uma política de bucket S3.
- C. O ARN do modelo de fundação no elemento `Resource` da permissão `bedrock:InvokeModel`.
- D. Um alarme do CloudWatch.

**Q36.** Uma aplicação em subnets privadas chama o Bedrock. Requisitos: tráfego sem passar pela internet e só um grupo de roles pode invocar um modelo aprovado. Selecione DUAS ações.
- A. Criar um VPC endpoint de interface para o Bedrock Runtime.
- B. Restringir a permissão `bedrock:InvokeModel` ao ARN do modelo aprovado nas roles autorizadas.
- C. Criar um NAT gateway com rota para a internet.
- D. Permitir IP público nas instâncias.
- E. Desativar o IAM.

**Q37.** Um agente de IA atende vários clientes. Como evitar que a memória de um cliente apareça para outro?
- A. Compartilhar um único contexto global.
- B. Isolar o contexto/memória por sessão (e por identidade) do usuário.
- C. Aumentar o tamanho do contexto.
- D. Reduzir a temperatura.

---

## Domínio 3 — Testing and Deployment

**Q38.** No CodeBuild, como injetar uma senha armazenada no Secrets Manager como variável de ambiente sem deixá-la no repositório?
- A. Seção `env.secrets-manager` no `buildspec.yml`.
- B. Escrever a senha em `env.variables`.
- C. Commit do arquivo `.env`.
- D. Colocar na imagem Docker.

**Q39.** Uma equipe quer repositório privado de pacotes npm com *proxy* para o registro público. O que usar?
- A. Amazon S3 com versionamento.
- B. Amazon ECR.
- C. AWS CodeArtifact com *upstream* para npmjs.
- D. AWS CodeCommit.

**Q40.** Como fazer o CodeDeploy reverter automaticamente um deploy se um alarme do CloudWatch disparar?
- A. Criar um alarme e executar rollback manual.
- B. Associar o alarme ao *deployment group* e habilitar rollback automático em caso de alarme.
- C. Criar uma regra EventBridge para `StopDeployment`.
- D. Reduzir o tempo de espera do hook.

**Q41.** Um serviço ECS atrás de um ALB deve ser atualizado com *blue/green*, validando a nova versão em um listener de teste antes do corte de tráfego. Selecione DUAS ações.
- A. Usar o tipo de deployment *blue/green* do CodeDeploy para ECS.
- B. Configurar um *test listener* no ALB.
- C. Usar *rolling update* com `minimumHealthyPercent` = 0.
- D. Usar *in-place deployment* do CodeDeploy no ECS.
- E. Usar uma instância EC2 única sem balanceador.

**Q42.** Antes de excluir uma stack com um banco RDS, a equipe quer que o CloudFormation tire um snapshot automaticamente. O que configurar no recurso?
- A. `DeletionPolicy: Delete`
- B. `DeletionPolicy: Snapshot`
- C. `DependsOn`
- D. `UpdateReplacePolicy: Delete`

**Q43.** Uma stack precisa usar o ID de uma VPC criada por outra stack. O que usar?
- A. Exportar o valor na stack da VPC e usar `!ImportValue` na outra.
- B. Copiar o ID manualmente no template.
- C. `!GetAtt` entre stacks diferentes sem exportação.
- D. `Mappings` global.

**Q44.** Como implantar o mesmo template em várias contas e Regiões com uma única operação?
- A. Nested stacks.
- B. Change sets.
- C. Drift detection.
- D. CloudFormation StackSets.

**Q45.** Qual comando do AWS CDK gera o template do CloudFormation a partir do código?
- A. `cdk bootstrap`
- B. `cdk synth`
- C. `cdk destroy`
- D. `cdk init`

**Q46.** Para acelerar a iteração de desenvolvimento de um app serverless, sincronizando mudanças de código com a nuvem sem rodar um deploy completo, qual comando do SAM usar?
- A. `sam package`
- B. `sam validate`
- C. `sam sync --watch`
- D. `sam delete`

**Q47.** Cada branch de um app web deve ter um ambiente próprio com URL, criado automaticamente. O que usar?
- A. AWS Amplify com deploy por branch.
- B. Um bucket S3 por branch criado manualmente.
- C. Elastic Beanstalk com uma única versão.
- D. CloudFront sem origens.

**Q48.** Como enviar 5% do tráfego para uma nova versão de uma função Lambda sem alterar o código dos clientes?
- A. Duplicar a função com outro nome.
- B. Reduzir a memória da nova versão.
- C. Usar a versão `$LATEST` diretamente.
- D. Configurar *weighted alias* apontando 95%/5% entre a versão atual e a nova.

**Q49.** No Elastic Beanstalk, qual estratégia usa dois ambientes e troca a URL (CNAME) entre eles?
- A. Rolling
- B. Blue/green (*swap environment URLs*)
- C. All at once
- D. Immutable

**Q50.** Qual prática reduz o tamanho de imagens Docker de aplicações compiladas?
- A. Instalar o compilador na imagem final.
- B. Usar sempre a tag `latest`.
- C. *Multi-stage build*, copiando apenas os artefatos finais para a imagem de runtime.
- D. Incluir o código-fonte e os testes na imagem.

**Q51.** Para testar integrações sem depender de serviços externos, selecione DUAS práticas.
- A. Usar a integração MOCK do API Gateway para simular a dependência.
- B. Testes unitários com clientes AWS SDK simulados (*mocks*).
- C. Testar diretamente em produção com dados reais.
- D. Desabilitar validação de entrada.
- E. Chamar a API real de pagamento em cada teste.

---

## Domínio 4 — Troubleshooting and Optimization

**Q52.** Como transformar ocorrências da palavra `ERROR` em um grupo de logs em uma métrica para alarme?
- A. Subscription filter.
- B. Dashboard.
- C. Metric filter.
- D. CloudTrail Insights.

**Q53.** Muitos alarmes disparam juntos por uma mesma causa, gerando ruído. O que combinar vários alarmes em um único estado?
- A. Composite alarm.
- B. Alarme de anomalia.
- C. Ação do Auto Scaling.
- D. Event bus.

**Q54.** Para investigar um problema, a equipe quer amostrar mais traces do caminho `/checkout` no X-Ray. O que ajustar?
- A. O tamanho do segmento.
- B. Uma *sampling rule* específica para esse caminho.
- C. O período de retenção do CloudWatch.
- D. O número de annotations.

**Q55.** Em instâncias EC2, o X-Ray daemon recebe segmentos do SDK. Em qual porta/protocolo ele escuta por padrão?
- A. TCP 443
- B. TCP 2000
- C. UDP 53
- D. UDP 2000

**Q56.** Qual parâmetro cria uma métrica customizada de alta resolução (1 segundo) via `PutMetricData`?
- A. `Period=60`
- B. `Unit=Count`
- C. `StorageResolution=1`
- D. `Dimensions` vazias

**Q57.** Uma API recebe 50 requisições por segundo e cada execução da Lambda leva em média 2 s. Qual é a concorrência aproximada necessária?
- A. 100
- B. 25
- C. 52
- D. 1.000

**Q58.** O processamento de uma mensagem SQS leva até 2 minutos, mas o *visibility timeout* é 30 s e há duplicidade. O que ajustar?
- A. Reduzir o timeout da função.
- B. Definir o *visibility timeout* maior que o tempo de processamento (ou usar `ChangeMessageVisibility`).
- C. Reduzir a retenção.
- D. Trocar a fila para FIFO.

**Q59.** Um contêiner entra em *deadlock*: o processo continua rodando, mas não responde. Qual verificação reinicia automaticamente esse contêiner?
- A. *Readiness probe*.
- B. *Startup probe* somente.
- C. *Liveness probe*.
- D. *Resource limit*.

**Q60.** Nos logs: `Task timed out after 3.00 seconds`. Qual é a causa mais provável?
- A. O timeout padrão de 3 s da função é insuficiente para a execução.
- B. A role não tem permissão.
- C. Falta o handler.
- D. O pacote excede 250 MB.

**Q61.** A Lambda falha com `Runtime.ImportModuleError: Unable to import module 'app'`. Qual é a causa mais provável?
- A. Falta de permissão IAM.
- B. Concurrency esgotada.
- C. Timeout.
- D. O handler aponta para arquivo/módulo inexistente ou faltam dependências no pacote.

**Q62.** Os logs mostram `AccessDeniedException: ... is not authorized to perform: dynamodb:PutItem`. Qual correção aplicar?
- A. Aumentar a memória.
- B. Adicionar `dynamodb:PutItem` à *execution role* da função para a tabela correta.
- C. Aumentar o timeout.
- D. Habilitar cache.

**Q63.** O API Gateway mostra `IntegrationLatency` alta e `Latency` ≈ `IntegrationLatency`. Onde investigar?
- A. No cache do CloudFront.
- B. Na validação de requisições.
- C. No backend (integração), por exemplo na Lambda ou no serviço chamado.
- D. No certificado do domínio.

**Q64.** Para reduzir custos de leituras repetitivas em DynamoDB, selecione DUAS ações.
- A. Usar o DAX para cachear leituras.
- B. Usar leituras eventualmente consistentes quando a aplicação tolerar.
- C. Trocar `Query` por `Scan`.
- D. Usar sempre leituras fortemente consistentes.
- E. Aumentar as WCUs.

**Q65.** Como atualizar assets estáticos imediatamente e evitar custos de invalidação no CloudFront?
- A. Invalidar `/*` a cada deploy.
- B. Versionar os nomes dos arquivos (por exemplo, `app.4f9c2.js`).
- C. Reduzir o TTL para 0 em todos os arquivos.
- D. Desabilitar o CloudFront.

---
---

# ✅ GABARITO — Simulado 2

| Q | Resp. | Skill | Explicação |
|---|---|---|---|
| 1 | **C** | 1.1.1 | Lambda tem limite de 15 min; Fargate roda contêiner longo sem servidores. |
| 2 | **B** | 1.2.3 | *Destination* on-success suporta EventBridge. |
| 3 | **D** | 4.3.1 | Reserved = 0 bloqueia a função (throttle total). |
| 4 | **A** | 3.1.1 | Layer compartilha dependências. |
| 5 | **C** | 4.3.3 | `DelaySeconds` (até 15 min) atrasa a visibilidade. |
| 6 | **B** | 1.1.3 | `maxReceiveCount` fica na *redrive policy* da fila de origem. |
| 7 | **A** | 1.1.5 | Extended Client usa S3 para payloads acima do limite (1 MiB). |
| 8 | **D** | 1.1.8 | Fan-out SNS → SQS. |
| 9 | **B** | 1.3.4 | LSI só na criação; GSI resolve. |
| 10 | **C** | 1.3.4 | Transações ACID. |
| 11 | **A** | 1.3.1 | TTL não consome WCU. |
| 12 | **D** | 1.2.4 | Streams + Lambda. |
| 13 | **B** | 1.3.4 | 5 KB → 2 blocos de 4 KB × 40 = 80. |
| 14 | **C** | 1.3.4 | 3 WCU × 2 (transacional) × 20 = 120. |
| 15 | **A** | 1.1.5 | Reenviar apenas `UnprocessedItems` com backoff. |
| 16 | **B** | 3.1.5 | Stage variables. |
| 17 | **C** | 1.1.4 | *Request validation* devolve 400 sem invocar. |
| 18 | **C** | 1.1.4 | Cache integrado é de REST API. |
| 19 | **B** | 1.1.6 | *Enhanced fan-out* dá 2 MB/s por consumidor/shard. |
| 20 | **A, B** | 1.1.2 | Idempotência: escrita condicional ou FIFO com deduplicação. |
| 21 | **A** | 2.1.1 | User Pool = diretório + JWT. |
| 22 | **C** | 2.1.2 | Cache do authorizer. |
| 23 | **B** | 2.1.6 | *Permissions boundary* define o teto. |
| 24 | **D** | 2.1.2 | `aws:MultiFactorAuthPresent`. |
| 25 | **A** | 2.2.4 | Cross-account com KMS exige *key policy* e IAM. |
| 26 | **B** | 2.2.4 | Estado inválido da chave. |
| 27 | **A** | 2.2.7 | Réplicas de segredos multi-região. |
| 28 | **D** | 2.2.7 | Cache/extension. |
| 29 | **C** | 2.1.4 | *Signed cookies* para vários arquivos. |
| 30 | **B** | 2.1.4 | Presigned PUT/POST. |
| 31 | **A, B** | 2.1.3 | IMDSv2 + roles em vez de chaves. |
| 32 | **B** | 2.2.2 | ACM renova automaticamente. |
| 33 | **D** | 2.2.2 | Private CA. |
| 34 | **A** | 2.2.6 | Data protection policy. |
| 35 | **C** | 2.3.1 | ARN do modelo no `Resource`. |
| 36 | **A, B** | 2.3.1 / 2.3.2 | Endpoint privado + permissão restrita. |
| 37 | **B** | 2.3.4 | Isolamento de sessão. |
| 38 | **A** | 3.1.4 | `env.secrets-manager`. |
| 39 | **C** | 3.1.3 | CodeArtifact com upstream. |
| 40 | **B** | 3.3.7 | Alarme no *deployment group* + rollback automático. |
| 41 | **A, B** | 3.3.2 / 3.3.6 | Blue/green com CodeDeploy e *test listener*. In-place não existe para ECS. |
| 42 | **B** | 3.3.3 | `DeletionPolicy: Snapshot`. |
| 43 | **A** | 3.3.3 | Export + `!ImportValue`. |
| 44 | **D** | 3.3.3 | StackSets. |
| 45 | **B** | 3.3.3 | `cdk synth`. |
| 46 | **C** | 3.2.1 | `sam sync --watch`. |
| 47 | **A** | 3.2.4 | Amplify branches. |
| 48 | **D** | 3.2.4 | Alias ponderado. |
| 49 | **B** | 3.3.6 | Blue/green com troca de CNAME. |
| 50 | **C** | 3.1.2 | Multi-stage build. |
| 51 | **A, B** | 3.2.1 / 3.2.2 | MOCK e mocks de SDK. |
| 52 | **C** | 4.2.2 | Metric filter → métrica → alarme. |
| 53 | **A** | 4.2.3 | Composite alarm. |
| 54 | **B** | 4.2.4 | Sampling rules. |
| 55 | **D** | 4.2.4 | Daemon escuta em UDP 2000. |
| 56 | **C** | 4.2.2 | `StorageResolution=1`. |
| 57 | **A** | 4.3.1 | 50 × 2 = 100. |
| 58 | **B** | 4.3.3 | Visibility timeout > processamento. |
| 59 | **C** | 4.2.5 | Liveness reinicia; readiness só tira do tráfego. |
| 60 | **A** | 4.1.1 | Timeout padrão de 3 s. |
| 61 | **D** | 4.1.1 | Handler/módulo/dependências. |
| 62 | **B** | 4.1.1 | Corrigir a execution role. |
| 63 | **C** | 4.1.2 | `IntegrationLatency` aponta para o backend. |
| 64 | **A, B** | 4.3.4 | DAX e leituras eventuais reduzem custo. |
| 65 | **B** | 4.3.4 | Arquivos versionados evitam invalidações. |

## Contagem
59 questões de escolha única e 6 de múltipla resposta (Q20, Q31, Q36, Q41, Q51 e Q64).

## Desempenho por domínio (preencha)
| Domínio | Questões | Acertos | % |
|---|---|---|---|
| D1 Development | Q1–Q20 | | |
| D2 Security | Q21–Q37 | | |
| D3 Testing and Deployment | Q38–Q51 | | |
| D4 Troubleshooting and Optimization | Q52–Q65 | | |
