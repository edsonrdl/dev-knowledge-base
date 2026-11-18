# 🔷 Template Monolítico Modular (Multi-Module Hexagonal Architecture)
#arquitetura #hexagonal #ports-and-adapters #ddd #monolito-modular #template

> [!info] Visão Geral
> Este é o **template** da Arquitetura Hexagonal (Ports & Adapters) para **monólito modular** ou **serviço único**. Ele descreve **a estrutura, a responsabilidade de cada parte e onde fica cada tipo de código**, sem depender de linguagem, framework ou ferramenta de build. Use-o como ponto de partida para montar um projeto novo, estender um existente ou revisar a aderência de um repositório.
>
> Para ver a estrutura **aplicada em uma tecnologia concreta** (Java, Spring e Maven, com código), veja o [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Hexagonal/Exemplo de Implementação - Monólito Modular Hexagonal (Java, Spring e Maven)|Exemplo de Implementação (Java, Spring e Maven)]].

---

## 1. A ideia central

O **negócio fica no centro e não conhece tecnologia**. Tudo que fala com o mundo (HTTP, banco, fila, outro módulo, serviço externo) entra e sai por **portas** (contratos) e é implementado por **adapters** nas bordas.

```
   adapters de entrada  ───►  application  ───►  domain
   (HTTP, eventos)            (casos de uso,      (regras de negócio,
                               portas in/out)      sem dependências)
                                    ▲
   adapters de saída  ──────────────┘   implementam as portas de saída
   (banco, APIs, fila, outros módulos)
```

| Termo | O que é |
|---|---|
| **Porta de entrada** (primary / driving) | o que a aplicação oferece ("criar pedido"). Quem usa é um adapter de entrada |
| **Porta de saída** (secondary / driven) | o que a aplicação exige do mundo ("salvar pedido", "consultar preço"). Quem implementa é um adapter de saída |
| **Adapter** | a peça que traduz entre o mundo (HTTP, SQL, mensagem) e as portas. Só ele conhece tecnologia |
| **Hexágono** | um contexto de negócio completo: núcleo (domínio + aplicação), portas e adapters |

O monólito modular é a **soma de hexágonos** (um por bounded context) que conversam só por contratos públicos.

---

## 2. As duas regras inegociáveis

### Regra 1: dentro do módulo, o domínio não conhece ninguém

```
   adapters  ──►  application  ──►  domain
   (fora)         (orquestra)       (núcleo, não depende de nada)
```

- `domain` não depende de nada, só do `shared-kernel`.
- `application` depende do `domain`. Declara as **portas** (de entrada e de saída).
- `adapters` dependem da `application`: implementam as portas de saída e chamam as de entrada. Só eles trazem bibliotecas de tecnologia.
- Adapter de entrada e adapter de saída **não se enxergam**.

### Regra 2: entre módulos, só se enxerga o `api/`

```
   módulo A (application)  ──►  módulo B (api)       ✅ contrato público
   módulo A (application)  ──►  módulo B (domain)    ❌ proibido
   módulo A (adapters)     ──►  módulo B (adapters)  ❌ proibido
```

### Como garantir

Uma regra que depende da boa vontade do time acaba violada. O template exige **três camadas de defesa**, adaptadas à ferramenta da stack:

1. **Isolamento de build:** cada módulo declara explicitamente do que depende, e uma dependência não declarada falha na compilação (quando a stack permite).
2. **Dependências banidas:** o domínio e a aplicação não aceitam, nem indiretamente, bibliotecas de tecnologia.
3. **Teste de arquitetura:** uma verificação automática de dependências entre pastas ou pacotes, rodando no pipeline. **Sem ela verde, não há merge.**

> [!tip] Prova de proteção
> Uma regra só vale se a violação realmente falha. Ao criar o projeto, introduza temporariamente uma violação (uma biblioteca no domínio; um import entre módulos fora do `api/`), confirme que a verificação falha e remova.

---

## 3. Quando usar e quando não usar

**Use** quando há: regra de negócio relevante; várias integrações voláteis (pagamento, ERP, fila); várias pessoas ou times no mesmo código; possibilidade de extrair módulos no futuro.

**Não use** para: CRUD sem regra, protótipo descartável, script ou job trivial. Aplique Hexagonal **só nos módulos com regra rica** se o repositório mistura os dois.

---

## 4. O que definir antes de montar

| Item | O que é | Exemplo |
|---|---|---|
| Nome do serviço | identifica o repo e os logs | `shop` |
| Módulos | um por contexto de negócio (bounded context) | `catalog`, `orders` |
| Topologia | monólito modular (vários módulos) ou serviço único (um módulo) | monólito modular |
| Framework HTTP, acesso a dados, logger, testes | ferramentas padrão do projeto | definidas no plano do projeto |

Nomes de módulo: minúsculas, em inglês, substantivo do negócio. Em serviço único, existe **um** módulo.

---

## 5. Estrutura de pastas

```
<nome-do-servico>/
├── src/
│   ├── shared-kernel/                  ← mínimo e estável; sem framework
│   │   ├── domain/                     ← tipos base: raiz de agregado, evento de domínio,
│   │   │                                 erro de domínio, dinheiro
│   │   ├── application/                ← contrato de transação (unit of work)
│   │   ├── events/                     ← contrato do barramento de eventos
│   │   ├── observability/              ← contrato do logger
│   │   └── persistence/                ← contrato mínimo de acesso ao banco
│   │
│   ├── modules/
│   │   └── <modulo>/                   ← UM contexto de negócio (um hexágono)
│   │       ├── api/                    ← CONTRATO PÚBLICO: única porta de saída do módulo
│   │       │   ├── interface pública   ← o que outros módulos podem chamar
│   │       │   └── eventos             ← eventos de integração publicados
│   │       ├── domain/                 ← núcleo: regra de negócio pura
│   │       │   ├── model/              ← agregados, entidades, objetos de valor
│   │       │   ├── services/           ← regras que envolvem mais de um agregado
│   │       │   ├── specifications/     ← regras reutilizáveis e combináveis
│   │       │   ├── events/             ← eventos de domínio (algo que aconteceu)
│   │       │   └── errors/             ← erros de regra de negócio
│   │       ├── application/
│   │       │   ├── ports/in/           ← portas de entrada: um caso de uso por intenção
│   │       │   ├── ports/out/          ← portas de saída: o que se exige do mundo
│   │       │   ├── services/           ← implementam as portas de entrada (orquestram)
│   │       │   ├── commands/           ← dados de entrada dos casos de uso
│   │       │   ├── results/            ← dados de saída dos casos de uso
│   │       │   └── facade/             ← implementa a interface pública de api/
│   │       ├── adapters/
│   │       │   ├── in/http/            ← controllers, formato de request/response, rotas
│   │       │   ├── in/events/          ← assinantes de eventos de OUTROS módulos
│   │       │   ├── out/persistence/    ← repositórios, mapeadores, migrations
│   │       │   ├── out/<outro-modulo>/ ← anticorruption layer (usa só o api/ do outro)
│   │       │   └── out/events/         ← publicação no barramento de eventos
│   │       └── composição do módulo    ← único lugar que liga as camadas do módulo
│   │
│   └── bootstrap/                      ← só compõe: nenhuma regra de negócio
│       ├── ponto de entrada            ← inicia a aplicação
│       ├── configuração                ← único lugar que lê variáveis de ambiente
│       ├── health check · barramento de eventos
│       └── montagem da aplicação       ← instancia os módulos na ordem das dependências
│
├── tests/
│   ├── integration/                    ← adapters com banco/serviço real ou container
│   └── e2e/                            ← fluxos completos pela borda HTTP
├── sdd/                                ← quando existir
├── configuração da ferramenta de arquitetura (regras de dependência)
└── README, .env.example, .gitignore
```

> [!note] Em build multi-módulo
> Quando a stack permite, cada pasta de camada vira um **módulo de build** próprio (`<ctx>-api`, `<ctx>-domain`, `<ctx>-application`, `<ctx>-adapter`), e a regra de dependência passa a ser imposta pelo compilador. Veja o exemplo com Maven no documento de implementação.

---

## 6. Responsabilidade de cada pasta

| Pasta | Responsabilidade | Pode depender de | Não pode depender de |
|---|---|---|---|
| `shared-kernel` | tipos base e contratos técnicos mínimos | nada | módulos, bootstrap, bibliotecas externas |
| `<m>/api` | contrato público do módulo | `shared-kernel` | domain, application, adapters, bibliotecas externas |
| `<m>/domain` | regra de negócio | `shared-kernel` e o próprio domain | application, adapters, outros módulos, bibliotecas externas |
| `<m>/application` | orquestra casos de uso; declara portas in/out | o próprio domain, `api` de outros módulos, `shared-kernel` | adapters, bibliotecas externas |
| `<m>/adapters/in` | traduz a entrada (HTTP/evento) em comando e chama a porta de entrada | portas de entrada, commands/results, bibliotecas de tecnologia | adapters de saída, domain direto |
| `<m>/adapters/out` | implementa porta de saída com tecnologia real | portas de saída, domain, `api` de outros módulos, bibliotecas | adapters de entrada |
| composição do módulo | liga casos de uso e adapters do módulo | todas as camadas do próprio módulo, `api` de outros | — |
| `bootstrap` | liga módulos, configuração e inicialização | composição dos módulos, `shared-kernel` | camadas internas dos módulos |

> [!tip] Por que as portas de saída ficam na `application`
> Seguindo o vocabulário hexagonal, as **portas de saída pertencem à aplicação**: o domínio fica livre de qualquer contrato técnico (só tem regra de negócio) e a aplicação declara *o que precisa do mundo externo*. Se um domain service precisar de algo externo (por exemplo, cotação de frete), a porta correspondente vai no `domain`. É um caso excepcional e deve ser justificado nas decisões do projeto.

---

## 7. Onde colocar cada tipo de código

| O que é | Onde fica |
|---|---|
| Validação de **formato** (obrigatório, tamanho, e-mail) | adapter de entrada HTTP |
| Validação e cálculo de **negócio** | `domain` (método do agregado, domain service ou specification) |
| Orquestração de um caso de uso | `application/services` |
| Transação | `application/services`, via contrato de unit of work |
| Autorização (pode ou não pode) | `application/services` |
| Autenticação (token, sessão) | adapter de entrada HTTP (middleware) |
| JSON ↔ comando/resultado | adapter de entrada HTTP |
| Banco, cache, API externa | `adapters/out` |
| Chamada a outro módulo | `adapters/out/<modulo>` com anticorruption layer |
| Evento de negócio (algo ocorreu) | `domain/events` |
| Evento que cruza módulos | eventos em `api/` |
| Montagem de dependências | composição do módulo e `bootstrap` |
| Variáveis de ambiente | **somente** a configuração do `bootstrap` |

**Regra de triagem:** a decisão depende de conhecimento de negócio ou é só execução técnica? Negócio vai para o `domain`; técnica vai para um adapter. Regra de uma entidade só vira método da entidade; regra que combina agregados vira domain service; regra reutilizável e combinável vira specification. A `application` apenas **chama** a decisão que o domínio tomou.

### Como criar uma integração (API externa, mensageria ou outro módulo)

A aplicação **nunca** chama a tecnologia: ela chama uma porta de saída, e um adapter de saída a implementa.

1. **Nomear a porta pelo negócio**, não pela tecnologia nem pelo provedor: `buscar pagamento`, e não `chamar API do provedor X`.
2. **Declarar a porta em `application/ports/out`**, só com as operações que o caso de uso usa, em **tipos do próprio módulo** (nunca a resposta crua da API).
3. **Chamar a porta no serviço de aplicação**, sem saber o que existe por trás.
4. **Implementar em `adapters/out/<integração>/`** (um adapter por serviço): chamada HTTP ou cliente, tradução do formato externo para o modelo próprio, timeout, erro e nova tentativa. Sem regra de negócio.
5. **Mensageria de saída:** porta de publicação em `application/ports/out`, publicador em `adapters/out/events`. **De entrada:** assinante em `adapters/in/events` que chama uma porta de entrada; se o evento cruza módulos, o contrato fica em `api/`.
6. **Outro módulo:** porta de saída + anticorruption layer em `adapters/out/<outro-modulo>`, usando só o `api/` do vizinho.
7. **Ligar** a porta à implementação na composição do módulo.
8. **Testar:** o serviço de aplicação com porta falsa (sem rede); o adapter com serviço simulado ou container.

> [!tip] Trocar de provedor
> É escrever outro adapter e mudar só a ligação na composição. `domain` e `application` não mudam.

---

## 8. Papel de cada peça

### 8.1 shared-kernel
Só o que todos os módulos realmente compartilham e quase nunca muda: raiz de agregado (guarda os eventos pendentes), evento de domínio, erro de domínio (com código e tipo: não encontrado, conflito, inválido, proibido), dinheiro (valor inteiro da menor unidade, nunca decimal flutuante) e os contratos técnicos mínimos (transação, barramento de eventos, logger, acesso ao banco). Se um item é usado por um módulo só, ele não é do kernel.

### 8.2 domain
- O **agregado** é a raiz de consistência: guarda as invariantes e muda de estado **só por métodos de negócio**, nunca por setters públicos.
- **Objetos de valor** são imutáveis e comparados pelo valor.
- **Domain services** ficam com regras que envolvem mais de um agregado.
- **Eventos de domínio** registram o que aconteceu; o agregado os acumula e quem persiste decide quando publicá-los.
- **Sem I/O, sem biblioteca externa e sem relógio solto:** se a hora importa para a regra, ela entra como dependência fornecida pela `application`.

### 8.3 application
- **Porta de entrada:** um contrato por intenção do usuário. Uma porta com dezenas de operações é anti-padrão.
- **Porta de saída:** descreve o que a aplicação precisa do mundo, em **tipos próprios do módulo** (nunca reaproveita o modelo de outro contexto).
- **Serviço de aplicação:** implementa a porta de entrada. Carrega o necessário, chama o domínio, abre a transação, persiste e publica eventos. **Não decide regra de negócio e não conhece tecnologia.**
- **Comandos e resultados:** dados simples; nunca a entidade de domínio.
- **Facade:** implementa a interface pública de `api/` para os outros módulos, devolvendo dados simples.

### 8.4 api (contrato público)
Só interfaces, dados simples e constantes de eventos. **Nunca** expõe entidade de domínio. Mudar algo aqui é mudar contrato: afeta todos os consumidores, então muda com cuidado e com versão de evento.

### 8.5 adapters de entrada
Finos: validam o formato, montam o comando, chamam a porta de entrada e traduzem o resultado. Dependem da **porta**, nunca do serviço concreto. Um mapeador de erros converte erro de domínio em resposta HTTP; erro inesperado vira 500 genérico, sem vazar detalhe interno. Assinantes de evento recebem o evento de outro módulo (usando só o `api/` dele) e chamam uma porta de entrada.

### 8.6 adapters de saída
- **Repositório:** implementa a porta de persistência e converte entre domínio e modelo do banco por um **mapeador**. O domínio **nunca é** o modelo de persistência.
- **Anticorruption layer:** implementa a porta que fala com outro módulo, usando só o `api/` dele, e traduz o modelo alheio para o modelo próprio.
- **Publicador de eventos:** entrega o evento ao barramento.
- O adapter de saída **não decide fluxo de negócio**: só executa o que a aplicação mandou.

### 8.7 composição do módulo e bootstrap
A composição do módulo é o **único lugar que instancia e liga** adapters, serviços e facade de um módulo. O `bootstrap` instancia os módulos **na ordem das dependências** (o módulo consultado antes do consumidor). Adicionar um módulo é criar a sua composição e registrar uma linha no bootstrap; remover é apagar essa linha.

---

## 9. Comunicação entre módulos

| Situação | Mecanismo |
|---|---|
| Preciso do dado agora (preço, estoque) | `api/` do outro módulo, consumido por adapter de saída com anticorruption layer |
| Aviso de que algo aconteceu | evento de integração no barramento (contrato em `api/`) |
| Efeito que **não pode ser perdido** | outbox: grava o evento na mesma transação e publica depois |
| Preciso de consistência forte entre dois contextos | reavalie: provavelmente são o mesmo contexto |

**Proibido:** importar domain, application ou adapters de outro módulo; JOIN ou chave estrangeira entre dados de módulos; ler a tabela do vizinho; entidade de domínio dentro de evento ou `api`; dois módulos compartilhando o mesmo modelo de persistência.

---

## 10. Banco de dados

- Cada módulo só toca nos **seus** dados.
- Com banco que suporta schema: **um schema por módulo**. Sem suporte: prefixo no nome da tabela.
- Referência a outro módulo é só o **identificador**, sem chave estrangeira.
- Migrations versionadas, automatizadas no pipeline e **nunca editadas** depois de aplicadas em produção. Ficam dentro do módulo, na persistência, com nome que inclui data e hora.
- Em serviço único, o serviço é dono do seu banco.

---

## 11. Tratamento de erros

- Regra de negócio violada → erro de domínio (com código e tipo) → mapeador do adapter de entrada → envelope de erro padrão.
- Erro de formato → 400 com detalhe por campo, no adapter de entrada.
- Erro inesperado → 500 genérico; log com a causa técnica e **sem dados do payload**.
- Nível de erro no log apenas para falha que exige atenção humana.

---

## 12. Testes por camada

| Camada | O que testar | Como |
|---|---|---|
| `domain` | invariantes e regras | puro, sem mock |
| `application` | orquestração, ordem, erros | portas de saída falsas, sem framework |
| `adapters/in` | formato, status HTTP, tradução de erros | controller com a porta de entrada simulada |
| `adapters/out` | mapeador, consultas, contrato da porta | integração com banco real ou container |
| arquitetura | regras de dependência | verificação automática + prova de proteção |

---

## 13. Checklist de conformidade

```
✓ domain sem biblioteca externa ou framework
✓ domain não importa application, adapters nem outro módulo
✓ application sem adapters nem biblioteca externa
✓ adapter de entrada não importa adapter de saída (e vice-versa)
✓ módulo só importa o api/ de outro
✓ sem ciclos de dependência
✓ toda saída (banco, HTTP, fila, outro módulo) passa por porta de saída
✓ controllers sem regra de negócio nem mutação direta de agregado
✓ application sem cálculo de negócio
✓ adapter de saída não decide fluxo de negócio
✓ agregado sem setters públicos; muda estado por método de negócio
✓ domínio é diferente do modelo de persistência (existe mapeador)
✓ dinheiro não é decimal flutuante
✓ cada porta de entrada = uma intenção
✓ schema ou prefixo por módulo; sem chave estrangeira entre módulos
✓ variáveis de ambiente só na configuração do bootstrap
✓ a verificação de arquitetura roda no pipeline e a prova de proteção foi feita
```

---

## 14. Anti-padrões e como corrigir

| Anti-padrão | Correção |
|---|---|
| Entidade de domínio acoplada ao ORM | classe de domínio pura + mapeador + modelo de persistência no adapter |
| Domain service chamando API externa | porta de saída + adapter |
| Controller com regra de negócio | mover para o agregado; o controller só chama a porta |
| Serviço de aplicação com cálculo de negócio | mover para agregado ou domain service |
| Adapter decidindo fluxo (repositório dispara e-mail) | a decisão sobe para a `application`; o adapter só persiste |
| Módulo usando internals do vizinho | `api/` + anticorruption layer |
| Serviço com dezenas de operações | dividir em portas coesas, uma por intenção |
| Modelo do vizinho vazando para o domínio | anticorruption layer traduz para tipos próprios |

---

## 15. Trade-offs

```
✅ Vantagens
  - Domínio testável em milissegundos, sem banco nem framework
  - Troca de tecnologia isolada nos adapters
  - Fronteiras prontas para extração futura em microsserviços
  - Cada módulo com responsabilidade óbvia

⚠️ Custos
  - Mais código de tradução: mapeadores e dados simples em cada borda
  - Curva de aprendizado para quem está acostumado a "tudo num projeto"
  - Excesso de cerimônia em CRUD simples
```

---

## 16. Evolução para microsserviço

Para extrair um módulo (por exemplo `catalog`): o anticorruption layer do consumidor passa a chamar HTTP em vez do `api/` em memória; o assinante de evento troca o barramento em memória pela fila; o schema vira banco próprio. **Não mudam** `domain` nem `application` de nenhum dos dois lados.

---

## 17. Relação com outros conceitos

- **Ports & Adapters (Cockburn):** é a base do template: portas de entrada e saída, adapters nas bordas.
- **Clean Architecture:** protege o domínio do mesmo jeito. Ela organiza o código em anéis concêntricos, enquanto a Hexagonal enfatiza a simetria "entra por uma porta, sai por outra". Veja o [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Clean architecture/Template Monolítico Modular (Multi-Module Clean Architecture)|Template de Clean Architecture]].
- **Domain-Driven Design:** agregados, objetos de valor, eventos de domínio e bounded contexts.
- **SOLID:** especialmente a inversão de dependência: o núcleo define o contrato e a borda o obedece.
- **Exemplo de implementação:** [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Hexagonal/Exemplo de Implementação - Monólito Modular Hexagonal (Java, Spring e Maven)|Java, Spring e Maven]].
