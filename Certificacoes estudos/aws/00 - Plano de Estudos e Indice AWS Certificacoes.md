---
tags: [aws, certificacao, plano, indice]
verificado-em: 2026-11-04
---

# 🗺️ Plano e Índice — Certificações AWS Associate (Developer e Architect)

## 1. Índice dos arquivos
| Certificação | Glossário | Prompts de questões | Status |
|---|---|---|---|
| **Developer Associate (DVA-C03)** | [[DVA-C03 - Glossario]] | [[DVA-C03 - Prompts de Questoes]] | ✅ v1 completo |
| **Solutions Architect Associate (SAA-C03)** | [[SAA-C03 - Glossario]] | [[SAA-C03 - Prompts de Questoes]] | ✅ v1 completo e conferido |
| **Simulados Developer (DVA-C03)** | [[DVA-C03 - Simulado 1]] · [[DVA-C03 - Simulado 2]] · [[DVA-C03 - Simulado 3]] | 65 questões cada, gabarito no final | ✅ (04/11/2026) |
| Fontes e links de validação | [[Referencias e Fontes]] | | ✅ |
| Nota anterior (resumo informal) | [[Conteúdo de estudos Architect – Associate]] | | existente |

Estrutura de pastas:
```
Certificacoes estudos/aws/
├── 00 - Plano de Estudos e Indice AWS Certificacoes.md
├── Referencias e Fontes.md
├── developer/
│   ├── DVA-C03 - Glossario.md
│   └── DVA-C03 - Prompts de Questoes.md
└── architect/
    ├── SAA-C03 - Glossario.md
    └── SAA-C03 - Prompts de Questoes.md
```

## 2. Achados da pesquisa (2026-11-04)
1. **DVA-C02 está sendo aposentado:** registro do **DVA-C03** abriu em 27/10/2026; último dia do C02 = **30/11/2026**; C03 vale a partir de **01/12/2026**. Por isso o glossário do Developer foi construído sobre o **C03** (com a lista do que mudou).
2. **Pesos C03:** D1 30% · D2 26% · D3 22% (Testing and Deployment) · D4 22%.
3. **Novidade do C03:** foco em **IA** (novo Task 2.3 de segurança com IA; IA no desenvolvimento, teste, CI/CD, troubleshooting e otimização) + containers (ECR/ECS/EKS/Fargate) + presigned URLs + liveness/readiness.
4. **SAA-C03** continua vigente (guia v1.1); pesos 30/26/24/20; nenhuma aposentadoria oficial encontrada.
5. Ambos: 65 questões (50 pontuadas), 130 min, nota 720/1000, escolha única e múltipla resposta.
6. **Concurseiros/comunidade:** há repositórios e cheat sheets (lista em [[Referencias e Fontes]]); muitos misturam "dumps" — evitar.

## 3. Plano de execução em fases
| Fase | Entrega | Estado |
|---|---|---|
| **0** | Pesquisa em guias oficiais + comunidade | ✅ |
| **1 — Developer** | Glossário + prompts + referências (DVA-C03) | ✅ |
| **2 — Architect** | Glossário + prompts (SAA-C03), números conferidos | ✅ |
| **3 — Banco de questões** | Gerar e salvar lotes por domínio (pasta `questoes/`), validadas na doc | ⏳ |
| **4 — Simulados** | 3 simulados por certificação + análise de erros | ⏳ |

> **Decisão de escopo:** esta pasta **não** terá notas filhas nem seguirá a hierarquia pai/filho do restante do repositório. Ela é só **orientação/glossário de referência**: *o que cai* (domínio → task → skill), *como cai* (estilo das perguntas, palavras-gatilho, pegadinhas) e *links* para validar. O **conteúdo técnico detalhado** dos serviços mora nas outras camadas (ex.: `8. DevOps e Gerenciamento de Infraestrutura/CLOUD COMPUTING/AWS (AMAZON WEB SERVICE)/`). Aqui não se duplica explicação de serviço.

### 3.1 Onde estudar o conteúdo (camadas existentes)
- Base AWS: `8. DevOps.../AWS (AMAZON WEB SERVICE)/` — Glossário core, Arquitetura AWS, Lambda (ciclo de vida), Guia de rede VPC e as subpastas *Conceitos de Nuvem*, *Segurança e Conformidade*, *Tecnologia e Serviços*.
- Quando um serviço da prova não tiver nota nas camadas, o fluxo é criar a nota **lá** (padrão do Readme) e apenas referenciá-la aqui, sem copiar o conteúdo.

### 3.2 Ritmo de estudo sugerido (8 semanas por exame, ~1h/dia)
- **Sem. 1–5:** 1 domínio por semana (ler glossário → hands-on no console/Free Tier → gerar 20–30 questões com o prompt do domínio).
- **Sem. 6:** domínios fracos + comparativos.
- **Sem. 7:** 2 simulados completos cronometrados (65 questões/130 min).
- **Sem. 8:** revisão de erros (prompt 4.6), flashcards, Official Practice Question Set do Skill Builder, agendar.

## 4. Fluxo de uso para "gerar questões por tópico e subtópico"
1. Abra o glossário e escolha **Domínio → Task → Skill** (ex.: `1.2.3 Handle event lifecycles and errors`).
2. Copie o **Prompt Mestre** + o prompt do domínio no arquivo de prompts.
3. Anexe o glossário correspondente como contexto.
4. Preencha `{{SUBTOPICOS}}`, `{{QTD}}`, `{{NIVEL}}`, `{{TIPOS}}`.
5. Valide as respostas nos links de [[Referencias e Fontes]]; registre erros e use o prompt de revisão.

## 5. Observações de qualidade
- O conteúdo foi montado a partir dos **Exam Guides oficiais** (lidos integralmente) + conhecimento técnico de serviços; números de cotas devem ser reconfirmados na doc (as cotas mudam).
- Números e ferramentas de IA do C03 foram **conferidos nas docs oficiais em 2026-11-04** (tabela em [[Referencias e Fontes]]); restam só as pendências listadas lá.
- Os glossários desta pasta ainda trazem **bastante detalhe técnico** (limites, mecânicas) para apoiar a geração de questões. Isso é redundante com as camadas de conteúdo; se preferir, podem ser enxugados para ficar só com tópico, "como cai", pegadinhas e palavras-gatilho.
