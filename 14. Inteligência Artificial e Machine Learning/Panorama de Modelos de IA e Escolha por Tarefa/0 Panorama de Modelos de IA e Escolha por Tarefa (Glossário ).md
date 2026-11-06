# 📚 Guia de Estudos: Panorama de Modelos de IA e Escolha por Tarefa
#ia #llm #modelos #escolha-de-modelo

> [!info] Visão Geral
> Um mapa dos **modelos de IA disponíveis** (proprietários, de pesos abertos, pequenos/locais e especializados em imagem, voz, vídeo e embeddings) e de **qual usar em cada tarefa**: código, raciocínio, extração em volume, documentos longos, multimodal, agentes. Inclui como comparar modelos com senso crítico, combinar modelos (roteamento) e manter a escolha ao longo do tempo. Os nomes e preços mudam rápido: cada nota traz a **data da pesquisa e a fonte**. Para a base técnica, veja [[14. Inteligência Artificial e Machine Learning/Como LLMs Funcionam/0 Como LLMs Funcionam (Glossário )|Como LLMs Funcionam]].

> [!warning] Pesquisa de 06/nov/2026
> As notas com dados do mercado foram escritas com base na documentação oficial (Anthropic, OpenAI, Google) e, onde não havia fonte oficial, em comparativos de terceiros, que **divergem entre si**. Nesses casos a nota avisa. Confirme preços, IDs e licenças na fonte antes de decidir.

---

## 1 Domínio: Como Ler o Mercado de Modelos

### 1.1 Categorias e Eixos de Comparação
- **1.1.1. Taxonomia dos modelos**
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/1. Como Ler o Mercado de Modelos/1.1 Categorias e Eixos de Comparação/1.1.1. Taxonomia dos modelos/1.1.1.1. Taxonomia — frontier, intermediário, rápido, raciocínio, multimodal e pesos abertos|1.1.1.1. Taxonomia — frontier, intermediário, rápido, raciocínio, multimodal e pesos abertos]]
- **1.1.2. Eixos de comparação**
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/1. Como Ler o Mercado de Modelos/1.1 Categorias e Eixos de Comparação/1.1.2. Eixos de comparação/1.1.2.1. Eixos de escolha — capacidade, latência, custo, contexto, licença e privacidade|1.1.2.1. Eixos de escolha — capacidade, latência, custo, contexto, licença e privacidade]]
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/1. Como Ler o Mercado de Modelos/1.1 Categorias e Eixos de Comparação/1.1.2. Eixos de comparação/1.1.2.2. Lendo benchmarks com senso crítico — SWE-bench, GPQA, leaderboards e vieses|1.1.2.2. Lendo benchmarks com senso crítico — SWE-bench, GPQA, leaderboards e vieses]]

## 2 Domínio: Famílias Proprietárias

### 2.1 Anthropic — Claude
- **2.1.1. Linha atual**
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/2. Famílias Proprietárias/2.1 Anthropic — Claude/2.1.1. Linha atual/2.1.1.1. Claude — Fable, Opus, Sonnet e Haiku 5.x, papéis, preços e quando usar|2.1.1.1. Claude — Fable, Opus, Sonnet e Haiku 5.x, papéis, preços e quando usar]]
### 2.2 OpenAI
- **2.2.1. Linha atual**
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/2. Famílias Proprietárias/2.2 OpenAI/2.2.1. Linha atual/2.2.1.1. OpenAI — GPT-6 Astra, Sol, Terra e Luna, e os modelos especializados|2.2.1.1. OpenAI — GPT-6 Astra, Sol, Terra e Luna, e os modelos especializados]]
### 2.3 Google — Gemini
- **2.3.1. Linha atual**
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/2. Famílias Proprietárias/2.3 Google — Gemini/2.3.1. Linha atual/2.3.1.1. Google — Gemini 4 Argon, 3.x Flash e Flash-Lite, e a família multimodal|2.3.1.1. Google — Gemini 4 Argon, 3.x Flash e Flash-Lite, e a família multimodal]]
### 2.4 Outros provedores
- **2.4.1. xAI e demais**
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/2. Famílias Proprietárias/2.4 Outros provedores/2.4.1. xAI e demais/2.4.1.1. xAI Grok e outros provedores proprietários|2.4.1.1. xAI Grok e outros provedores proprietários]]

## 3 Domínio: Modelos de Pesos Abertos

### 3.1 Pesos abertos de fronteira
- **3.1.1. Laboratórios chineses**
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/3. Modelos de Pesos Abertos/3.1 Pesos abertos de fronteira/3.1.1. Laboratórios chineses/3.1.1.1. DeepSeek, Qwen, Kimi, GLM e MiniMax — o que cada um entrega|3.1.1.1. DeepSeek, Qwen, Kimi, GLM e MiniMax — o que cada um entrega]]
### 3.2 Pesos abertos ocidentais
- **3.2.1. Mistral, Meta e outros**
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/3. Modelos de Pesos Abertos/3.2 Pesos abertos ocidentais/3.2.1. Mistral, Meta e outros/3.2.1.1. Mistral, Meta e outros pesos abertos ocidentais|3.2.1.1. Mistral, Meta e outros pesos abertos ocidentais]]
### 3.3 Licenças
- **3.3.1. Entendendo licenças**
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/3. Modelos de Pesos Abertos/3.3 Licenças/3.3.1. Entendendo licenças/3.3.1.1. Licenças de pesos abertos — MIT, Apache 2.0 e licenças com cláusulas comerciais|3.3.1.1. Licenças de pesos abertos — MIT, Apache 2.0 e licenças com cláusulas comerciais]]

## 4 Domínio: Modelos Pequenos e Locais

### 4.1 Panorama de SLMs
- **4.1.1. Famílias pequenas**
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/4. Modelos Pequenos e Locais/4.1 Panorama de SLMs/4.1.1. Famílias pequenas/4.1.1.1. Famílias de modelos pequenos — Qwen3.5, Gemma 4, Ministral, Phi, Granite, Llama 3.2|4.1.1.1. Famílias de modelos pequenos — Qwen3.5, Gemma 4, Ministral, Phi, Granite, Llama 3.2]]
- **4.1.2. Hardware**
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/4. Modelos Pequenos e Locais/4.1 Panorama de SLMs/4.1.2. Hardware/4.1.2.1. Dimensionando memória e quantização para rodar localmente|4.1.2.1. Dimensionando memória e quantização para rodar localmente]]
### 4.2 O que modelos pequenos conseguem
- **4.2.1. Capacidades por faixa de tamanho**
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/4. Modelos Pequenos e Locais/4.2 O que modelos pequenos conseguem/4.2.1. Capacidades por faixa de tamanho/4.2.1.1. O que cada faixa de tamanho faz bem — de 1B a 30B|4.2.1.1. O que cada faixa de tamanho faz bem — de 1B a 30B]]

## 5 Domínio: Modelos Especializados

### 5.1 Além do texto
- **5.1.1. Imagem**
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/5. Modelos Especializados/5.1 Além do texto/5.1.1. Imagem/5.1.1.1. Geração e edição de imagem|5.1.1.1. Geração e edição de imagem]]
- **5.1.2. Voz e áudio**
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/5. Modelos Especializados/5.1 Além do texto/5.1.2. Voz e áudio/5.1.2.1. Voz em tempo real, transcrição e síntese de fala|5.1.2.1. Voz em tempo real, transcrição e síntese de fala]]
- **5.1.3. Vídeo**
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/5. Modelos Especializados/5.1 Além do texto/5.1.3. Vídeo/5.1.3.1. Geração e compreensão de vídeo|5.1.3.1. Geração e compreensão de vídeo]]
- **5.1.4. Embeddings**
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/5. Modelos Especializados/5.1 Além do texto/5.1.4. Embeddings/5.1.4.1. Modelos de embedding e rerankers|5.1.4.1. Modelos de embedding e rerankers]]
### 5.2 Domínios específicos
- **5.2.1. Código e setores regulados**
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/5. Modelos Especializados/5.2 Domínios específicos/5.2.1. Código e setores regulados/5.2.1.1. Modelos de código, segurança e ciências da vida|5.2.1.1. Modelos de código, segurança e ciências da vida]]

## 6 Domínio: Escolhendo o Modelo por Tarefa

### 6.1 Matriz de decisão
- **6.1.1. Tarefa × modelo**
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/6. Escolhendo o Modelo por Tarefa/6.1 Matriz de decisão/6.1.1. Tarefa × modelo/6.1.1.1. Matriz tarefa × tipo de modelo — o guia rápido|6.1.1.1. Matriz tarefa × tipo de modelo — o guia rápido]]
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/6. Escolhendo o Modelo por Tarefa/6.1 Matriz de decisão/6.1.1. Tarefa × modelo/6.1.1.2. Programação e agentes de código|6.1.1.2. Programação e agentes de código]]
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/6. Escolhendo o Modelo por Tarefa/6.1 Matriz de decisão/6.1.1. Tarefa × modelo/6.1.1.3. Raciocínio, matemática e pesquisa profunda|6.1.1.3. Raciocínio, matemática e pesquisa profunda]]
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/6. Escolhendo o Modelo por Tarefa/6.1 Matriz de decisão/6.1.1. Tarefa × modelo/6.1.1.4. Classificação, extração e roteamento em alto volume|6.1.1.4. Classificação, extração e roteamento em alto volume]]
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/6. Escolhendo o Modelo por Tarefa/6.1 Matriz de decisão/6.1.1. Tarefa × modelo/6.1.1.5. Contexto longo e análise de documentos|6.1.1.5. Contexto longo e análise de documentos]]
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/6. Escolhendo o Modelo por Tarefa/6.1 Matriz de decisão/6.1.1. Tarefa × modelo/6.1.1.6. Multimodal, uso de computador e voz|6.1.1.6. Multimodal, uso de computador e voz]]
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/6. Escolhendo o Modelo por Tarefa/6.1 Matriz de decisão/6.1.1. Tarefa × modelo/6.1.1.7. Escrita, conversação e tradução|6.1.1.7. Escrita, conversação e tradução]]
### 6.2 Combinando modelos
- **6.2.1. Estratégias**
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/6. Escolhendo o Modelo por Tarefa/6.2 Combinando modelos/6.2.1. Estratégias/6.2.1.1. Roteamento, cascata e orquestrador–trabalhadores|6.2.1.1. Roteamento, cascata e orquestrador–trabalhadores]]
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/6. Escolhendo o Modelo por Tarefa/6.2 Combinando modelos/6.2.1. Estratégias/6.2.1.2. Esforço de raciocínio versus trocar de modelo|6.2.1.2. Esforço de raciocínio versus trocar de modelo]]

## 7 Domínio: Avaliação e Manutenção da Escolha

### 7.1 Validar a escolha
- **7.1.1. Evals**
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/7. Avaliação e Manutenção da Escolha/7.1 Validar a escolha/7.1.1. Evals/7.1.1.1. Montando um conjunto de testes próprio para comparar modelos|7.1.1.1. Montando um conjunto de testes próprio para comparar modelos]]
### 7.2 Ciclo de vida
- **7.2.1. Mudanças e riscos**
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/7. Avaliação e Manutenção da Escolha/7.2 Ciclo de vida/7.2.1. Mudanças e riscos/7.2.1.1. Depreciação, versões fixadas e migração entre modelos|7.2.1.1. Depreciação, versões fixadas e migração entre modelos]]
  - [x] [[14. Inteligência Artificial e Machine Learning/Panorama de Modelos de IA e Escolha por Tarefa/7. Avaliação e Manutenção da Escolha/7.2 Ciclo de vida/7.2.1. Mudanças e riscos/7.2.1.2. Custo, privacidade e soberania de dados na escolha|7.2.1.2. Custo, privacidade e soberania de dados na escolha]]

---

> **Links Relacionados:**
> [[14. Inteligência Artificial e Machine Learning/Como LLMs Funcionam/0 Como LLMs Funcionam (Glossário )|Como LLMs Funcionam]]
> [[14. Inteligência Artificial e Machine Learning/AI Engineering (Engenharia Aplicada)/0 Engenharia de IA Aplicada (AI Engineering) ( Glossário )|Engenharia de IA Aplicada (AI Engineering)]]
> [[14. Inteligência Artificial e Machine Learning/IA Aplicada ao Desenvolvimento de Software/0 IA Aplicada ao Desenvolvimento de Software (Glossário )|IA Aplicada ao Desenvolvimento de Software]]

> **Glossário Pai:** [[0 Glossário/Glossário|Base de Conhecimento Tecnológico]]
