# 📚 Guia de Estudos: Microservices
#arquitetura #microservices #sistemas-distribuidos #padroes-arquiteturais

> [!info] Visão Geral
> Microservices é um estilo arquitetural que divide a aplicação em serviços pequenos, autônomos e implantáveis de forma independente, cada um dono do seu dado e alinhado a uma capacidade de negócio. Ele troca a complexidade do código pela complexidade da rede, dos dados distribuídos e da operação. Este guia cobre o conceito, a comunicação entre serviços, a consistência de dados, a operação e o fator organizacional.

---

## 1 Domínio: Fundamentos e Contexto

### 1.1 Conceito e Contexto
- **1.1.1. O que são Microservices**
  - [ ] 1.1.1.1. O que é Microservices — definição, características e princípios
  - [ ] 1.1.1.2. Quando adotar e quando não adotar microsserviços
- **1.1.2. Monolito vs Microsserviços**
  - [x] [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Microservices/1. Fundamentos e Contexto/1.1 Conceito e Contexto/1.1.2. Monolito vs Microsserviços/1.1.2.1. Monolítico Modular vs Microsserviços|1.1.2.1. Monolítico Modular vs Microsserviços]]

### 1.2 Desafios da Arquitetura
- **1.2.1. Panorama dos Desafios**
  - [x] [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Microservices/1. Fundamentos e Contexto/1.2 Desafios da Arquitetura/1.2.1. Panorama dos Desafios/1.2.1.1. Panorama dos desafios e fatores críticos de sucesso|1.2.1.1. Panorama dos desafios e fatores críticos de sucesso]]

---

## 2 Domínio: Comunicação entre Serviços

### 2.1 IPC
- **2.1.1. Estilos de Comunicação**
  - [ ] 2.1.1.1. Como definir o seu IPC — síncrono vs assíncrono, REST, gRPC e mensageria
- **2.1.2. Contrato da API**
  - [ ] 2.1.2.1. API First Design — contrato antes do código

### 2.2 Mensageria
- **2.2.1. Canais de Mensagem**
  - [ ] 2.2.1.1. Tipos de canais — Point-to-Point e Publish/Subscribe

### 2.3 Resiliência
- **2.3.1. Falhas em Cascata**
  - [x] [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Microservices/2. Comunicação entre Serviços/2.3 Resiliência/2.3.1. Falhas em Cascata/2.3.1.1. Complexidade da comunicação, timeouts, retries e Circuit Breaker|2.3.1.1. Complexidade da comunicação, timeouts, retries e Circuit Breaker]]

---

## 3 Domínio: Dados e Consistência

### 3.1 Dual Write
- **3.1.1. O Problema**
  - [x] [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Microservices/3. Dados e Consistência/3.1 Dual Write/3.1.1. O Problema/3.1.1.1. O problema do Dual Write e as quatro soluções|3.1.1.1. O problema do Dual Write e as quatro soluções]]
- **3.1.2. Padrões de Solução**
  - [x] [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Microservices/3. Dados e Consistência/3.1 Dual Write/3.1.2. Padrões de Solução/3.1.2.1. Change Data Capture (CDC)|3.1.2.1. Change Data Capture (CDC)]]
  - [x] [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Microservices/3. Dados e Consistência/3.1 Dual Write/3.1.2. Padrões de Solução/3.1.2.2. Listen to Yourself|3.1.2.2. Listen to Yourself]]
  - [x] [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Microservices/3. Dados e Consistência/3.1 Dual Write/3.1.2. Padrões de Solução/3.1.2.3. Transactional Outbox|3.1.2.3. Transactional Outbox]]
  - [x] [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Microservices/3. Dados e Consistência/3.1 Dual Write/3.1.2. Padrões de Solução/3.1.2.4. Event Sourcing e CQRS|3.1.2.4. Event Sourcing e CQRS]]
- **3.1.3. Como Escolher**
  - [x] [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Microservices/3. Dados e Consistência/3.1 Dual Write/3.1.3. Como Escolher/3.1.3.1. Framework de decisão, performance e estratégia de migração|3.1.3.1. Framework de decisão, performance e estratégia de migração]]

### 3.2 Consistência Distribuída
- **3.2.1. Mudança de Mentalidade**
  - [x] [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Microservices/3. Dados e Consistência/3.2 Consistência Distribuída/3.2.1. Mudança de Mentalidade/3.2.1.1. Consistência de dados em microsserviços|3.2.1.1. Consistência de dados em microsserviços]]

---

## 4 Domínio: Infraestrutura e Operação

### 4.1 Descoberta e Balanceamento
- **4.1.1. Infraestrutura Dinâmica**
  - [x] [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Microservices/4. Infraestrutura e Operação/4.1 Descoberta e Balanceamento/4.1.1. Infraestrutura Dinâmica/4.1.1.1. Service Discovery e balanceamento de carga|4.1.1.1. Service Discovery e balanceamento de carga]]

### 4.2 Testes
- **4.2.1. Testes em Sistemas Distribuídos**
  - [x] [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Microservices/4. Infraestrutura e Operação/4.2 Testes/4.2.1. Testes em Sistemas Distribuídos/4.2.1.1. Estratégias de teste para microsserviços|4.2.1.1. Estratégias de teste para microsserviços]]

### 4.3 Complexidade Operacional
- **4.3.1. Plataforma e Observabilidade**
  - [x] [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Microservices/4. Infraestrutura e Operação/4.3 Complexidade Operacional/4.3.1. Plataforma e Observabilidade/4.3.1.1. Complexidade operacional e engenharia de plataforma|4.3.1.1. Complexidade operacional e engenharia de plataforma]]

### 4.4 Segurança
- **4.4.1. Superfície de Ataque**
  - [x] [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Microservices/4. Infraestrutura e Operação/4.4 Segurança/4.4.1. Superfície de Ataque/4.4.1.1. Segurança em microsserviços|4.4.1.1. Segurança em microsserviços]]

---

## 5 Domínio: Organização e Evolução

### 5.1 Fator Organizacional
- **5.1.1. Times e Arquitetura**
  - [x] [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Microservices/5. Organização e Evolução/5.1 Fator Organizacional/5.1.1. Times e Arquitetura/5.1.1.1. Transformação organizacional e Team Topologies|5.1.1.1. Transformação organizacional e Team Topologies]]

### 5.2 Tendências
- **5.2.1. Adoção Pragmática**
  - [x] [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Microservices/5. Organização e Evolução/5.2 Tendências/5.2.1. Adoção Pragmática/5.2.1.1. Tendências atuais e implementação pragmática|5.2.1.1. Tendências atuais e implementação pragmática]]

---

> **Links Relacionados:**
> Estes temas têm glossário próprio e não são duplicados aqui:
> Saga, Transactional Outbox, CQRS, Event Sourcing, API Gateway, Circuit Breaker, Service Mesh, Service Discovery, Database per Service e Strangler Fig (Glossário geral, seções 10 e Integração e Mensageria).
> [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Hexagonal/0 Hexagonal (Glossário )|Hexagonal]]
> [[10. Arquitetura de Software e Design de Software/Padrões e Princípios/Padrões Arquiteturais/Clean architecture/0 Clean Architecture (Glossário )|Clean Architecture]]
