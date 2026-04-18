# Decodificar Checkout 2.0

## 📌 Visão Geral

O sistema **Decodificar Checkout 2.0** é uma evolução de um software legado utilizado para gestão financeira, com foco em:

* Cobrança via boletos
* Processamento de pagamentos
* Cancelamentos
* Operação de caixa (desktop)
* Integrações com adquirentes, TEF e POS

O objetivo deste projeto é modernizar a arquitetura, tecnologia e organização do sistema, mantendo as regras de negócio existentes.

---

## 🎯 Objetivo do Projeto

* Modernizar tecnologia (.NET Core)
* Melhorar organização do código
* Eliminar duplicidade de regras
* Criar arquitetura escalável e sustentável
* Permitir evolução contínua do sistema

---

## 👥 Usuários do Sistema

* Operador de Caixa (Desktop)
* Administrativo
* Gerencial
* Integrações externas
* Área financeira

---

## 🧱 Arquitetura Geral

O sistema é dividido em múltiplas camadas:

* Domain
* Application
* Infrastructure
* API
* Web
* Desktop
* Worker (processos automáticos)

---

## 🖥️ Plataformas

### Web

* ASP.NET Core MVC
* Bootstrap
* JavaScript mínimo

### Desktop

* WinUI 3
* MVVM

---

## 🗄️ Banco de Dados

* SQL Server
* Banco único centralizado
* Integração com base legado

---

## 🔐 Autenticação

* Centralizada na camada de negócio
* API expõe autenticação para clientes externos
* Desktop consome via API
* Web acessa diretamente a camada de Application

---

## 💳 Funcionalidades do MVP

* Login
* Listagem de boletos
* Pagamento de boletos
* Cancelamento de pagamento

---

## ⚙️ Estratégia de Pagamento

* Usuário paga o boleto
* Sistema distribui internamente entre lançamentos e parcelas
* Processamento varia por canal:

  * Desktop: TEF / POS / Dinheiro
  * Web: adquirente via API

---

## 🚧 Status do Projeto

Em fase de definição arquitetural (pré-implementação)
