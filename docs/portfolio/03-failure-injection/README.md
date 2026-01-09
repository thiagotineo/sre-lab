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

