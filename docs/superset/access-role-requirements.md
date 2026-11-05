# Access Role Requirements

## 1. Overview

AtmoSync uses two separate permission systems:

1. Apache Superset roles control access to dashboards, charts and datasets.
2. Snowflake roles control access to warehouse data.

## 2. Snowflake Access

| Item | Requirement |
|---|---|
| Service User | SUPERSET_SVC |
| Role | ATMOSYNC_READER |
| Access Type | Read-only |
| Warehouse | ATMOSYNC_WH |
| Database | ATMOSYNC |

The ATMOSYNC_READER role is used for reporting access.

Recommended minimum Snowflake privileges:

- USAGE on the required warehouse.
- USAGE on the ATMOSYNC database.
- USAGE on approved schemas.
- SELECT on approved tables and views.

Exact grants should be confirmed with the Snowflake administrator.

## 3. Apache Superset Roles

| Superset Role | Intended Responsibility |
|---|---|
| Admin | Manage Superset configuration and users |
| Alpha | Create and manage charts, datasets and dashboards, subject to permissions |
| Gamma | View dashboards and charts where access is granted |
| Public | Avoid unrestricted access to project data |

These are standard role guidelines. Actual access depends on the permissions configured in Superset.

## 4. Recommended Project Access

- Administrators should manage Superset configuration.
- Dashboard developers should receive appropriate chart and dashboard creation permissions.
- Dashboard viewers should receive view-only access.
- Snowflake reporting credentials should remain read-only.
- Avoid sharing administrator credentials.

## 5. Security Practices

- Follow the principle of least privilege.
- Never commit passwords or access tokens to GitHub.
- Share credentials only through approved private channels.
- Review user and role permissions periodically.
