# AtmoSync – Apache Superset Setup Checklist

**Date:** 5 November 2026  
**Responsible:** Ankush Pal  
**Role:** Apache Superset, BI Dashboard and Alerts Developer

## 1. Objective

Deploy Apache Superset locally and connect it with Snowflake to support container monitoring, spoilage-risk analysis and market opportunity dashboards.

## 2. Local Deployment Environment

| Component | Configuration / Status |
|---|---|
| Operating environment | Ubuntu 24.04 on WSL2 |
| Container runtime | Docker Desktop with WSL integration |
| Apache Superset | Local development deployment |
| Superset URL | http://localhost:8088 |
| Superset image | Custom master-dev image |
| Snowflake SQLAlchemy | Version 2.1.0 installed |
| PostgreSQL | Superset metadata database |
| Redis | Celery message broker |
| Celery worker | Running and healthy |
| Celery beat | Running |

## 3. Deployment Verification

| Task | Status | Evidence / Remarks |
|---|---|---|
| Superset source repository obtained | Verified | Local Superset repository available |
| Custom Snowflake-enabled image built | Verified | Image: superset-snowflake:master-dev |
| Snowflake SQLAlchemy installed | Verified | Version 2.1.0 |
| Superset application started | Verified | Application container healthy |
| Superset web interface available | Verified | http://localhost:8088 |
| PostgreSQL service started | Verified | Container running |
| Redis service started | Verified | Container running |
| Celery worker started | Verified | Container healthy |
| Celery beat started | Verified | Container running |
| Snowflake database connection | Verified | Connected using ATMOSYNC_READER role |
| Source table access | Verified | Three Snowflake tables successfully queried |
| KPI chart creation | Verified | Four Big Number charts created and saved |
| Initial dashboard creation | Verified | AtmoSync Container Monitoring Dashboard created and saved |
| Alert notification delivery | Pending | Notification configuration and testing required |

## 4. Snowflake Integration Requirements

- Install a compatible Snowflake SQLAlchemy dialect in the Superset environment.
- Confirm the Snowflake account identifier and authentication method.
- Obtain the approved warehouse, database, schema and role.
- Configure a dedicated read-only service user.
- Grant the required access to analytical tables or views.
- Add the Snowflake database through Superset's database connection interface.
- Test the connection and validate access to sample data.

### Verified Connection Configuration

| Parameter | Configuration |
|---|---|
| Database | Snowflake |
| Account Identifier | rrkmnsb-bo79148 |
| Database Name | ATMOSYNC |
| Warehouse | ATMOSYNC_WH |
| Role | ATMOSYNC_READER |
| Default Schema | MARTS |
| Service User | SUPERSET_SVC |

**Security:** Passwords and other credentials are intentionally excluded from this document.

### Verified Data Sources

| Schema | Table/View | Verification |
|---|---|---|
| MARTS | MART_CONTAINER_LATEST | Successfully queried |
| STAGING | STG_CONTAINER_TELEMETRY | Successfully queried |
| STAGING | STG_COMMODITY_PRICES | Successfully queried |

All three sources returned records using `SELECT * ... LIMIT 10` queries in Superset SQL Lab.

## 5. Initial Dashboard Preparation

**Dashboard Name:** AtmoSync Container Monitoring Dashboard

**Data Source:** MARTS.MART_CONTAINER_LATEST

The following four Big Number KPI charts have been created, saved and added to the dashboard.

| KPI | Metric Expression | Displayed Value |
|---|---|---:|
| Total Monitored Containers | COUNT(DISTINCT CONTAINER_ID) | 3 |
| Average Container Temperature | AVG(TEMPERATURE_C) | 11.23 °C |
| Average Container Humidity | AVG(HUMIDITY_PCT) | 82.43% |
| Average Container Vibration | AVG(VIBRATION_G) | 0.34 g |

The displayed values represent the data returned at the time of dashboard creation and may change as new telemetry arrives.

### Proposed Future Dashboards

1. Container Environmental Monitoring.
2. Spoilage-Risk Monitoring.
3. Alternative-Market and Arbitrage Opportunities.

## 6. Alerts and Notifications

Planned alert categories:

- Temperature threshold violations.
- Humidity threshold violations.
- Elevated spoilage-risk conditions.
- Potential market opportunities.

Slack or email delivery must be configured and tested before alerts are considered operational.

Alert thresholds must be confirmed with the project team before implementation.

## 7. Deployment Issues and Observations

- Docker permission access initially required adding the development user to the Docker group.
- The initial Superset image lacked the required PostgreSQL driver.
- A development image mismatch caused dependency issues; the image was aligned with the master development branch.
- A custom image was built with the Snowflake SQLAlchemy dependency.
- The Superset application and supporting services were subsequently started successfully.
- Snowflake connectivity was established after configuring the required connection details and service role.

These observations describe the local development setup, not a production deployment.

## 8. Pending Tasks

- Configure notification channels and alert conditions.
- Confirm temperature, humidity and vibration thresholds with the project team.
- Validate KPI definitions and dashboard data with the team.
- Develop additional spoilage-risk and market-monitoring dashboards.
- Perform end-to-end dashboard and alert validation.

## 9. Security Notes

- Never commit Snowflake passwords, private keys or access tokens.
- Store connection secrets outside the Git repository.
- Use least-privilege database access.
- Prefer a dedicated read-only service account for dashboard access.
- Restrict dashboard access to authorized project members.
- Do not use administrator credentials for routine reporting.

## 10. Related Documentation

- `docs/superset/snowflake-prerequisites.md`
- `docs/superset/access-role-requirements.md`
- `docs/superset/dashboard-kpi-list.md`

**Current Status:** Local Apache Superset deployment verified. Snowflake connectivity established and three source tables tested successfully. Four KPI charts created and added to the initial container monitoring dashboard. Alert configuration, threshold validation and additional dashboards remain pending.
