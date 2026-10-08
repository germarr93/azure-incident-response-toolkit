# Incident Triage Runbook

Generic first-response runbook for production incidents on an Azure-hosted platform. Severity thresholds and escalation paths are illustrative — adapt them to your organization's actual SLAs.

## 1. Severity Classification

| Severity | Definition | Target Response | Example |
|---|---|---|---|
| Sev1 — Critical | Full outage or data loss, affects all users | Immediate | Service down, database unreachable |
| Sev2 — High | Major feature broken, affects a large user segment | < 30 min | Checkout failing, auth down for one region |
| Sev3 — Medium | Partial degradation, workaround exists | < 2 hours | Slow responses on one endpoint |
| Sev4 — Low | Minor issue, no user impact | Next business day | Noisy logging, non-critical alert |

## 2. Initial Triage Checklist

1. Acknowledge the alert/ticket and note the time — the SLA clock starts here
2. Check Azure Monitor / Application Insights dashboards for the affected service
3. Confirm scope: one service, one region, or platform-wide?
4. Check recent deployments (last 24h) — correlate incident start with the release timeline
5. Check dependent services (database, third-party APIs, CDN) for upstream issues
6. Classify severity (see table above) and escalate if Sev1/Sev2

## 3. Common First Actions

- Run the error-rate and exception queries in [`../kql-queries/`](../kql-queries/) against Log Analytics
- Check App Service / VM health and resource metrics (CPU, memory, connection count)
- Review the Application Insights Failures and Exceptions blades
- If a recent deploy is implicated, consider rollback before deep investigation
- Open a dedicated incident channel/bridge for Sev1/Sev2

## 4. Escalation Path

1. **L1/L2 on-call** — initial triage and mitigation
2. **L3 / platform owner** — if root cause isn't clear within the SLA window
3. **Engineering manager** — Sev1 only, or when mitigation requires a decision beyond on-call authority

## 5. Closure

- Confirm resolution via monitoring (error rate back to baseline)
- Notify stakeholders of resolution
- Open a post-incident RCA for Sev1/Sev2 — see [`../templates/rca-template.md`](../templates/rca-template.md)
