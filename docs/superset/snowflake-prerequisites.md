# Snowflake Connection Prerequisites

## 1. Connection Overview

Apache Superset is connected to the AtmoSync Snowflake data warehouse
using the Snowflake SQLAlchemy connector.

## 2. Connection Configuration

| Parameter | Configuration |
|---|---|
| Database | Snowflake |
| Account Identifier | rrkmnsb-bo79148 |
| Database Name | ATMOSYNC |
| Warehouse | ATMOSYNC_WH |
| Role | ATMOSYNC_READER |
| Default Schema | MARTS |
| Authentication | Username and password |
| Service User | SUPERSET_SVC |

Note: Passwords and other secrets must never be committed to GitHub.

## 3. Required Connector

The Superset environment requires:

- snowflake-sqlalchemy
- Snowflake SQLAlchemy dialect
- Apache Superset Snowflake database support

## 4. Verified Data Sources

| Schema | Table/View | Purpose |
|---|---|---|
| MARTS | MART_CONTAINER_LATEST | Latest reading for each container |
| STAGING | STG_CONTAINER_TELEMETRY | Container telemetry history |
| STAGING | STG_COMMODITY_PRICES | Commodity price information |

## 5. Network and Access Requirements

- Superset must be able to reach the Snowflake account.
- Valid Snowflake service-account credentials are required.
- The service role must have appropriate warehouse, database, schema and table access.
- Read-only access is preferred for BI reporting.

## 6. Connection Verification

The connection was successfully tested from Apache Superset.

The following queries were executed successfully:

- SELECT * FROM MART_CONTAINER_LATEST LIMIT 10;
- SELECT * FROM STG_CONTAINER_TELEMETRY LIMIT 10;
- SELECT * FROM STG_COMMODITY_PRICES LIMIT 10;

All three data sources returned records.

## 7. Security Notes

- Never expose Snowflake passwords in source code or documentation.
- Use environment-based secret management for production.
- Apply least-privilege access.
- Do not use administrator credentials for dashboard reporting.
