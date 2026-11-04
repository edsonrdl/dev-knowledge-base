---
tags: [aws, certificacao, developer-associate, dva-c03, simulado]
exame: DVA-C03
simulado: 3
data: 2026-11-04
questoes: 65
---

# 📝 Simulado 3 — AWS Certified Developer – Associate (DVA-C03)

**Data de elaboração:** 04/11/2026 · **Tempo sugerido:** 130 min · **Questões:** 65 · **Meta:** ~47 acertos (≈72%)

> **Instruções:** questões originais no estilo da prova. "Selecione DUAS" indica múltipla resposta. Agrupadas por domínio para estudo. Abra o **Gabarito** só no final.
> Base: [[DVA-C03 - Glossario]] · Prompts: [[DVA-C03 - Prompts de Questoes]] · Anteriores: [[DVA-C03 - Simulado 1]], [[DVA-C03 - Simulado 2]].

---

## Domínio 1 — Development with AWS Services

**Q1.** Em uma máquina de estados do AWS Step Functions, um estado `Task` falha de forma intermitente com erros transitórios. Qual é a forma nativa de tentar novamente com espera crescente?
- A. Um estado `Wait` seguido de `Choice` manual.
- B. O campo `Retry` com `IntervalSeconds`, `BackoffRate` e `MaxAttempts`.
- C. Um estado `Parallel` com duas cópias da tarefa.
- D. Um alarme do CloudWatch que reinicia a execução.

**Q2.** Uma solução de ingestão recebe centenas de milhares de eventos curtos por segundo (cada fluxo dura segundos) e aceita processamento *at-least-once* com o menor custo. Qual tipo de máquina de estados usar?
- A. Standard
- B. Standard com `Map` distribuído
- C. Standard com *callback*
- D. Express

**Q3.** Uma função Lambda deve rodar todos os dias às 02:00 UTC. Qual é a solução com o MENOR esforço?
- A. Uma instância EC2 com `cron`.
- B. Uma regra (ou schedule) do Amazon EventBridge com expressão `cron` apontando para a Lambda.
- C. Um loop com `sleep` dentro da função.
- D. Um tópico SNS com assinatura diária.

**Q4.** Mensagens de uma fila SQS devem ser enriquecidas com dados de uma API e então iniciar uma execução do Step Functions, sem código de "cola". O que usar?
- A. Uma Lambda com polling manual.
- B. Amazon SNS com filtro.
- C. Amazon EventBridge Pipes (origem SQS, enriquecimento e destino Step Functions).
- D. Kinesis Data Firehose.

**Q5.** Quando imagens são enviadas ao S3, uma Lambda as processa. A equipe quer evitar perda de eventos se a Lambda ficar indisponível e controlar a taxa de processamento. O que fazer?
- A. Notificações do S3 direto para a Lambda, sem outras configurações.
- B. Notificações do S3 para uma fila SQS e a Lambda consumindo a fila.
- C. Polling do bucket a cada segundo.
- D. Habilitar versionamento no bucket.

**Q6.** Um arquivo de 8 GB precisa ser enviado ao S3. Qual abordagem é necessária?
- A. Um único `PutObject`.
- B. `PutObject` com `Content-Length` de 8 GB.
- C. Upload *multipart* (partes enviadas e depois concluídas).
- D. Compactar para 4 GB e usar `PutObject`.

**Q7.** Uma aplicação precisa ler apenas os primeiros 1 MB de um objeto grande no S3. Como reduzir a transferência?
- A. Baixar tudo e cortar localmente.
- B. Usar *byte-range fetch* com o header `Range`.
- C. Usar S3 Transfer Acceleration.
- D. Usar versionamento.

**Q8.** Consultas do Amazon Athena sobre grandes arquivos CSV no S3 são lentas e caras. Qual mudança reduz mais o custo (dados varridos)?
- A. Compactar o CSV em ZIP.
- B. Aumentar a memória do Athena.
- C. Converter para Parquet e particionar por data.
- D. Usar versões de objetos.

**Q9.** Um catálogo de produtos precisa de busca *full-text* com relevância e filtros. Qual serviço usar?
- A. Amazon OpenSearch Service.
- B. Amazon S3 Select.
- C. DynamoDB `Scan`.
- D. Amazon Athena.

**Q10.** Uma aplicação de ranking precisa de estruturas como *sorted sets*, persistência e replicação. Qual engine do Amazon ElastiCache escolher?
- A. Memcached
- B. Memcached com múltiplos nós
- C. Redis (ou Valkey)
- D. Nenhum; use DynamoDB

**Q11.** Qual estratégia de cache evita dados desatualizados gravando no cache e no banco a cada escrita?
- A. *Lazy loading*
- B. *Write-through*
- C. TTL somente
- D. Cache-aside sem expiração

**Q12.** Uma função Lambda lê um stream do DynamoDB, mas só precisa processar eventos `INSERT`. Como evitar invocações desnecessárias?
- A. Verificar o tipo no código e ignorar.
- B. Usar um segundo stream.
- C. Reduzir a memória.
- D. Configurar *filter criteria* no event source mapping para `eventName = INSERT`.

**Q13.** Um registro inválido ("poison pill") em um shard Kinesis faz a Lambda falhar repetidamente e bloqueia o processamento do shard. Selecione DUAS configurações do event source mapping que mitigam isso.
- A. `BisectBatchOnFunctionError` habilitado.
- B. Um *destination* de falha (on-failure) e limites de `MaximumRetryAttempts`/`MaximumRecordAgeInSeconds`.
- C. Aumentar o timeout para 15 minutos.
- D. Aumentar a retenção do stream para 365 dias.
- E. Trocar o stream por uma fila FIFO.

**Q14.** Uma função precisa de dependências de 3 GB (bibliotecas de ML). Qual formato de empacotamento usar?
- A. .zip com layers.
- B. .zip de 3 GB enviado pelo console.
- C. Variáveis de ambiente.
- D. Imagem de contêiner (até 10 GB) publicada no ECR.

**Q15.** Uma Lambda precisa de 5 GB de espaço temporário em disco durante o processamento. O que configurar?
- A. Aumentar o armazenamento efêmero (`/tmp`) até 10 GB.
- B. Aumentar o timeout.
- C. Criar uma layer de 5 GB.
- D. Usar variáveis de ambiente.

**Q16.** Como reduzir a latência de invocações "quentes" de uma Lambda que cria um cliente do SDK a cada chamada?
- A. Criar o cliente dentro do handler.
- B. Inicializar o cliente fora do handler para reutilizar entre invocações.
- C. Usar um novo cliente por requisição.
- D. Reduzir a memória.

**Q17.** Qual modo de retry do AWS SDK ajusta dinamicamente a taxa de requisições do cliente conforme os erros de *throttling*?
- A. `legacy`
- B. `standard`
- C. `adaptive`
- D. `none`

**Q18.** Uma operação `list-objects-v2` em um bucket com milhões de objetos retorna apenas parte dos resultados. Como obter todos?
- A. Aumentar o timeout do cliente.
- B. Chamar uma única vez com `--max-items` muito alto.
- C. Usar um bucket diferente.
- D. Usar paginação com o token de continuação (ou o *paginator* do SDK).

**Q19.** Em uma integração **Lambda proxy** no API Gateway REST, selecione DUAS afirmações verdadeiras.
- A. A função deve retornar um objeto com `statusCode` e `body` (e `headers` quando necessário).
- B. Os headers CORS da resposta real devem ser retornados pela própria função.
- C. O API Gateway aplica *mapping templates* VTL ao corpo por padrão.
- D. A função não recebe o corpo da requisição.
- E. A resposta pode ser uma string simples.

**Q20.** Uma interface de chat precisa exibir a resposta do modelo à medida que é gerada, reduzindo a latência percebida. Qual API do Bedrock usar?
- A. `ConverseStream`
- B. `ApplyGuardrail`
- C. `ListFoundationModels`
- D. `GetFoundationModel`

---

## Domínio 2 — Security

**Q21.** Visitantes não autenticados precisam ler arquivos públicos de um bucket S3 com credenciais temporárias. O que configurar?
- A. Chaves de longo prazo no app.
- B. Acesso de convidado (*unauthenticated identities*) no Cognito Identity Pool com role de permissões restritas.
- C. Bucket com ACL pública de escrita.
- D. Um usuário IAM compartilhado.

**Q22.** Funcionários devem acessar o console usando o login corporativo existente (IdP SAML 2.0). O que usar?
- A. Criar usuários IAM para todos.
- B. Compartilhar a senha do root.
- C. Federação SAML com roles IAM (por exemplo, via IAM Identity Center).
- D. Chaves de acesso por pessoa.

**Q23.** Um desenvolvedor quer usar a AWS CLI com credenciais de curta duração obtidas pelo login SSO da empresa. Qual comando inicia a autenticação?
- A. `aws configure set`
- B. `aws sts get-caller-identity`
- C. `aws iam create-access-key`
- D. `aws sso login --profile <perfil>`

**Q24.** Chamadas assinadas com SigV4 falham com `RequestTimeTooSkewed`. Qual é a causa?
- A. Relógio do cliente muito diferente do da AWS; sincronizar com NTP.
- B. Chave KMS desabilitada.
- C. Falta de permissão IAM.
- D. Bucket inexistente.

**Q25.** Um desenvolvedor definiu `AWS_ACCESS_KEY_ID`/`AWS_SECRET_ACCESS_KEY` no ambiente e também tem um perfil configurado. Qual credencial o SDK/CLI usa primeiro?
- A. O perfil `default`.
- B. A role da instância (IMDS).
- C. As variáveis de ambiente.
- D. O arquivo `config` sempre.

**Q26.** Um pipeline cria funções Lambda associando uma role de execução existente e recebe `AccessDenied` em `iam:PassRole`. O que corrigir?
- A. Conceder `iam:PassRole` sobre a role específica ao principal que cria a função.
- B. Aumentar o timeout.
- C. Adicionar `lambda:InvokeFunction`.
- D. Habilitar MFA.

**Q27.** O serviço Lambda não consegue assumir a role de execução. Onde está o problema mais provável?
- A. Na *permissions policy* da role.
- B. Na *trust policy* da role, que deve permitir o principal `lambda.amazonaws.com`.
- C. Na política do bucket.
- D. Nas variáveis de ambiente.

**Q28.** Uma chamada de `Decrypt` do KMS falha com `InvalidCiphertextException` mesmo com a chave correta, e o dado foi criptografado com *encryption context*. Qual a causa provável?
- A. O contexto de criptografia na decriptação difere do usado na criptografia.
- B. O dado tem mais de 4 KB.
- C. A chave foi rotacionada.
- D. O usuário não tem MFA.

**Q29.** Uma aplicação multi-Região precisa decriptar na Região B dados criptografados na Região A, sem chamar a Região A. O que usar?
- A. Chaves AWS managed.
- B. Replicar o texto claro.
- C. Chaves KMS *multi-Region*.
- D. SSE-C.

**Q30.** Uma regra de negócio exige que a empresa forneça a chave em cada requisição e que o S3 não a armazene. Qual opção usar?
- A. SSE-S3
- B. SSE-KMS
- C. SSE-C
- D. DSSE-KMS com chave AWS managed

**Q31.** Uma equipe quer auditar cada uso da chave que protege uma tabela DynamoDB e controlar sua política. O que usar?
- A. Chave *AWS owned*.
- B. Chave gerenciada pelo cliente (CMK) no KMS, com eventos no CloudTrail.
- C. Desativar criptografia.
- D. SSE-C.

**Q32.** Parâmetros de configuração seguem a hierarquia `/app/prod/...` e `/app/dev/...`. Como permitir que a role de dev leia apenas os de dev?
- A. Conceder `ssm:*` em `*`.
- B. Permissão `ssm:GetParameter*` restrita ao ARN `parameter/app/dev/*`.
- C. Usar o mesmo parâmetro para ambos.
- D. Colocar tudo em variáveis de ambiente.

**Q33.** A rotação de segredos do Secrets Manager usa uma função Lambda. Quais são as etapas implementadas por essa função?
- A. `start`, `run`, `stop`, `report`
- B. `create`, `update`, `delete`, `list`
- C. `createSecret`, `setSecret`, `testSecret`, `finishSecret`
- D. `encrypt`, `decrypt`, `sign`, `verify`

**Q34.** Como proteger uma API do API Gateway contra injeção de SQL e *cross-site scripting*?
- A. Associar um AWS WAF *web ACL* com regras gerenciadas.
- B. Usar Security Groups.
- C. Habilitar CloudTrail.
- D. Usar NACLs.

**Q35.** Uma aplicação de IA deve mascarar PII em respostas e proteger o conteúdo dos logs de invocação. Selecione DUAS ações.
- A. Configurar *sensitive information filters* em um Bedrock Guardrail.
- B. Criptografar com KMS e restringir o acesso ao destino dos logs de invocação.
- C. Armazenar prompts e respostas em um bucket público.
- D. Desativar o IAM para o Bedrock.
- E. Registrar segredos em texto claro para depuração.

**Q36.** Qual afirmação está correta sobre os dados enviados ao Amazon Bedrock?
- A. Entradas e saídas são usadas para treinar os modelos base de outros clientes.
- B. Entradas e saídas não são usadas para treinar os modelos base.
- C. Os dados sempre trafegam pela internet pública.
- D. Não é possível usar VPC endpoints.

**Q37.** Um agente precisa chamar uma API de terceiros em nome do usuário usando OAuth. Qual componente do Bedrock AgentCore trata a identidade e as credenciais?
- A. AgentCore Memory
- B. AgentCore Identity
- C. AgentCore Browser
- D. AgentCore Evaluations

---

## Domínio 3 — Testing and Deployment

**Q38.** Como o CodePipeline pode obter o código-fonte de um repositório GitHub?
- A. Via AWS CodeConnections (conexão com o provedor).
- B. Copiando arquivos manualmente para o S3 a cada commit.
- C. Via VPN.
- D. Pelo Parameter Store.

**Q39.** Os builds do CodeBuild baixam as mesmas dependências a cada execução. Como acelerar?
- A. Aumentar o timeout.
- B. Remover a fase `install`.
- C. Habilitar cache (S3 ou local) para diretórios de dependências.
- D. Usar tag `latest`.

**Q40.** Em um deploy de Lambda com CodeDeploy, onde executar um teste de validação antes de o tráfego ser deslocado para a nova versão?
- A. Hook `ApplicationStart`
- B. Hook `BeforeAllowTraffic`
- C. Hook `AfterInstall`
- D. Hook `ApplicationStop`

**Q41.** Qual é a ordem correta dos hooks de ciclo de vida do CodeDeploy em um deploy *in-place* para EC2?
- A. BeforeInstall → ApplicationStop → AfterInstall → ValidateService → ApplicationStart
- B. ApplicationStart → ApplicationStop → BeforeInstall → AfterInstall → ValidateService
- C. ApplicationStop → BeforeInstall → AfterInstall → ApplicationStart → ValidateService
- D. ValidateService → ApplicationStop → BeforeInstall → AfterInstall → ApplicationStart

**Q42.** O mesmo template CloudFormation deve criar um recurso extra apenas em produção. Que seção usar?
- A. `Mappings` sozinha.
- B. `Outputs`.
- C. `Metadata`.
- D. `Conditions` (com `Condition` no recurso).

**Q43.** O CloudFormation deve aguardar o script de inicialização de uma instância EC2 sinalizar sucesso antes de marcar o recurso como criado. O que usar?
- A. `CreationPolicy` com `cfn-signal`.
- B. `DeletionPolicy`.
- C. `UpdatePolicy` apenas.
- D. `Outputs`.

**Q44.** Qual valor de `Transform` identifica um template AWS SAM?
- A. `AWS::Include`
- B. `AWS::LanguageExtensions`
- C. `AWS::Serverless-2016-10-31`
- D. `AWS::SecretsManager`

**Q45.** No AWS CDK, o que são *constructs* de nível L2?
- A. Abstrações de recurso com padrões e métodos auxiliares (por exemplo, `s3.Bucket`).
- B. Mapeamentos 1:1 do CloudFormation (`CfnBucket`).
- C. Apenas comandos da CLI.
- D. Arquivos de bootstrap.

**Q46.** Qual afirmação sobre versões e aliases de Lambda está correta?
- A. `$LATEST` é imutável.
- B. Versões publicadas são imutáveis, e um alias aponta para uma versão.
- C. Aliases não podem ter roteamento ponderado.
- D. Cada alias recebe uma nova função.

**Q47.** Como liberar uma nova versão de uma API REST para 10% do tráfego em um stage?
- A. Criar outro stage obrigatoriamente.
- B. Habilitar cache.
- C. Usar variáveis de ambiente.
- D. Configurar um *canary release* no stage.

**Q48.** Em um serviço ECS com *rolling update*, como manter 100% da capacidade saudável durante o deploy?
- A. `minimumHealthyPercent` = 100 e `maximumPercent` = 200.
- B. `minimumHealthyPercent` = 0 e `maximumPercent` = 100.
- C. `desiredCount` = 0.
- D. Parar o serviço antes do deploy.

**Q49.** Em um cluster EKS, como reverter um Deployment do Kubernetes à revisão anterior?
- A. `kubectl delete cluster`
- B. `kubectl rollout undo deployment/<nome>`
- C. `kubectl get pods`
- D. `eksctl delete nodegroup`

**Q50.** Como impedir que uma tag de imagem já publicada no ECR (por exemplo, `1.4.2`) seja sobrescrita?
- A. Habilitar *image scanning*.
- B. Habilitar replicação.
- C. Criar uma lifecycle policy.
- D. Habilitar a imutabilidade de tags (*tag immutability*) no repositório.

**Q51.** Para manter ambientes `dev`, `test` e `prod` de uma API no API Gateway, selecione DUAS práticas.
- A. Usar *stages* distintos para cada ambiente.
- B. Usar *stage variables* para apontar para recursos específicos (por exemplo, aliases Lambda).
- C. Editar a API de produção diretamente para testar.
- D. Compartilhar a mesma chave de API entre todos.
- E. Desabilitar logs.

---

## Domínio 4 — Troubleshooting and Optimization

**Q52.** Qual consulta do CloudWatch Logs Insights lista os 5 erros mais frequentes?
- A. `fields @timestamp | limit 5`
- B. `filter @message like /ERROR/ | stats count(*) as total by @message | sort total desc | limit 5`
- C. `stats avg(@duration)`
- D. `sort @timestamp asc`

**Q53.** No mapa de serviços do X-Ray, um nó downstream aparece em vermelho com muitos erros 5xx. O que isso indica?
- A. Problema no DNS do cliente.
- B. O serviço downstream representado está retornando falhas, ajudando a localizar a origem.
- C. O alarme de custo disparou.
- D. A sampling rule está desligada.

**Q54.** Para registrar no CloudTrail as chamadas `GetObject` em um bucket S3, qual tipo de evento deve ser habilitado?
- A. Eventos de gerenciamento (*management events*).
- B. CloudTrail Insights apenas.
- C. Eventos de dados (*data events*) para o S3.
- D. Eventos de configuração do AWS Config.

**Q55.** Usuários recebem `504 Gateway Timeout` do ALB, e os logs indicam que o backend demora mais que o *idle timeout* do balanceador. Qual solução é adequada?
- A. Remover o ALB.
- B. Trocar o certificado.
- C. Reduzir o número de alvos.
- D. Otimizar o backend e/ou ajustar o *idle timeout* do ALB para acomodar o tempo de resposta.

**Q56.** Uma tabela DynamoDB apresenta `ThrottledRequests` apesar de capacidade total sobrando. A chave de partição é a data do dia. Selecione DUAS correções.
- A. Usar uma chave de partição de alta cardinalidade.
- B. Aplicar *write sharding* (sufixo aleatório/calculado na chave) para distribuir a carga.
- C. Aumentar apenas as RCUs.
- D. Trocar para `Scan` paralelo.
- E. Habilitar o DynamoDB Streams.

**Q57.** Uma função Lambda Python executa bem em arm64. Qual mudança costuma reduzir o custo mantendo ou melhorando o desempenho?
- A. Migrar a arquitetura para arm64 (Graviton).
- B. Aumentar o timeout.
- C. Remover as layers.
- D. Usar `/tmp` maior.

**Q58.** Como ser alertado quando mensagens chegam a uma DLQ do SQS?
- A. Alarme do CloudWatch na métrica `ApproximateNumberOfMessagesVisible` da DLQ.
- B. Alarme de custo.
- C. Habilitar X-Ray.
- D. Habilitar Config.

**Q59.** Entregas de uma assinatura SNS para um endpoint HTTP às vezes falham. Como preservar as mensagens que não puderam ser entregues?
- A. Aumentar a retenção do tópico.
- B. Trocar o protocolo para e-mail.
- C. Configurar uma DLQ (SQS) na assinatura.
- D. Criar mais tópicos.

**Q60.** Um alarme do CloudWatch está no estado `INSUFFICIENT_DATA`. O que isso significa?
- A. A métrica ultrapassou o limite.
- B. A métrica está dentro do limite.
- C. O alarme foi excluído.
- D. Não há dados suficientes para avaliar o alarme (por exemplo, métrica ainda sem pontos).

**Q61.** Como ser avisado antes de atingir cotas de serviço (por exemplo, de concorrência) em produção?
- A. Aguardar erros de *throttling*.
- B. Usar o Service Quotas com alarmes do CloudWatch sobre o uso das cotas.
- C. Excluir recursos antigos.
- D. Aumentar o timeout.

**Q62.** Usuários globais acessam uma API REST em uma única Região com alta latência. Selecione DUAS ações para reduzir a latência.
- A. Colocar o Amazon CloudFront na frente da API, com política de cache adequada para respostas cacheáveis.
- B. Usar o tipo de endpoint *edge-optimized* para a API.
- C. Aumentar a memória da Lambda de backend para 128 MB.
- D. Trocar para `Scan` no DynamoDB.
- E. Aumentar o timeout.

**Q63.** Como detectar automaticamente comportamento anormal de uma métrica sem definir limites fixos?
- A. Alarme com limite estático.
- B. Dashboard simples.
- C. CloudWatch *anomaly detection*.
- D. Metric filter.

**Q64.** Uma tarefa ECS está com falha de *health check* do contêiner. O que o ECS faz?
- A. Ignora a falha.
- B. Aumenta o `desiredCount`.
- C. Marca o contêiner como não saudável e o serviço substitui a tarefa.
- D. Exclui o cluster.

**Q65.** Qual prática é adequada ao usar uma ferramenta de IA para analisar um erro de produção?
- A. Colar variáveis de ambiente com segredos no prompt.
- B. Aceitar e aplicar a correção sugerida diretamente em produção.
- C. Enviar dumps completos com PII.
- D. Remover segredos/PII do contexto e validar a sugestão em um ambiente de teste antes de aplicar.

---
---

# ✅ GABARITO — Simulado 3

| Q | Resp. | Skill | Explicação |
|---|---|---|---|
| 1 | **B** | 1.1.3 | `Retry` com backoff é nativo no Step Functions. |
| 2 | **D** | 1.1.8 | Express: alto volume, curta duração, *at-least-once*. |
| 3 | **B** | 1.1.8 | EventBridge `cron`. |
| 4 | **C** | 1.1.8 | EventBridge Pipes liga origem → enriquecimento → destino. |
| 5 | **B** | 1.1.8 | S3 → SQS → Lambda dá durabilidade e controle de taxa. |
| 6 | **C** | 1.1.5 | Acima de 5 GB o *multipart* é obrigatório. |
| 7 | **B** | 1.1.5 | Byte-range fetch. |
| 8 | **C** | 1.1.7 | Parquet + partições reduzem dados varridos. |
| 9 | **A** | 1.3.2 | OpenSearch para busca full-text. |
| 10 | **C** | 1.3.3 | Redis/Valkey: estruturas ricas, persistência, replicação. |
| 11 | **B** | 1.3.3 | *Write-through*. |
| 12 | **D** | 1.2.4 | *Filter criteria* no event source mapping. |
| 13 | **A, B** | 1.2.3 | Bisect + destino de falha/limites de retry. |
| 14 | **D** | 3.3.1 | Imagem de contêiner (até 10 GB). |
| 15 | **A** | 1.2.2 | `/tmp` configurável até 10 GB. |
| 16 | **B** | 1.2.2 | Inicializar fora do handler. |
| 17 | **C** | 1.1.3 | Modo `adaptive`. |
| 18 | **D** | 1.1.5 | Paginação. |
| 19 | **A, B** | 1.1.4 | Proxy: formato de resposta e CORS na função. |
| 20 | **A** | 1.1.10 | `ConverseStream`. |
| 21 | **B** | 2.1.1 | Identidades não autenticadas do Identity Pool. |
| 22 | **C** | 2.1.1 | Federação SAML/Identity Center. |
| 23 | **D** | 2.1.3 | `aws sso login`. |
| 24 | **A** | 2.1.5 | Relógio dessincronizado. |
| 25 | **C** | 2.1.3 | Variáveis de ambiente vêm antes do perfil. |
| 26 | **A** | 2.1.6 | `iam:PassRole`. |
| 27 | **B** | 2.1.6 | Trust policy precisa do principal do serviço. |
| 28 | **A** | 2.2.4 | Contexto de criptografia deve ser idêntico. |
| 29 | **C** | 2.2.4 | Chaves *multi-Region*. |
| 30 | **C** | 2.2.3 | SSE-C. |
| 31 | **B** | 2.2.4 | CMK permite política própria e auditoria via CloudTrail. |
| 32 | **B** | 2.2.7 | Restrição por caminho do parâmetro. |
| 33 | **C** | 2.2.7 | Quatro etapas da função de rotação. |
| 34 | **A** | 2.2.1 | AWS WAF. |
| 35 | **A, B** | 2.3.3 / 2.3.5 | Guardrails para PII; logs criptografados e restritos. |
| 36 | **B** | 2.3.2 | Entradas/saídas não treinam os modelos base. |
| 37 | **B** | 2.3.4 | AgentCore Identity. |
| 38 | **A** | 3.1.3 | CodeConnections. |
| 39 | **C** | 3.3.5 | Cache do CodeBuild. |
| 40 | **B** | 3.3.4 | `BeforeAllowTraffic`. |
| 41 | **C** | 3.3.4 | ApplicationStop → BeforeInstall → AfterInstall → ApplicationStart → ValidateService. |
| 42 | **D** | 3.3.3 | `Conditions`. |
| 43 | **A** | 3.3.3 | `CreationPolicy` + `cfn-signal`. |
| 44 | **C** | 3.3.3 | `AWS::Serverless-2016-10-31`. |
| 45 | **A** | 3.3.3 | L2 = abstração de alto nível. |
| 46 | **B** | 3.2.4 | Versões imutáveis; alias aponta para versão. |
| 47 | **D** | 3.1.5 | Canary release no stage. |
| 48 | **A** | 3.3.2 | 100% mínimo, 200% máximo. |
| 49 | **B** | 3.3.2 | `kubectl rollout undo`. |
| 50 | **D** | 3.1.2 | Tag immutability. |
| 51 | **A, B** | 3.2.4 | Stages e stage variables. |
| 52 | **B** | 4.1.3 | `stats count(*) ... sort desc | limit 5`. |
| 53 | **B** | 4.1.2 | Service map mostra o serviço com falhas. |
| 54 | **C** | 4.1.2 | S3 object-level exige *data events*. |
| 55 | **D** | 4.1.1 | 504 do ALB = backend lento / idle timeout. |
| 56 | **A, B** | 4.3.5 | Hot partition: alta cardinalidade e *write sharding*. |
| 57 | **A** | 4.3.2 | arm64 (Graviton) melhora preço/desempenho. |
| 58 | **A** | 4.2.3 | Alarme na DLQ. |
| 59 | **C** | 4.3.3 | DLQ na assinatura SNS. |
| 60 | **D** | 4.2.3 | `INSUFFICIENT_DATA`. |
| 61 | **B** | 4.2.3 | Service Quotas + alarmes de uso. |
| 62 | **A, B** | 4.3.4 | CloudFront e endpoint edge-optimized reduzem a latência global. |
| 63 | **C** | 4.1.2 | Anomaly detection. |
| 64 | **C** | 4.2.5 | Health check falha → tarefa substituída. |
| 65 | **D** | 4.1.5 | Higienizar o contexto e validar antes de aplicar. |

## Contagem
59 questões de escolha única e 6 de múltipla resposta (Q13, Q19, Q35, Q51, Q56 e Q62).

## Desempenho por domínio (preencha)
| Domínio | Questões | Acertos | % |
|---|---|---|---|
| D1 Development | Q1–Q20 | | |
| D2 Security | Q21–Q37 | | |
| D3 Testing and Deployment | Q38–Q51 | | |
| D4 Troubleshooting and Optimization | Q52–Q65 | | |
