# TechFlow BI — Proposta Técnica de Business Intelligence

Site single-page desenvolvido como entregável da Parte Prática do trabalho de **Business Intelligence for Software Engineers** da UniFECAF (2025).

Representa a proposta técnica do Lead de Engenharia para o CTO da TechFlow: uma estratégia de BI para diagnosticar o impacto da IA Generativa no fluxo de desenvolvimento de software.

## Contexto

Após a adoção de IA Generativa em janeiro de 2024, a TechFlow registrou aumento de 40% no volume de linhas de código — mas o Lead Time cresceu 89%, o Change Failure Rate saltou 8 pontos percentuais e o Code Review tornou-se o gargalo crítico do processo de entrega.

## O que o site cobre

- **Visão Geral** — KPIs do diagnóstico pós-IA (Lead Time, Deployment Frequency, CFR, MTTR)
- **Modelagem Dimensional** — Star schema com `fato_deploys` e 4 dimensões (`dim_tempo`, `dim_repositorio`, `dim_engenheiro`, `dim_squad`)
- **Pipeline ELT** — Arquitetura Raw → Trusted → Refined com Airbyte, dbt Core e BigQuery
- **Dashboard Executivo** — 3 níveis analíticos: Macro DORA, Segmentação e Drill-down
- **Análise Estratégica** — 4 hipóteses diagnósticas e conexão deploy → valor de negócio

## Stack de BI proposta

| Camada | Ferramenta |
|--------|-----------|
| Extração | Airbyte (conectores GitHub + Jira) |
| Armazenamento | Google BigQuery |
| Transformação | dbt Core |
| Orquestração | Apache Airflow |
| Visualização | Looker Studio |

## Tecnologias do site

- HTML5 + CSS3 + JavaScript puro (sem frameworks)
- [Chart.js](https://www.chartjs.org/) via CDN
- Google Fonts (Inter)
- SVG inline para o diagrama star schema

## Como rodar

```bash
# Com Python (recomendado)
cd techflow-bi
python -m http.server 8080
# Acesse: http://localhost:8080
```

## Autor

**Rodrigo** — Lead de Engenharia  
UniFECAF · Business Intelligence for Software Engineers · 2025
