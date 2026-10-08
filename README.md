# Azure Incident Response Toolkit

Reference KQL queries, a triage runbook, and an RCA template built from day-to-day L2/L3 incident response on an Azure-hosted production platform.

![Azure Monitor](https://img.shields.io/badge/Azure_Monitor-0078D4?style=flat&logo=microsoftazure&logoColor=white)
![Log Analytics](https://img.shields.io/badge/Log_Analytics-0078D4?style=flat&logo=microsoftazure&logoColor=white)
![Application Insights](https://img.shields.io/badge/Application_Insights-0078D4?style=flat&logo=microsoftazure&logoColor=white)
![KQL](https://img.shields.io/badge/KQL-blue?style=flat)

> Generalized from real support practice. No proprietary data, customer information, or internal system details — every query and template here is reusable in any Azure / Application Insights environment.

## Why this exists

4+ years in production support means writing the same Log Analytics queries and following the same triage steps, over and over, under time pressure. This repo is the reusable version: the queries I reach for first when an alert fires, and the runbook that keeps triage consistent regardless of who's on call.

## Contents

| Folder | What's in it |
|---|---|
| [`kql-queries/`](kql-queries/) | Log Analytics / Application Insights KQL — error rates, latency percentiles, exception triage, failed-request breakdowns |
| [`runbooks/`](runbooks/) | Severity classification, initial triage checklist, escalation path |
| [`templates/`](templates/) | Post-incident RCA template |

## Background

I work in Cloud & Platform Support, handling incident response, root-cause analysis and platform troubleshooting for a high-traffic production platform on Azure — day-to-day coordination across US, LATAM and India teams. This toolkit is the practical side of that work, kept generic enough to reuse anywhere, alongside ongoing AZ-900 / Azure Security certification study.

- LinkedIn: [linkedin.com/in/germanmarr](https://www.linkedin.com/in/germanmarr)
- GitHub: [github.com/germarr93](https://github.com/germarr93)
