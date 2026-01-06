# Observabilidade local com Prometheus e Grafana

## Objetivo
Implementar observabilidade básica para um sistema distribuído rodando em Docker Compose.

## Stack
- Prometheus (coleta)
- Node Exporter (host)
- Grafana (visualização)

## Resultados
- Métricas de CPU, memória e rede do host
- Visibilidade do impacto do Sock Shop no sistema
- Base pronta para alertas e SLOs

## Evidências
- docker stats
- Dashboards Grafana
- Targets Prometheus ativos

## Decisões SRE
Prometheus foi escolhido por ser padrão CNCF e pull-based. Grafana por flexibilidade e adoção de mercado.

