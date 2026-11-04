---
tags: [aws, certificacao, developer-associate, dva-c03, simulado]
exame: DVA-C03
simulado: 1
data: 2026-11-04
questoes: 65
---

# 📝 Simulado 1 — AWS Certified Developer – Associate (DVA-C03)

**Data de elaboração:** 04/11/2026 · **Tempo sugerido:** 130 min · **Questões:** 65 · **Aprovação (referência):** ≥ 72% (nota 720/1000 é escalonada; use ~47 acertos como meta)

> **Instruções:** questões originais no estilo da prova (escolha única, ou múltipla resposta quando indicado "Selecione DUAS"). Responda tudo antes de abrir o **Gabarito** no final. Aqui as questões vêm agrupadas por domínio (D1→D4) para facilitar o estudo; na prova real elas vêm misturadas.
> Conteúdo baseado em [[DVA-C03 - Glossario]]. Registre seus erros e use o prompt de revisão em [[DVA-C03 - Prompts de Questoes]].

---

## Domínio 1 — Development with AWS Services

**Q1.** Uma função Lambda é acionada por uma fila Amazon SQS com lotes de 10 mensagens. Quando uma única mensagem do lote causa exceção, todas as 10 mensagens voltam à fila e são reprocessadas, gerando efeitos duplicados. Qual solução resolve com o MENOR esforço?
- A. Reduzir o tamanho do lote para 1 e remover a fila DLQ.
- B. Aumentar o timeout da função para 15 minutos.
- C. Habilitar `ReportBatchItemFailures` no event source mapping e retornar apenas os IDs das mensagens que falharam.
- D. Trocar a fila Standard por uma fila FIFO.

**Q2.** Um serviço de pedidos chama de forma síncrona um serviço de estoque. Em picos, o serviço de estoque fica lento e os pedidos falham. O desenvolvedor quer absorver os picos e manter o serviço de pedidos disponível, com a MENOR mudança de código. O que usar?
- A. Aumentar o timeout do cliente HTTP do serviço de pedidos.
- B. Publicar os pedidos em uma fila Amazon SQS e fazer o serviço de estoque consumir da fila.
- C. Publicar em um tópico Amazon SNS e fazer o estoque consultar o tópico periodicamente.
- D. Colocar um Application Load Balancer na frente do serviço de estoque.

**Q3.** Uma aplicação recebe esporadicamente `ProvisionedThroughputExceededException` ao gravar no Amazon DynamoDB durante picos curtos. Qual é a prática recomendada no código?
- A. Repetir a requisição com backoff exponencial e jitter.
- B. Repetir imediatamente em um loop até obter sucesso.
- C. Trocar todas as gravações por `Scan`.
- D. Desabilitar o retry do SDK para evitar sobrecarga.

**Q4.** Uma API REST do Amazon API Gateway invoca uma Lambda que leva cerca de 45 segundos para processar. Os clientes recebem erro 504. Qual mudança de arquitetura é a MAIS adequada?
- A. Aumentar a memória da função para 10 GB.
- B. Habilitar cache de 3.600 s no stage.
- C. Retornar `202 Accepted` imediatamente e processar o trabalho de forma assíncrona (por exemplo, via SQS ou Step Functions), expondo um endpoint de consulta de status.
- D. Trocar a integração para MOCK.

**Q5.** Um stream do Amazon Kinesis Data Streams recebe eventos de sensores usando o tipo do sensor (3 valores possíveis) como *partition key*. Um shard recebe quase todo o tráfego e há `ProvisionedThroughputExceededException`. O que fazer?
- A. Aumentar a retenção do stream para 7 dias.
- B. Usar uma *partition key* de alta cardinalidade, como o ID do dispositivo.
- C. Trocar para o Amazon SQS Standard.
- D. Registrar um consumidor com *enhanced fan-out*.

**Q6.** Uma tabela DynamoDB em modo provisionado recebe 100 leituras **eventualmente consistentes** por segundo de itens com 9 KB. Quantas RCUs são necessárias?
- A. 150
- B. 300
- C. 225
- D. 450

**Q7.** Uma aplicação grava 50 itens de 2,5 KB por segundo em uma tabela DynamoDB provisionada (gravações padrão, não transacionais). Quantas WCUs são necessárias?
- A. 63
- B. 125
- C. 150
- D. 300

**Q8.** Uma tabela DynamoDB tem `orderId` como chave de partição. A aplicação precisa listar frequentemente todos os pedidos de um `customerId`, e hoje faz `Scan` com filtro, que é lento e caro. Qual solução é a MAIS eficiente?
- A. Aumentar a capacidade de leitura da tabela.
- B. Criar um índice secundário global (GSI) com `customerId` como chave de partição e consultar com `Query`.
- C. Criar um índice secundário local (LSI) com `customerId` na tabela existente.
- D. Habilitar o DynamoDB Streams.

**Q9.** Dois usuários podem atualizar o mesmo item DynamoDB simultaneamente e a última gravação sobrescreve a anterior sem aviso. Como evitar a perda de atualizações?
- A. Usar `Scan` antes de cada gravação.
- B. Habilitar leituras fortemente consistentes.
- C. Usar bloqueio otimista: atributo de versão com `ConditionExpression` que valida a versão lida.
- D. Aumentar as WCUs da tabela.

**Q10.** Uma função Lambda em subnets privadas de uma VPC precisa chamar uma API pública de terceiros e também acessar o Amazon DynamoDB sem tráfego pela internet pública e com o MENOR custo. Selecione DUAS ações.
- A. Criar um NAT gateway em uma subnet pública e adicionar rota `0.0.0.0/0` na route table das subnets privadas.
- B. Criar um VPC endpoint do tipo *gateway* para o DynamoDB e associá-lo às route tables das subnets privadas.
- C. Colocar a Lambda em uma subnet pública com IP público.
- D. Criar um VPC endpoint do tipo *interface* para a API de terceiros.
- E. Anexar um Internet Gateway às subnets privadas.

**Q11.** Uma função Lambda em Java tem *cold starts* de vários segundos e afeta a latência. Qual abordagem reduz o *cold start* SEM pagar por instâncias pré-aquecidas permanentemente?
- A. Aumentar o timeout para 15 minutos.
- B. Habilitar o Lambda SnapStart.
- C. Configurar *reserved concurrency* igual a 1.
- D. Adicionar mais camadas (layers) à função.

**Q12.** Uma função Lambda invocada de forma assíncrona falha após as tentativas automáticas. A equipe quer enviar o evento original **e o contexto do erro** a uma fila SQS. Qual recurso usar?
- A. Uma *dead-letter queue* da função apontando para SQS (somente o evento).
- B. Um *destination* de falha (on-failure) apontando para a fila SQS.
- C. Um alarme do CloudWatch em `Errors`.
- D. Uma regra do EventBridge em `Invocations`.

**Q13.** Um tópico Amazon SNS publica eventos de pagamento com o atributo de mensagem `type`. Uma fila SQS deve receber apenas mensagens com `type = "refund"`. Qual é a solução com o MENOR esforço operacional?
- A. Fazer o consumidor da fila descartar mensagens que não sejam `refund`.
- B. Configurar uma *filter policy* na assinatura SNS da fila.
- C. Criar um tópico SNS por tipo de evento.
- D. Usar uma Lambda intermediária para filtrar.

**Q14.** Eventos de um parceiro SaaS chegam a um *partner event bus* do Amazon EventBridge. É preciso rotear eventos com `detail.status = "FAILED"` para uma Lambda e os demais para uma fila SQS. O que configurar?
- A. Duas regras no barramento, cada uma com um *event pattern* apropriado e seu alvo.
- B. Uma regra com *schedule expression*.
- C. Uma assinatura SNS com filtro.
- D. Um stream do Kinesis com duas partition keys.

**Q15.** Um fluxo de aprovação deve pausar por horas até que um gerente aprove em um sistema externo, sem manter recursos de computação ocupados. Qual solução é adequada?
- A. Um loop com `sleep` em uma Lambda.
- B. Um Step Functions *Standard* com um estado `Task` usando o padrão `.waitForTaskToken`.
- C. Um Step Functions *Express* com estado `Wait` de 6 horas.
- D. Uma fila SQS com *visibility timeout* de 12 horas e polling contínuo.

**Q16.** Mensagens de um mesmo cliente precisam ser processadas na ordem em que foram enviadas, mas clientes diferentes podem ser processados em paralelo. Qual configuração atende?
- A. Fila SQS Standard com *long polling*.
- B. Fila SQS FIFO usando o ID do cliente como `MessageGroupId`.
- C. Fila SQS FIFO com um único `MessageGroupId` fixo para todas as mensagens.
- D. Tópico SNS Standard com uma assinatura por cliente.

**Q17.** Uma aplicação usa *lazy loading* com Amazon ElastiCache e usuários às vezes veem dados desatualizados após alterações no banco. Qual mudança limita o tempo de dado velho com o MENOR esforço?
- A. Adicionar um TTL às chaves do cache.
- B. Trocar o Redis por Memcached.
- C. Aumentar o tamanho do nó.
- D. Desativar o cache.

**Q18.** Arquivos em um bucket S3 são muito acessados por 30 dias, depois raramente, mas precisam permanecer disponíveis em milissegundos por 1 ano e depois ser removidos. Qual regra de *lifecycle* atende com o MENOR custo?
- A. Transição para S3 Glacier Deep Archive aos 30 dias e expiração aos 365 dias.
- B. Transição para S3 Standard-IA aos 30 dias e expiração aos 365 dias.
- C. Manter em S3 Standard e expirar aos 365 dias.
- D. Transição para S3 One Zone-IA aos 1 dia e expiração aos 30 dias.

**Q19.** Uma equipe precisa de um serviço de streaming onde **vários consumidores independentes** possam reler eventos das últimas 72 horas. Selecione DUAS ações.
- A. Usar o Amazon Kinesis Data Streams.
- B. Configurar o período de retenção do stream para 72 horas ou mais.
- C. Usar o Amazon Data Firehose com buffer de 60 segundos.
- D. Usar uma fila SQS Standard.
- E. Usar um tópico SNS Standard.

**Q20.** Uma aplicação precisa trocar de modelo de IA no Amazon Bedrock sem reescrever o formato das requisições e do histórico de mensagens para cada provedor. Qual API usar?
- A. `InvokeModel` com o corpo específico de cada modelo.
- B. A API `Converse`.
- C. `ApplyGuardrail`.
- D. `InvokeAgent`.

---

## Domínio 2 — Security

**Q21.** Um aplicativo móvel deve permitir que usuários autenticados enviem fotos diretamente ao S3 usando **credenciais temporárias da AWS** com escopo por usuário. O que usar?
- A. Cognito User Pool apenas.
- B. Cognito Identity Pool (identidades federadas) com uma role IAM apropriada.
- C. Uma chave de acesso de longo prazo embutida no app.
- D. Um bucket com escrita pública.

**Q22.** Uma API REST do API Gateway deve aceitar apenas requisições com JWT válido emitido por um Cognito User Pool, com o MENOR código. O que configurar?
- A. Um Lambda authorizer que valide o token manualmente.
- B. Um *Cognito user pool authorizer* no método.
- C. Autorização IAM (SigV4) em todos os métodos.
- D. Uma chave de API em cada requisição.

**Q23.** Uma função Lambda na conta A precisa ler objetos de um bucket S3 na conta B. Selecione DUAS ações.
- A. Adicionar uma *bucket policy* na conta B permitindo `s3:GetObject` à role da função da conta A.
- B. Conceder `s3:GetObject` na *execution role* da função na conta A para o bucket da conta B.
- C. Compartilhar a chave de acesso do root da conta B.
- D. Tornar o bucket público.
- E. Criar um usuário IAM na conta A com a senha da conta B.

**Q24.** Uma aplicação precisa criptografar um arquivo de 500 MB usando uma chave do AWS KMS. Qual abordagem usar?
- A. Chamar `Encrypt` do KMS enviando o arquivo inteiro.
- B. Chamar `GenerateDataKey`, criptografar o arquivo localmente com a chave de dados e guardar a chave de dados criptografada junto ao arquivo.
- C. Usar `CreateGrant` para cada bloco do arquivo.
- D. Dividir o arquivo em partes de 4 KB e chamar `Encrypt` para cada parte.

**Q25.** A senha de um banco Amazon RDS deve ser rotacionada automaticamente a cada 30 dias sem alterações de código além da leitura do segredo. Qual serviço usar?
- A. AWS Systems Manager Parameter Store (Standard).
- B. AWS Secrets Manager com rotação habilitada.
- C. Variáveis de ambiente criptografadas da Lambda.
- D. Um arquivo de configuração no S3.

**Q26.** Uma função Lambda lê um parâmetro `SecureString` do Parameter Store criptografado com uma chave gerenciada pelo cliente (CMK). Quais permissões a *execution role* precisa?
- A. `ssm:GetParameter` e `kms:Decrypt` na CMK.
- B. Apenas `ssm:GetParameter`.
- C. `kms:Encrypt` e `kms:GenerateDataKey`.
- D. `secretsmanager:GetSecretValue`.

**Q27.** Um cliente externo, sem conta AWS, precisa baixar um relatório privado do S3 durante 10 minutos. Qual a abordagem MAIS segura?
- A. Tornar o objeto público por 10 minutos.
- B. Gerar uma *presigned URL* com expiração de 10 minutos.
- C. Criar um usuário IAM para o cliente.
- D. Enviar a chave de acesso do desenvolvedor.

**Q28.** Como garantir que todas as requisições a um bucket S3 usem TLS?
- A. Habilitar versionamento.
- B. Adicionar uma *bucket policy* com `Deny` quando `aws:SecureTransport` for `false`.
- C. Habilitar SSE-KMS.
- D. Habilitar S3 Transfer Acceleration.

**Q29.** Uma role tem política de identidade que permite `s3:*` no bucket `dados`, e a *bucket policy* contém um `Deny` explícito para essa role em `s3:DeleteObject`. Qual é o resultado de uma chamada `DeleteObject` feita pela role?
- A. Permitida, pois a política de identidade concede `s3:*`.
- B. Negada, pois um `Deny` explícito sempre prevalece.
- C. Permitida, pois políticas de recurso têm prioridade menor.
- D. Depende da ordem em que as políticas foram criadas.

**Q30.** Um fornecedor terceirizado precisa assumir uma role IAM na conta do cliente. Qual recurso previne o problema do *confused deputy*?
- A. `ExternalId` na trust policy e na chamada `AssumeRole`.
- B. Aumentar a duração da sessão para 12 horas.
- C. Usar `GetSessionToken`.
- D. Habilitar MFA no usuário root.

**Q31.** Um certificado público ACM será usado em uma distribuição do Amazon CloudFront. Em qual Região o certificado deve ser solicitado?
- A. Na Região mais próxima dos usuários.
- B. us-east-1
- C. Em qualquer Região, pois o ACM é global.
- D. Na mesma Região do bucket de origem.

**Q32.** Uma função Lambda usa uma senha de banco em uma variável de ambiente em texto claro. Qual é a melhor prática?
- A. Manter a variável, pois ela já é criptografada em repouso.
- B. Armazenar o segredo no Secrets Manager e buscá-lo na inicialização, com cache.
- C. Codificar o valor em Base64 no código.
- D. Guardar o segredo em um bucket S3 público.

**Q33.** Um chatbot construído sobre Amazon Bedrock deve bloquear tentativas de *prompt injection* e se recusar a responder sobre aconselhamento de investimentos. Selecione DUAS configurações.
- A. Filtro de ataque a prompts (*prompt attack*) em um Bedrock Guardrail.
- B. *Denied topics* em um Bedrock Guardrail.
- C. Um VPC endpoint para o Bedrock Runtime.
- D. Habilitar CloudTrail data events.
- E. Aumentar o número máximo de tokens.

**Q34.** Um agente de IA pode executar a ação "excluir registros de clientes". Qual controle reduz o risco de exclusões indevidas?
- A. Conceder ao agente permissões administrativas.
- B. Exigir aprovação humana (*human-in-the-loop*) antes de ações sensíveis, além de permissão mínima por ferramenta.
- C. Aumentar a temperatura do modelo.
- D. Desativar logs.

**Q35.** Uma aplicação em instâncias EC2 precisa acessar o S3 sem armazenar credenciais. O que usar?
- A. Chaves de acesso em variáveis de ambiente.
- B. Uma role IAM associada à instância por meio de um *instance profile*.
- C. Um usuário IAM compartilhado.
- D. Credenciais no arquivo `~/.aws/credentials` na AMI.

**Q36.** Requisito de conformidade: os dados devem ser criptografados na aplicação **antes** de sair para a AWS, de modo que o serviço nunca veja o texto claro. O que usar?
- A. SSE-S3.
- B. Criptografia no cliente (*client-side*), por exemplo com o AWS Encryption SDK.
- C. SSE-KMS.
- D. Apenas HTTPS.

**Q37.** Uma CMK simétrica gerenciada pelo cliente deve ter o material criptográfico rotacionado a cada 180 dias. O que fazer?
- A. Habilitar a rotação automática com `RotationPeriodInDays` = 180.
- B. Chaves gerenciadas pelo cliente só podem ser rotacionadas anualmente.
- C. Excluir a chave a cada 180 dias.
- D. Trocar para uma chave AWS managed.

---

## Domínio 3 — Testing and Deployment

**Q38.** Uma equipe quer liberar uma *feature flag* para produção sem novo deploy e reverter automaticamente se o alarme de erros do CloudWatch disparar. Qual serviço usar?
- A. AWS AppConfig com estratégia de implantação gradual e monitores do CloudWatch.
- B. Parameter Store sem versionamento.
- C. Variáveis de ambiente da Lambda.
- D. Um arquivo JSON no S3.

**Q39.** Um desenvolvedor alterou uma integração no API Gateway REST, mas as chamadas ao stage `prod` ainda se comportam como antes. Qual é a causa mais provável?
- A. Faltou criar um novo *deployment* e associá-lo ao stage.
- B. O cache do navegador.
- C. A API precisa ser recriada.
- D. É necessário reiniciar a Lambda.

**Q40.** Como testar localmente uma função Lambda com um evento de notificação do S3?
- A. `sam local generate-event s3 put` e `sam local invoke` com o evento gerado.
- B. `sam deploy --guided`.
- C. `aws s3 sync`.
- D. `cdk synth`.

**Q41.** Um deploy de Lambda via CodeDeploy deve aumentar o tráfego da nova versão em 10% a cada 3 minutos. Qual configuração usar?
- A. `Canary10Percent5Minutes`
- B. `AllAtOnce`
- C. `Linear10PercentEvery3Minutes`
- D. `HalfAtATime`

**Q42.** Em um deploy EC2/on-premises com CodeDeploy, onde executar um *smoke test* depois que a aplicação já foi iniciada?
- A. Hook `BeforeInstall`
- B. Hook `ApplicationStop`
- C. Hook `ValidateService`
- D. Hook `AfterAllowTraffic`

**Q43.** Em um `buildspec.yml` do CodeBuild, em qual fase deve ficar o `docker push` da imagem recém-construída?
- A. `install`
- B. `pre_build`
- C. `build`
- D. `post_build`

**Q44.** Um pipeline deve exigir aprovação manual antes de implantar em produção e notificar o aprovador por e-mail. O que configurar?
- A. Uma action de aprovação manual no CodePipeline com um tópico SNS.
- B. Um alarme CloudWatch na action de build.
- C. Uma regra do EventBridge para o CodeBuild.
- D. Uma action de teste do CodeBuild.

**Q45.** Ao criar uma stack, o CloudFormation falhou e a stack ficou em `ROLLBACK_COMPLETE`. O que fazer?
- A. Atualizar a stack com um novo template.
- B. Identificar o primeiro evento `CREATE_FAILED`, corrigir a causa, excluir a stack e criá-la novamente.
- C. Executar *continue update rollback*.
- D. Executar `cdk bootstrap`.

**Q46.** Como visualizar o que mudará em uma stack do CloudFormation antes de aplicar um template atualizado?
- A. Drift detection.
- B. Um *change set*.
- C. `DeletionPolicy`.
- D. Um nested stack.

**Q47.** Em um template SAM, como configurar a liberação gradual de uma Lambda com CodeDeploy?
- A. `AutoPublishAlias` + `DeploymentPreference` na função.
- B. `Layers` + `Environment`.
- C. `Events` do tipo `Api`.
- D. `ReservedConcurrentExecutions`.

**Q48.** Uma tarefa do Amazon ECS precisa acessar uma tabela DynamoDB, e o agente precisa puxar a imagem do ECR e gravar logs. Qual combinação está correta?
- A. A *task role* concede o acesso ao DynamoDB; a *task execution role* permite puxar a imagem e gravar logs.
- B. A *task execution role* concede o acesso ao DynamoDB.
- C. Uma única role EC2 para ambos.
- D. A *task role* puxa imagens do ECR.

**Q49.** Um repositório do Amazon ECR acumula imagens antigas sem tag, aumentando o custo. Qual é a solução?
- A. Excluir manualmente todo mês.
- B. Configurar uma *lifecycle policy* que expira imagens sem tag após N dias.
- C. Habilitar replicação entre Regiões.
- D. Habilitar *image scanning*.

**Q50.** No AWS Elastic Beanstalk, qual política de deploy mantém a capacidade total, usa novas instâncias e permite *rollback* rápido encerrando o novo grupo?
- A. All at once
- B. Rolling
- C. Immutable
- D. Rolling com lote adicional

**Q51.** Por que escolher uma função Lambda empacotada como **imagem de container** em vez de .zip? Selecione DUAS razões.
- A. O pacote com bibliotecas de ML tem alguns GB, acima do limite de 250 MB descompactados do .zip.
- B. A equipe já usa Docker e quer reutilizar o mesmo fluxo de build.
- C. Imagens de container removem o *cold start*.
- D. Imagens dispensam permissões IAM.
- E. Imagens permitem executar por mais de 15 minutos.

---

## Domínio 4 — Troubleshooting and Optimization

**Q52.** Qual consulta do CloudWatch Logs Insights calcula o percentil 95 da duração de uma Lambda a partir dos relatórios `REPORT`?
- A. `filter @type = "REPORT" | stats pct(@duration, 95)`
- B. `fields @message | sort @timestamp`
- C. `stats count(*) by @logStream`
- D. `filter @message like /ERROR/`

**Q53.** No AWS X-Ray, como permitir buscar traces de um cliente específico?
- A. Adicionar o ID do cliente como *metadata* do segmento.
- B. Adicionar o ID do cliente como *annotation*.
- C. Criar uma métrica customizada com dimensão `customerId`.
- D. Aumentar a taxa de amostragem para 100%.

**Q54.** Como emitir métricas customizadas de uma Lambda de alto volume SEM fazer chamadas de API `PutMetricData`?
- A. CloudWatch Embedded Metric Format (EMF) nos logs.
- B. Habilitar CloudTrail.
- C. Usar uma regra do EventBridge.
- D. Habilitar X-Ray.

**Q55.** A métrica `Throttles` de uma função crítica sobe porque outras funções consomem a concorrência da conta. O que garante capacidade para a função crítica?
- A. Aumentar a memória.
- B. Configurar *reserved concurrency* para a função crítica.
- C. Reduzir o timeout.
- D. Adicionar uma layer.

**Q56.** Qual ferramenta ajuda a encontrar a configuração de memória com melhor relação custo × desempenho de uma Lambda?
- A. AWS Lambda Power Tuning
- B. AWS CloudTrail
- C. AWS Config
- D. AWS Artifact

**Q57.** Um consumidor SQS faz muitas chamadas `ReceiveMessage` que retornam vazias, gerando custo. Qual ajuste reduz as chamadas vazias?
- A. Reduzir o *visibility timeout*.
- B. Habilitar *long polling* com `WaitTimeSeconds` > 0.
- C. Usar fila FIFO.
- D. Reduzir a retenção.

**Q58.** Uma tabela DynamoDB tem leituras repetitivas de alta taxa e o time quer latência de microssegundos com a MENOR mudança de código. O que usar?
- A. Amazon DynamoDB Accelerator (DAX).
- B. Trocar para RDS.
- C. Adicionar um GSI.
- D. Aumentar as RCUs.

**Q59.** Uma distribuição CloudFront tem baixo *cache hit ratio* porque a política de cache inclui todas as query strings e headers. O que melhora o *hit ratio*?
- A. Incluir na chave de cache apenas os headers/query strings necessários.
- B. Desativar o cache.
- C. Reduzir o TTL para 0.
- D. Invalidar `/*` a cada minuto.

**Q60.** Clientes recebem `429` do API Gateway durante picos. Qual causa e solução?
- A. Backend fora do ar; reiniciar a Lambda.
- B. Limite de *throttling* excedido; ajustar limites do stage/*usage plan* ou solicitar aumento, e usar retry com backoff no cliente.
- C. Certificado expirado; renovar no ACM.
- D. Payload acima de 10 MB; compactar.

**Q61.** Um contêiner leva 60 s para aquecer, mas o balanceador envia tráfego antes de ficar pronto, gerando erros. Qual verificação do Kubernetes resolve?
- A. *Liveness probe* mais agressiva.
- B. *Readiness probe*, que só marca o pod como pronto quando a aplicação responde.
- C. Reduzir réplicas a 1.
- D. Desativar *probes*.

**Q62.** A métrica `IteratorAge` de uma função que lê do Kinesis está crescendo. Selecione DUAS ações para reduzir o atraso.
- A. Aumentar o `ParallelizationFactor` do event source mapping.
- B. Otimizar o código e/ou aumentar a memória da função para reduzir a duração.
- C. Diminuir o número de shards.
- D. Reduzir a retenção do stream.
- E. Desativar o event source mapping.

**Q63.** Quem excluiu uma tabela DynamoDB ontem? Qual serviço responde?
- A. AWS X-Ray
- B. Amazon CloudWatch Logs Insights da aplicação
- C. AWS CloudTrail
- D. Amazon Inspector

**Q64.** Uma Lambda abre muitas conexões a um banco RDS e esgota o limite de conexões em picos. Qual solução reduz o problema?
- A. Aumentar o timeout.
- B. Usar o Amazon RDS Proxy.
- C. Trocar o runtime.
- D. Habilitar Multi-AZ.

**Q65.** Por que adotar logs estruturados (JSON) em uma aplicação Lambda?
- A. Reduz o custo de armazenamento a zero.
- B. Facilita filtrar e agregar campos no CloudWatch Logs Insights.
- C. Substitui o X-Ray.
- D. Elimina a necessidade de métricas.

---
---

# ✅ GABARITO — Simulado 1

| Q | Resp. | Skill | Explicação |
|---|---|---|---|
| 1 | **C** | 1.2.3 | `ReportBatchItemFailures` devolve só as mensagens com falha; as demais são apagadas. |
| 2 | **B** | 1.1.1 | SQS absorve picos e desacopla com pouca mudança. SNS é push, não guarda para polling. |
| 3 | **A** | 1.1.3 | Retry com backoff exponencial + jitter. |
| 4 | **C** | 1.1.2 | O limite de integração é 29 s; padrão assíncrono com 202 + consulta de status. |
| 5 | **B** | 1.1.6 | Chave de baixa cardinalidade cria *hot shard*. |
| 6 | **A** | 1.3.4 | 9 KB → 3 blocos de 4 KB; eventual = ½ RCU por bloco → 3×100÷2 = 150. |
| 7 | **C** | 1.3.4 | 2,5 KB arredonda para 3 WCU × 50 = 150. |
| 8 | **B** | 1.3.4 | GSI + `Query`. LSI só na criação da tabela. |
| 9 | **C** | 1.3.4 | Bloqueio otimista com versão e `ConditionExpression`. |
| 10 | **A, B** | 1.2.1 | NAT para API pública; endpoint *gateway* do DynamoDB é gratuito e privado. |
| 11 | **B** | 1.2.2 | SnapStart reduz *cold start* sem concorrência provisionada contínua. |
| 12 | **B** | 1.2.3 | Destination de falha inclui contexto; DLQ só o evento. |
| 13 | **B** | 4.3.3 / 1.1.8 | *Filter policy* na assinatura. |
| 14 | **A** | 1.1.8 | Regras com *event patterns* distintos. |
| 15 | **B** | 1.1.1 | Standard + `.waitForTaskToken` (até 1 ano). Express dura no máximo 5 min. |
| 16 | **B** | 1.1.8 | FIFO com `MessageGroupId` por cliente = ordem por cliente + paralelismo. |
| 17 | **A** | 1.3.3 | TTL limita a defasagem. |
| 18 | **B** | 1.3.1 | Standard-IA (≥30 d) mantém milissegundos; Deep Archive não. |
| 19 | **A, B** | 1.1.6 | KDS permite replay e múltiplos consumidores; ajustar retenção. |
| 20 | **B** | 1.1.10 | `Converse` padroniza o formato entre modelos. |
| 21 | **B** | 2.1.1 | Identity Pool troca token por credenciais AWS temporárias. |
| 22 | **B** | 2.1.2 | *Cognito authorizer* valida o JWT sem código. |
| 23 | **A, B** | 2.1.6 | Acesso cross-account exige permissão nos dois lados. |
| 24 | **B** | 2.2.4 | Envelope encryption; `Encrypt` aceita só 4 KB. |
| 25 | **B** | 2.2.7 | Secrets Manager faz rotação nativa. |
| 26 | **A** | 2.2.7 | Também precisa de `kms:Decrypt` na CMK. |
| 27 | **B** | 2.1.4 | Presigned URL com expiração. |
| 28 | **B** | 2.2.1 | `Deny` com `aws:SecureTransport = false`. |
| 29 | **B** | 2.1.2 | Deny explícito sempre vence. |
| 30 | **A** | 2.1.7 | `ExternalId` previne *confused deputy*. |
| 31 | **B** | 2.2.2 | Certificados para CloudFront ficam em us-east-1. |
| 32 | **B** | 2.2.7 | Segredos em Secrets Manager, com cache na inicialização. |
| 33 | **A, B** | 2.3.3 | Prompt attack filter e denied topics. |
| 34 | **B** | 2.3.4 | Human-in-the-loop + permissão mínima por ferramenta. |
| 35 | **B** | 1.1.5 / 2.1.3 | Instance profile/role. |
| 36 | **B** | 2.2.3 | Client-side: o serviço nunca vê o texto claro. |
| 37 | **A** | 2.2.4 | Rotação automática aceita período customizado (padrão 365 d). |
| 38 | **A** | 3.1.4 | AppConfig: estratégias graduais e rollback por alarme. |
| 39 | **A** | 3.1.5 | Mudanças só valem após novo *deployment* no stage. |
| 40 | **A** | 3.2.3 | `generate-event` + `local invoke`. |
| 41 | **C** | 3.3.4 | Linear a cada 3 min; Canary faz 2 passos. |
| 42 | **C** | 3.3.4 | `ValidateService` roda após `ApplicationStart`. |
| 43 | **D** | 3.3.5 | Push de imagem na `post_build`. |
| 44 | **A** | 3.3.5 | Aprovação manual + SNS. |
| 45 | **B** | 4.1.4 / 3.3.3 | Stack em `ROLLBACK_COMPLETE` só pode ser excluída e recriada. |
| 46 | **B** | 3.3.3 | Change set mostra a prévia. |
| 47 | **A** | 3.3.3 | `AutoPublishAlias` + `DeploymentPreference`. |
| 48 | **A** | 3.3.2 | Task role (app) vs execution role (ECR/logs). |
| 49 | **B** | 3.1.2 | Lifecycle policy do ECR. |
| 50 | **C** | 3.3.6 | Immutable usa novo ASG; rollback encerra o novo grupo. |
| 51 | **A, B** | 3.1.2 | Pacotes grandes e reuso do Docker. Container não elimina cold start nem muda o limite de 15 min. |
| 52 | **A** | 4.1.3 | `pct(@duration, 95)` nos eventos `REPORT`. |
| 53 | **B** | 4.2.4 | Annotations são indexadas e filtráveis. |
| 54 | **A** | 4.2.2 | EMF extrai métricas dos logs. |
| 55 | **B** | 4.3.1 | *Reserved concurrency* garante capacidade (e também limita). |
| 56 | **A** | 4.3.2 | Power Tuning. |
| 57 | **B** | 4.3.3 | *Long polling* reduz respostas vazias e custo. |
| 58 | **A** | 4.3.4 | DAX é compatível com a API do DynamoDB. |
| 59 | **A** | 4.3.4 | Cache key mínima aumenta o *hit ratio*. |
| 60 | **B** | 4.1.1 | 429 = throttling. |
| 61 | **B** | 4.2.5 | Readiness controla quando recebe tráfego. |
| 62 | **A, B** | 4.3.5 | Paralelismo e função mais rápida reduzem o `IteratorAge`. |
| 63 | **C** | 4.1.2 | CloudTrail registra quem chamou qual API. |
| 64 | **B** | 4.3.1 | RDS Proxy faz *pooling* de conexões. |
| 65 | **B** | 4.2.1 | JSON estruturado facilita consultas no Logs Insights. |

## Contagem de respostas
59 questões de escolha única e 6 de múltipla resposta (Q10, Q19, Q23, Q33, Q51 e Q62), todas com "Selecione DUAS".

## Desempenho por domínio (preencha)
| Domínio | Questões | Acertos | % |
|---|---|---|---|
| D1 Development | Q1–Q20 | | |
| D2 Security | Q21–Q37 | | |
| D3 Testing and Deployment | Q38–Q51 | | |
| D4 Troubleshooting and Optimization | Q52–Q65 | | |
