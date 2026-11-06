# AtmoSync – Dashboard and Monitoring Requirements

**Owner:** Ankush Pal
**Role:** Superset, BI Dashboard and Alerts Developer
**Status:** Initial requirements documented; alert thresholds pending team approval.

## 1. Dashboard Overview

The AtmoSync Container Monitoring Dashboard provides visibility into container sensor telemetry stored in Snowflake.

**Data Source:** AtmoSync Snowflake
**Schema:** MARTS
**Primary Dataset:** MART_CONTAINER_LATEST

## 2. Implemented Monitoring KPIs

| KPI | Calculation | Purpose |
|---|---|---|
| Total Monitored Containers | COUNT(DISTINCT CONTAINER_ID) | Number of monitored containers |
| Average Temperature | AVG(TEMPERATURE_C) | Average container temperature |
| Average Humidity | AVG(HUMIDITY_PCT) | Average container humidity |
| Average Vibration | AVG(VIBRATION_G) | Average container vibration |

## 3. Proposed Alert Categories

| Alert | Monitoring Condition | Priority |
|---|---|---|
| High Temperature | Temperature exceeds approved upper limit | Warning/Critical |
| High Humidity | Humidity exceeds approved upper limit | Warning/Critical |
| Excessive Vibration | Vibration exceeds approved upper limit | Warning/Critical |
| Stale Telemetry | No recent sensor event received within the approved time limit | Warning/Critical |

## 4. Threshold Configuration

Actual alert thresholds must be confirmed with the project team.

| Parameter | Threshold |
|---|---|
| Temperature | Pending approval |
| Humidity | Pending approval |
| Vibration | Pending approval |
| Telemetry freshness | Pending approval |

No production threshold is assumed or hardcoded at this stage.

## 5. Alert Notification Requirements

Proposed notification capabilities:

- Identify the affected container using CONTAINER_ID.
- Include the alert category and measured value.
- Record the event timestamp.
- Include alert severity.
- Avoid repeated notifications for the same unresolved condition.
- Support alert resolution and recovery tracking.

Notification channels and escalation rules require team confirmation.

## 6. Implementation Status

- [x] Initial Superset dashboard created.
- [x] Four monitoring KPI charts created.
- [x] Snowflake connectivity verified.
- [x] Dashboard access verified after deployment restart.
- [ ] Team-approved alert thresholds.
- [ ] Alert engine implementation and testing.
- [ ] Notification integration.
- [ ] Final dashboard and alert validation.

## 7. Dependencies

- Snowflake telemetry data availability.
- Confirmed sensor measurement units.
- Team-approved monitoring thresholds.
- Alert notification and escalation requirements.
- Agreed deployment environment.
