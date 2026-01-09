# Failure Injection & Observability — Sock Shop

## Objetivo

Validar o comportamento do sistema Sock Shop diante da falha de um serviço crítico,
observando impacto funcional e métricas de infraestrutura.

Este experimento simula um cenário real de indisponibilidade parcial,
avaliando isolamento de falhas e capacidade de recuperação.

---

## Ambiente

- Host: Linux (Ubuntu)
- Orquestração: Docker Compose
- Aplicação: Sock Shop (microservices-demo)
- Observabilidade:
  - Prometheus
  - Grafana
  - Node Exporter

---

## Estado inicial do sistema (Baseline)

Antes da injeção de falha, todos os serviços estavam operacionais.

### Verificação

```bash
docker compose ps

---

## Experimento 2 — Falha no RabbitMQ (Mensageria)

### Justificativa

RabbitMQ é responsável pela comunicação assíncrona entre serviços.
Falhas nesse componente tendem a gerar efeitos em cascata,
afetando serviços dependentes sem derrubar imediatamente o front-end.

Este experimento avalia:
- Tolerância a falhas assíncronas
- Degradação progressiva do sistema
- Capacidade de observação via métricas

---

### Estado inicial (Baseline)

Antes da falha:

```bash
docker compose ps

