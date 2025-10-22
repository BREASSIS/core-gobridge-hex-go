# 🌉 GoBridge

[![Build Status](https://img.shields.io/github/actions/workflow/status/<usuario>/core-gobridge-hex-go/build.yml?branch=main)](https://github.com/<usuario>/core-gobridge-hex-go/actions)
[![Coverage](https://img.shields.io/codecov/c/github/<usuario>/core-gobridge-hex-go)](https://codecov.io/gh/<usuario>/core-gobridge-hex-go)
[![License](https://img.shields.io/github/license/<usuario>/core-gobridge-hex-go)](LICENSE)
[![Go](https://img.shields.io/badge/Go-1.21-blue)](https://golang.org/)

---

## 🚀 Overview

**GoBridge** é um **serviço de mensageria universal** implementado em **Go**, com **Hexagonal Architecture**, projetado para:

- **Orquestrar eventos e mensagens** entre todos os módulos do ecossistema  
- **Suportar Kafka, RabbitMQ e Redis Streams** de forma transparente  
- **Permitir escalabilidade horizontal**, concorrência massiva e resiliência  
- Servir como **backbone de comunicação entre microserviços e pipelines de dados**

É a **espinha dorsal de integração** do ecossistema, permitindo que **CoreVault**, **EventHubX**, **DataForge** e outros módulos troquem mensagens de forma confiável e desacoplada.

---

## 🏗 Architecture

```mermaid
graph TD
    Domain[Core Domain Logic] -->|Ports| Adapters[Adapters Layer]
    Adapters -->|Inbound| API[REST/gRPC API]
    Adapters -->|Outbound| Messaging[Kafka / RabbitMQ / Redis Streams]
    Adapters -->|Outbound| DB[(Database)]
