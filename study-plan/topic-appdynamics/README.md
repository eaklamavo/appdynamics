# AppDynamics (Splunk AppDynamics SaaS) Study Plan

> Cloud-based Application Performance Monitoring — from first concepts to ADQL analytics, Dash Studio dashboards, alerting, and Grafana integration.

---

## Prerequisites

### Tools to Install
- Python 3.9+ and `pip` (for running notebooks and API exercises)
- `pip install notebook requests pandas matplotlib` (or `pip install jupyterlab`)
- Grafana OSS (v9+) — [download](https://grafana.com/grafana/download) — for Phase 6 exercises
- `dlopes7-appdynamics-datasource` Grafana plugin (for Phase 6)

### Accounts / Access
- A **Splunk AppDynamics SaaS** trial account — [start free trial](https://www.appdynamics.com/free-trial/)
- An AppDynamics **Controller Tenant URL** (provided after account creation, e.g., `https://<account>.saas.appdynamics.com`)
- API credentials: username, password or API key, account name

### Prior Knowledge Assumed
- Basic understanding of web application architecture (what a "server," "request," and "response" mean)
- Comfortable running Python scripts and reading JSON
- No AppDynamics experience required

---

## Capstone Overview

**Scenario**: You are an SRE at a fictitious e-commerce company. A new microservices app (`StoreFront`) has been deployed. Your mission is to:
1. Understand the AppDynamics monitoring topology for `StoreFront`
2. Write ADQL queries to detect slow transactions and errors
3. Build a Dash Studio operations dashboard with ADQL time-series bindings and dashboard variables
4. Configure health rules and alert policies to notify your team of SLA violations
5. Expose all key metrics in a Grafana dashboard using the AppDynamics datasource

---

## Phases and Lessons

| Phase | Lessons | Topics |
|-------|---------|--------|
| [Phase 1 — Foundations](phase-1-foundations/) | 4 | APM concepts, Controller, Applications, Business Transactions |
| [Phase 2 — Monitoring Core](phase-2-monitoring-core/) | 5 | Metrics, Flow Maps, Infrastructure, Database, EUM |
| [Phase 3 — Analytics & ADQL](phase-3-analytics-adql/) | 5 | Business iQ, ADQL syntax, aggregations, tables, variables |
| [Phase 4 — Dash Studio](phase-4-dash-studio/) | 5 | Dashboard editor, widgets, data binding, ADQL in dashboards |
| [Phase 5 — Alerting & Operations](phase-5-alerting-operations/) | 4 | Health rules, policies, baselines, troubleshooting |
| [Phase 6 — Grafana Integration](phase-6-grafana-integration/) | 5 | Datasource config, Metrics/Analytics/Health/Events query types |
| [Capstone](capstone/) | 1 | End-to-end observability scenario |

**Total lessons**: 28 + 1 capstone  
**Estimated time**: 30–40 hours (self-paced)

---

### Phase 1 — Foundations

| Lesson | File | Topic |
|--------|------|-------|
| 1.1 | [lesson-1.1-intro-to-appdynamics.ipynb](phase-1-foundations/lesson-1.1-intro-to-appdynamics.ipynb) | What is AppDynamics? APM, SaaS vs on-prem, product map |
| 1.2 | [lesson-1.2-controller-architecture.ipynb](phase-1-foundations/lesson-1.2-controller-architecture.ipynb) | Controller Tenant, account setup, Events Service |
| 1.3 | [lesson-1.3-applications-tiers-nodes.ipynb](phase-1-foundations/lesson-1.3-applications-tiers-nodes.ipynb) | Application topology: Applications, Tiers, Nodes |
| 1.4 | [lesson-1.4-business-transactions.ipynb](phase-1-foundations/lesson-1.4-business-transactions.ipynb) | Business Transactions: auto-discovery, naming, scopes |

### Phase 2 — Monitoring Core

| Lesson | File | Topic |
|--------|------|-------|
| 2.1 | [lesson-2.1-metrics-and-metric-browser.ipynb](phase-2-monitoring-core/lesson-2.1-metrics-and-metric-browser.ipynb) | Metrics model, Metric Browser, metric paths |
| 2.2 | [lesson-2.2-bt-performance-health.ipynb](phase-2-monitoring-core/lesson-2.2-bt-performance-health.ipynb) | BT performance, response time, error rate, call rate |
| 2.3 | [lesson-2.3-flow-maps-distributed-tracing.ipynb](phase-2-monitoring-core/lesson-2.3-flow-maps-distributed-tracing.ipynb) | Flow Maps, call graphs, transaction snapshots |
| 2.4 | [lesson-2.4-infrastructure-database-visibility.ipynb](phase-2-monitoring-core/lesson-2.4-infrastructure-database-visibility.ipynb) | Infrastructure Visibility, Database Visibility |
| 2.5 | [lesson-2.5-end-user-monitoring.ipynb](phase-2-monitoring-core/lesson-2.5-end-user-monitoring.ipynb) | EUM: Browser RUM, Mobile APM, user experience |

### Phase 3 — Analytics & ADQL

| Lesson | File | Topic |
|--------|------|-------|
| 3.1 | [lesson-3.1-business-iq-analytics-overview.ipynb](phase-3-analytics-adql/lesson-3.1-business-iq-analytics-overview.ipynb) | Business iQ, Analytics overview, Events Service |
| 3.2 | [lesson-3.2-adql-fundamentals.ipynb](phase-3-analytics-adql/lesson-3.2-adql-fundamentals.ipynb) | ADQL syntax: SELECT, FROM, WHERE, ORDER BY, LIMIT |
| 3.3 | [lesson-3.3-adql-aggregations-time-series.ipynb](phase-3-analytics-adql/lesson-3.3-adql-aggregations-time-series.ipynb) | Aggregations: count, avg, max, min, series() |
| 3.4 | [lesson-3.4-adql-analytics-tables.ipynb](phase-3-analytics-adql/lesson-3.4-adql-analytics-tables.ipynb) | Tables: transactions, browser_records, application_logs |
| 3.5 | [lesson-3.5-adql-variables.ipynb](phase-3-analytics-adql/lesson-3.5-adql-variables.ipynb) | Variables in ADQL queries, template binding |

### Phase 4 — Dash Studio

| Lesson | File | Topic |
|--------|------|-------|
| 4.1 | [lesson-4.1-dashboards-overview.ipynb](phase-4-dash-studio/lesson-4.1-dashboards-overview.ipynb) | Custom Dashboards vs Dash Studio, navigation |
| 4.2 | [lesson-4.2-dash-studio-layout-widgets.ipynb](phase-4-dash-studio/lesson-4.2-dash-studio-layout-widgets.ipynb) | Layout editor, widget types, canvas |
| 4.3 | [lesson-4.3-data-binding-metrics.ipynb](phase-4-dash-studio/lesson-4.3-data-binding-metrics.ipynb) | Data binding: server metrics, BT metrics, custom queries |
| 4.4 | [lesson-4.4-adql-in-dash-studio.ipynb](phase-4-dash-studio/lesson-4.4-adql-in-dash-studio.ipynb) | ADQL queries in Dash Studio: Time Series widget binding |
| 4.5 | [lesson-4.5-dashboard-variables.ipynb](phase-4-dash-studio/lesson-4.5-dashboard-variables.ipynb) | Dashboard variables, dynamic filtering, variable injection |

### Phase 5 — Alerting & Operations

| Lesson | File | Topic |
|--------|------|-------|
| 5.1 | [lesson-5.1-health-rules.ipynb](phase-5-alerting-operations/lesson-5.1-health-rules.ipynb) | Health rules: default, custom, conditions, scope |
| 5.2 | [lesson-5.2-policies-actions.ipynb](phase-5-alerting-operations/lesson-5.2-policies-actions.ipynb) | Policies, actions: email, HTTP, Jira, Slack |
| 5.3 | [lesson-5.3-dynamic-baselines-anomaly.ipynb](phase-5-alerting-operations/lesson-5.3-dynamic-baselines-anomaly.ipynb) | Dynamic baselines, anomaly detection, SLA enforcement |
| 5.4 | [lesson-5.4-alert-troubleshooting.ipynb](phase-5-alerting-operations/lesson-5.4-alert-troubleshooting.ipynb) | Troubleshooting alerts, threshold tuning, sensitivity |

### Phase 6 — Grafana Integration

| Lesson | File | Topic |
|--------|------|-------|
| 6.1 | [lesson-6.1-grafana-datasource-setup.ipynb](phase-6-grafana-integration/lesson-6.1-grafana-datasource-setup.ipynb) | Install plugin, configure datasource, test connection |
| 6.2 | [lesson-6.2-metrics-query-type.ipynb](phase-6-grafana-integration/lesson-6.2-metrics-query-type.ipynb) | Metrics query: application, metric path, aggregation, roll-up |
| 6.3 | [lesson-6.3-analytics-adql-in-grafana.ipynb](phase-6-grafana-integration/lesson-6.3-analytics-adql-in-grafana.ipynb) | Analytics query: ADQL in Grafana, autocomplete, limits |
| 6.4 | [lesson-6.4-health-events-tiers-queries.ipynb](phase-6-grafana-integration/lesson-6.4-health-events-tiers-queries.ipynb) | Health, Events, Tiers, Metric Names query types, annotations |
| 6.5 | [lesson-6.5-template-variables-advanced.ipynb](phase-6-grafana-integration/lesson-6.5-template-variables-advanced.ipynb) | Template variables, multi-app comparison, label customization |

---

## Recommended Resources

### 📋 Official Documentation

| Resource | URL |
|----------|-----|
| AppDynamics SaaS Help Portal | https://help.splunk.com/en/appdynamics-saas |
| AppDynamics On-Premises Help | https://help.splunk.com/en/appdynamics-on-premises |
| AppDynamics SaaS Get Started (v26.2) | https://help.splunk.com/en/appdynamics-saas/get-started/26.2.0 |
| AppDynamics Release Notes | https://help.splunk.com/en/appdynamics-saas/release-notes-and-references |

### 📚 Core Documentation

| Resource | URL |
|----------|-----|
| AppDynamics Concepts | https://help.splunk.com/en/appdynamics-saas/get-started/26.2.0/appdynamics-concepts |
| Getting Started Guide | https://help.splunk.com/en/appdynamics-saas/get-started/26.2.0/getting-started |
| Application Performance Monitoring | https://help.splunk.com/en/appdynamics-saas/application-performance-monitoring |
| Analytics Overview | https://help.splunk.com/en/appdynamics-saas/get-started/26.2.0/analytics |
| ADQL Reference | https://help.splunk.com/en/appdynamics-saas/analytics/26.2.0/analytics/adql-reference |
| Dashboards and Reports | https://help.splunk.com/en/appdynamics-saas/get-started/26.2.0/dashboards-and-reports |
| Dash Studio | https://help.splunk.com/en/appdynamics-saas/get-started/26.2.0/dashboards-and-reports/dash-studio |
| ADQL Queries in Dash Studio | https://help.splunk.com/en/appdynamics-saas/get-started/26.2.0/dashboards-and-reports/dash-studio/data-binding/adql-queries |
| Alert and Respond | https://help.splunk.com/en/appdynamics-saas/get-started/26.2.0/alert-and-respond |
| AppDynamics REST APIs | https://help.splunk.com/en/appdynamics-saas/extend-splunk-appdynamics/26.2.0/extend-splunk-appdynamics/splunk-appdynamics-apis |

### 🎓 Training & Courses

| Resource | URL |
|----------|-----|
| Splunk AppDynamics Tutorials (official) | https://help.splunk.com/en/appdynamics-saas/get-started/26.2.0/getting-started/tutorials |
| Cisco U. AppDynamics Learning Path | — search: "Cisco U AppDynamics training" |
| AppDynamics YouTube Channel | https://www.youtube.com/@AppDynamics |

### 📝 Cheat Sheets & Quick Reference

| Resource | URL |
|----------|-----|
| ADQL Reference (full syntax) | https://help.splunk.com/en/appdynamics-saas/analytics/26.2.0/analytics/adql-reference/adql-queries |
| Metric Browser Quick Start | https://help.splunk.com/en/appdynamics-saas/get-started/26.2.0/metrics-and-graphs/get-started-with-metric-browser |
| AppDynamics API Reference | https://help.splunk.com/en/appdynamics-saas/extend-splunk-appdynamics/26.2.0/extend-splunk-appdynamics/splunk-appdynamics-apis/api-clients |

### 🛠️ Key Docs by Phase/Feature

| Phase | Feature | URL |
|-------|---------|-----|
| Phase 1 | AppDynamics Concepts | https://help.splunk.com/en/appdynamics-saas/get-started/26.2.0/appdynamics-concepts |
| Phase 1 | Controller Tenant UI | https://help.splunk.com/en/appdynamics-saas/get-started/26.2.0/getting-started/controller-tenant-ui |
| Phase 1 | Install App Server Agents | https://help.splunk.com/en/appdynamics-saas/application-performance-monitoring/26.2.0/install-app-server-agents |
| Phase 2 | Business Transactions | https://help.splunk.com/en/appdynamics-saas/application-performance-monitoring/26.6.0/business-transactions |
| Phase 2 | Tiers and Nodes | https://help.splunk.com/en/appdynamics-saas/application-performance-monitoring/26.6.0/tiers-and-nodes |
| Phase 2 | Infrastructure Visibility | https://help.splunk.com/en/appdynamics-saas/infrastructure-visibility/26.2.0/infrastructure-visibility |
| Phase 2 | End User Monitoring | https://help.splunk.com/en/appdynamics-saas/end-user-monitoring/26.2.0/end-user-monitoring/overview-of-end-user-monitoring |
| Phase 3 | Analytics Overview | https://help.splunk.com/en/appdynamics-saas/analytics/26.2.0/analytics/overview-of-analytics |
| Phase 3 | ADQL Reference | https://help.splunk.com/en/appdynamics-saas/analytics/26.2.0/analytics/adql-reference |
| Phase 3 | Using Analytics Data | https://help.splunk.com/en/appdynamics-saas/analytics/26.2.0/analytics/using-analytics-data |
| Phase 4 | Dash Studio Overview | https://help.splunk.com/en/appdynamics-saas/get-started/26.2.0/dashboards-and-reports/dash-studio |
| Phase 4 | Dash Studio Widgets | https://help.splunk.com/en/appdynamics-saas/get-started/26.2.0/dashboards-and-reports/dash-studio/dash-studio-widgets |
| Phase 4 | Data Binding | https://help.splunk.com/en/appdynamics-saas/get-started/26.2.0/dashboards-and-reports/dash-studio/data-binding |
| Phase 4 | Dashboard Variables | https://help.splunk.com/en/appdynamics-saas/get-started/26.2.0/dashboards-and-reports/dash-studio/dashboard-variables |
| Phase 5 | Health Rules | https://help.splunk.com/en/appdynamics-saas/get-started/26.2.0/alert-and-respond/health-rules |
| Phase 5 | Dynamic Baselines | https://help.splunk.com/en/appdynamics-saas/application-performance-monitoring/26.2.0/business-transactions/monitor-the-business-transaction-performance/dynamic-baselines |
| Phase 5 | Policies | https://help.splunk.com/en/appdynamics-saas/get-started/26.2.0/alert-and-respond/policies |
| Phase 6 | Grafana Plugin Docs | https://grafana.com/docs/plugins/dlopes7-appdynamics-datasource/latest/ |
| Phase 6 | Grafana Query Editor | https://grafana.com/docs/plugins/dlopes7-appdynamics-datasource/latest/query-editor/ |
| Phase 6 | Grafana Plugin Configure | https://grafana.com/docs/plugins/dlopes7-appdynamics-datasource/latest/configure/ |
| Phase 6 | Grafana Annotations | https://grafana.com/docs/plugins/dlopes7-appdynamics-datasource/latest/annotations/ |

### 🧪 Practice & Sandboxes

| Resource | URL |
|----------|-----|
| AppDynamics Free Trial | https://www.appdynamics.com/free-trial/ |
| AppDynamics Sandbox (Cisco DevNet) | — search: "Cisco DevNet AppDynamics sandbox" |
| AppDynamics GitHub Samples | https://github.com/Appdynamics |
| AppDynamics Exchange (extensions) | https://developer.cisco.com/codeexchange/search?q=Appdynamics |

### 🏘️ Community & Support

| Resource | URL |
|----------|-----|
| AppDynamics Community Forums | https://community.appdynamics.com/ |
| Splunk AppDynamics Support | https://www.splunk.com/en_us/customer-success/appdynamics-support.html |
| AppDynamics GitHub | https://github.com/Appdynamics |
| Splunk Community | https://community.splunk.com/ |
| Stack Overflow Tag | https://stackoverflow.com/questions/tagged/appdynamics |
| AppDynamics Blog | https://www.appdynamics.com/blog/ |

---

## How to Use These Notebooks

1. Install Jupyter: `pip install jupyterlab`
2. Launch from this directory: `jupyter lab`
3. Open lessons in order, starting with [Phase 1, Lesson 1.1](phase-1-foundations/lesson-1.1-intro-to-appdynamics.ipynb)
4. Run cells top-to-bottom in each notebook (Shift+Enter)
5. Complete `# TODO:` / `# TASK:` exercises before moving to the next lesson
6. Have the AppDynamics Controller Tenant UI open alongside the notebooks — many exercises require switching between the notebook and the UI

> **Tip**: Store your AppDynamics credentials in environment variables (`APPD_CONTROLLER_URL`, `APPD_USER`, `APPD_PASSWORD`, `APPD_ACCOUNT`) rather than hardcoding them in notebooks.
