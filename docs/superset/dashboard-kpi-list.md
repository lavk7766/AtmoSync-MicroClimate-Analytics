# AtmoSync Dashboard KPI List

## 1. Overview

The initial AtmoSync Container Monitoring Dashboard uses
the MARTS.MART_CONTAINER_LATEST data source in Snowflake.

## 2. Implemented KPIs

| KPI | Metric Expression | Source | Current Display |
|---|---|---|---:|
| Total Monitored Containers | COUNT(DISTINCT CONTAINER_ID) | MART_CONTAINER_LATEST | 3 |
| Average Container Temperature | AVG(TEMPERATURE_C) | MART_CONTAINER_LATEST | 11.23 °C |
| Average Container Humidity | AVG(HUMIDITY_PCT) | MART_CONTAINER_LATEST | 82.43% |
| Average Container Vibration | AVG(VIBRATION_G) | MART_CONTAINER_LATEST | 0.34 g |

## 3. Dashboard

Dashboard Name: AtmoSync Container Monitoring Dashboard

Visualization: Big Number

All four KPI charts have been created and added to the dashboard.

## 4. Proposed Future KPIs

| KPI | Requirement |
|---|---|
| Temperature Threshold Violations | Confirmed temperature limits |
| Humidity Threshold Violations | Confirmed humidity limits |
| High Vibration Alerts | Approved vibration threshold |
| Spoilage Risk | Validated risk calculation or model |
| Commodity Price Trends | Validated commodity price data |
| Container Location Monitoring | Latitude and longitude data |

## 5. Dependencies

- Threshold values must be confirmed by the project team.
- Spoilage risk requires an agreed and validated calculation or model.
- Commodity price metrics require inspection and validation of source data.
- Simulated data must be clearly identified in reporting.

## 6. Notes

The displayed KPI values represent the results at the time of dashboard creation.
They may change as new telemetry data arrives.
