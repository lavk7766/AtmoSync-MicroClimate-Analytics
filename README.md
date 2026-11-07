# AtmoSync – Micro-Climate Arbitrage Analytics

**An IoT-powered analytics platform for container condition monitoring, spoilage-risk analysis, and alternative-market opportunity identification.**

## 1. Project Overview

AtmoSync is a data analytics project designed to monitor environmental conditions inside shipping containers and identify potential opportunities to reduce product spoilage and improve market decisions.

The system uses temperature, humidity, and vibration telemetry to monitor container conditions. It combines environmental data with commodity prices, market information, and transportation costs to support spoilage-risk analysis and potential rerouting recommendations.

## 2. Problem Statement

Perishable goods transported over long distances can experience quality deterioration due to changing environmental conditions.

Limited visibility into container conditions and market price differences can lead to:

- Product spoilage and financial losses.
- Delayed identification of environmental risks.
- Missed opportunities in alternative markets.
- Inefficient transportation and market decisions.

AtmoSync aims to address these challenges through integrated monitoring and analytics.

## 3. Proposed Solution

AtmoSync proposes an integrated data pipeline:

1. Generate or collect IoT sensor telemetry using Python.
2. Stream sensor events through Apache Kafka.
3. Store raw telemetry in Snowflake.
4. Clean and transform data using dbt.
5. Analyse environmental conditions and estimate potential spoilage risks.
6. Compare commodity prices across alternative markets.
7. Evaluate potential rerouting opportunities using transportation information.
8. Present insights through Apache Superset dashboards.
9. Provide notifications through Slack or email.

## 4. Key Features

The planned features include:

- **Container Monitoring:** Track temperature, humidity, and vibration.
- **Sensor Data Streaming:** Process telemetry through Apache Kafka.
- **Data Warehousing:** Store raw and processed data in Snowflake.
- **Data Transformation:** Clean and model data using dbt.
- **Spoilage-Risk Analysis:** Identify containers with potentially risky environmental conditions.
- **Market Price Comparison:** Compare commodity prices across different markets.
- **Rerouting Opportunity Analysis:** Evaluate alternative markets while considering transportation costs.
- **Interactive Dashboard:** Display analytical insights using Apache Superset.
- **Alerts and Notifications:** Communicate important risks and opportunities.

## 5. System Architecture

### Proposed Data Flow

```text
Python IoT Simulator
        |
        v
Apache Kafka
        |
        v
Snowflake RAW Tables
        |
        v
dbt Transformation
        |
        v
Analytical Models
        |
        +----------------------+
        |                      |
        v                      v
Spoilage-Risk Analysis   Market Opportunity Analysis
        |                      |
        +----------+-----------+
                   |
                   v
          Apache Superset
                   |
                   v
          Slack / Email Alerts
```

**Note:** The Kafka-to-Snowflake ingestion mechanism is still subject to technical confirmation.

## 6. Technology Stack

| Technology | Purpose |
|---|---|
| Python | IoT simulation and data processing |
| Apache Kafka | Real-time telemetry streaming |
| Snowflake | Cloud data warehousing |
| dbt | Data cleaning and transformation |
| SQL | Analytical queries and data modelling |
| Apache Superset | Interactive dashboards |
| Slack / Email | Notifications and alerts |
| Git and GitHub | Version control and collaboration |

## 7. Project Directory Structure

The initial documentation structure is:

```text
AtmoSync-MicroClimate-Analytics/
│
├── README.md
│
├── docs/
│   ├── architecture/
│   │   ├── event_schema.md
│   │   └── infrastructure_checklist.md
│   │
│   ├── daily_tasks/
│   │   └── 2026-11-05.md
│   │
│   ├── dataset/
│   │   └── data_dictionary.md
│   │
│   ├── meetings/
│   │   └── kickoff_notes_2026-11-05.md
│   │
│   ├── project_overview.md
│   └── team_responsibilities.md
│
└── reports/
    └── daily_progress/
        └── 2026-11-05.md
```

Additional source-code, configuration, transformation, and dashboard directories will be added as development progresses.

## 8. Dataset and Data Sources

The project uses four primary data components:

| Dataset | Important Fields | Purpose |
|---|---|---|
| Sensor Telemetry | Temperature, humidity, vibration, timestamp | Container monitoring |
| Container Metadata | Container ID, product, quantity, origin, destination | Shipment identification |
| Commodity Pricing | Product, market, price, timestamp | Market comparison |
| Route Information | Origin, destination, distance, transport cost | Rerouting analysis |

### Data Sources

- IoT sensor data: Python-based simulation or verified sensor data.
- Container metadata: To be confirmed with the project team.
- Commodity prices: Public sources or APIs, subject to mentor confirmation.
- Route information: Verified or clearly labelled simulated information.

**Data provenance:** All datasets should identify whether their records are simulated, mentor-provided, publicly sourced, or API-generated.

Simulated data must not be presented as real-world data.

## 9. Installation and Setup

### Prerequisites

The following tools and access are expected:

- Python 3.x
- Git
- GitHub account
- Apache Kafka
- Snowflake account
- dbt with the appropriate Snowflake adapter
- Apache Superset

### Clone the Repository

```bash
git clone https://github.com/lavk7766/AtmoSync-MicroClimate-Analytics.git
```

### Navigate to the Project

```bash
cd AtmoSync-MicroClimate-Analytics
```

### Create a Python Virtual Environment

```bash
python3 -m venv .venv
```

### Activate the Environment

For macOS or Linux:

```bash
source .venv/bin/activate
```

### Install Dependencies

Once the project dependency file is created:

```bash
pip install -r requirements.txt
```

**Note:** The dependency file and exact installation instructions will be updated when the application components are implemented.

## 10. How to Run the Project

The final execution commands will be documented after the simulator, Kafka pipeline, Snowflake integration, dbt models, and dashboard are implemented.

The planned execution sequence is:

1. Configure the Python environment.
2. Start the Kafka service and required topics.
3. Run the Python IoT simulator.
4. Verify sensor events in Kafka.
5. Ingest telemetry into Snowflake.
6. Execute dbt transformations.
7. Validate analytical models.
8. Connect Snowflake to Apache Superset.
9. View dashboards and configure notifications.

Actual commands will be added after integration testing.

## 11. Dashboard and Alerts

Apache Superset is planned as the primary visualization platform.

### Planned Dashboard KPIs

- Total monitored containers.
- Average container temperature.
- Average humidity.
- Environmental threshold violations.
- Containers with elevated spoilage risk.
- Commodity prices across markets.
- Potential alternative-market opportunities.
- Estimated transportation costs.
- Potential rerouting opportunities.

### Planned Alerts

- Temperature threshold violations.
- Humidity threshold violations.
- High-risk container conditions.
- Potential market opportunities.

Slack or email integration will be finalized during development.

## 12. Team Members and Responsibilities

| Team Member | Role |
|---|---|
| Lav Kumar | Project Coordinator, Documentation and Integration Manager |
| Aditya Singh Bisht | Python IoT Simulator and Apache Kafka Developer |
| Manash Mandal | Snowflake, dbt and SQL Data Engineer |
| ANKUSH PAL | Apache Superset, BI Dashboard and Alerts Developer |

## 13. Development Roadmap

| Week | Development Focus | Expected Deliverables |
|---|---|---|
| Week 1 | Ingestion Architecture and BI Foundations | Python simulator foundation, Kafka setup, Snowflake raw tables, Superset setup |
| Week 2 | Data Engineering and Integration | dbt staging models, cleaned telemetry, commodity pricing integration |
| Week 3 | Spoilage and Arbitrage Analytics | Spoilage-risk analysis, time-to-spoilage estimation, alternative-market analysis |
| Week 4 | Automation and Final Delivery | Automated workflows, optimized pipeline, final dashboard, alerts and complete documentation |

## 14. Contribution Guidelines

The project follows a branch-based GitHub collaboration workflow.

### Branches

| Member | Branch |
|---|---|
| Lav Kumar | `lav-kumar` |
| Aditya Singh Bisht | `Aditya-Singh-Bisht` |
| Manash Mandal | `manash` |
| ANKUSH PAL | `ankush-pal` |
| Main Branch | `main` |

### Contribution Steps

1. Work on your assigned branch.
2. Keep changes limited to your assigned responsibilities.
3. Test your work before committing.
4. Commit changes with meaningful messages.
5. Push changes to your branch.
6. Raise a Pull Request to `main`.
7. Request review before merging.

Example:

```bash
git add .
git commit -m "feat: add sensor simulator"
git push origin your-branch-name
```

Do not commit credentials, passwords, API keys, or sensitive configuration files.

## 15. Current Project Status

<details>
<summary>Initial project setup – 5 November 2026</summary>

- [x] Initial project overview documented.
- [x] Team responsibilities documented.
- [x] Day 1 task allocation documented.
- [x] Proposed sensor event schema documented.
- [x] Initial data dictionary prepared.
- [x] Infrastructure checklist prepared.
- [x] Initial project documentation pushed to `lav-kumar`.

- [ ] Sensor schema technical confirmation.
- [ ] Python simulator implementation.
- [ ] Kafka configuration and streaming validation.
- [ ] Snowflake raw table setup verification.
- [ ] dbt transformation implementation.
- [ ] Commodity pricing source confirmation.
- [ ] Superset deployment and dashboard implementation.
- [ ] End-to-end pipeline integration.

</details>

**Project status:** Initial planning and documentation phase. Implementation and integration tasks are subject to verification.

---

## Project Information

**Project Name:** AtmoSync – Micro-Climate Arbitrage Analytics

**Project Period:** 5 November – 2 December 2026

**Repository:** https://github.com/lavk7766/AtmoSync-MicroClimate-Analytics

**Documentation Maintainer:** Project Coordination Team
