# Arquitetura e Diretrizes do Sistema

## 📌 Objetivo

Este documento define as regras arquiteturais, padrões de desenvolvimento e contexto do sistema.

Ele também serve como base para uso com ferramentas de IA.

---

## 🧠 Contexto do Sistema

O sistema é uma modernização de um software legado financeiro com foco em:

* Boletos
* Pagamentos
* Negociação
* Integrações financeiras
* Operação de caixa

---

## 🏗️ Arquitetura

O sistema segue arquitetura em camadas:

* Domain
* Application
* Infrastructure
* API
* Web
* Desktop
* Worker

---

## 🔒 Regras de Dependência

* Domain não depende de ninguém
* Application depende apenas de Domain
* Infrastructure depende de Application e Domain
* API depende de Application
* Web NÃO acessa Infrastructure diretamente
* Desktop NÃO acessa banco diretamente

---

## 💡 Princípios

* Regra de negócio centralizada na camada Application
* Domain contém apenas regras puras
* Infrastructure contém apenas implementações técnicas
* Nenhuma regra de negócio deve existir em Web, API ou Desktop

---

## 💳 Pagamentos

### Regra central

* Pagamento é feito no nível do boleto
* Sistema distribui internamente entre lançamentos e parcelas

### Estratégia

* Processadores de pagamento por tipo:

  * TEF
  * POS
  * Adquirente Web
  * Dinheiro

### Padrão

Uso de Strategy Pattern para processadores de pagamento

---

## 🔐 Autenticação

* Centralizada na Application
* API expõe autenticação
* Web pode acessar diretamente Application
* Desktop consome via API

---

## 🗄️ Banco de Dados

* SQL Server
* Banco único
* Integração com banco legado
* Uso de EF Core

---

## ⚠️ Regras importantes

* Nunca duplicar regra de negócio
* Nunca acessar banco fora da Infrastructure
* Nunca colocar regra em Controllers
* Nunca misturar UI com regra de negócio

---

## 🤖 Diretrizes para uso com IA

Sempre considerar:

1. O sistema usa arquitetura em camadas
2. A lógica deve estar na Application
3. Domain é independente
4. Infrastructure implementa detalhes técnicos
5. Evitar duplicação de código
6. Seguir padrões já definidos
7. Sempre priorizar clareza e separação de responsabilidade

---

## 🚫 Anti-padrões proibidos

* Código duplicado
* Regras no Controller
* Acesso direto ao banco fora da Infrastructure
* Uso excessivo de lógica no frontend
* Métodos genéricos com múltiplos IFs de canal

---

## 📦 Organização futura

Estrutura base:

/src
Domain
Application
Infrastructure
Api
Web
Desktop
Worker

/tests
Tests
