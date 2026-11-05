
# AtmoSync – Micro-Climate Arbitrage Analytics

## 1. Project Overview

AtmoSync is a Micro-Climate Arbitrage Analytics project designed to monitor environmental conditions inside shipping containers and identify opportunities to reduce product spoilage through alternative-market recommendations.

The system uses temperature, humidity and vibration sensor data to monitor container conditions. It processes this telemetry data and combines it with commodity pricing and market information to support spoilage-risk analysis and potential rerouting decisions.

## 2. Problem Statement

Perishable products transported in shipping containers may experience quality deterioration because of changing environmental conditions during transit.

Traditional monitoring may not provide sufficiently timely insights into changing container conditions or potential alternative-market opportunities.

This can result in product spoilage, financial losses and missed opportunities to sell products in more profitable markets.

## 3. Proposed Solution

AtmoSync proposes an integrated data pipeline that:

1. Generates or collects IoT sensor telemetry.
2. Streams sensor events using Apache Kafka.
3. Stores raw sensor data in Snowflake.
4. Cleans and transforms data using dbt.
5. Analyses environmental conditions and estimates spoilage risk.
6. Compares commodity prices across alternative markets.
7. Identifies potential arbitrage and rerouting opportunities.
8. Presents insights through Apache Superset dashboards.
9. Supports notifications through Slack or email alerts.

## 4. Technology Stack

| Technology | Purpose |
|---|---|
| Python | IoT sensor simulation and data processing |
| Apache Kafka | Real-time sensor data streaming |
| Snowflake | Raw data storage and analytical warehouse |
| dbt | Data cleaning, transformation and analytical models |
| Apache Superset | Business intelligence dashboards |
| Slack / Email | Opportunity and risk notifications |

## 5. Main Data Components

- Sensor telemetry: Temperature, humidity and vibration readings.
- Container metadata: Container ID, product, quantity and destination.
- Commodity pricing: Product prices across different markets.
- Route information: Distance, estimated travel time and transportation cost.
- Data provenance: Identification of whether records are simulated, mentor-provided, publicly sourced or API-generated.

## 6. Team Members and Roles

| Member | Responsibility |
|---|---|
| Lav Kumar | Project Coordination, Documentation and Integration |
| Aditya Singh Bisht | Python IoT Simulator and Apache Kafka |
| Manash Mandal | Snowflake, dbt and SQL |
| ANKUSH PAL | Apache Superset, BI Dashboard and Alerts |

## 7. Project Development Phases

### Week 1 – Ingestion Architecture and BI Foundations
Build the Python IoT simulator, configure Kafka topics, establish Snowflake raw tables and deploy Apache Superset.

### Week 2 – Data Engineering and Integration
Develop dbt staging models, clean sensor data, integrate commodity pricing and validate the data pipeline.

### Week 3 – Spoilage and Arbitrage Analytics
Develop analytical models for spoilage risk, time-to-spoilage estimation and alternative-market opportunities.

### Week 4 – Automation and Final Delivery
Finalize dashboards, automate workflows, configure alerts, optimize the pipeline and complete project documentation.

## 8. Expected Outcome

A working analytics pipeline that processes container sensor telemetry, evaluates potential spoilage risks, compares market opportunities and presents actionable insights through an interactive dashboard.

The final solution should provide:

- Container-level environmental monitoring.
- Identification of containers with potential spoilage risk.
- Comparison of alternative-market prices.
- Rerouting recommendations based on market opportunity and transportation considerations.
- Dashboard-based monitoring and alerting.

## 9. Data Source Note

IoT telemetry may be generated using a Python simulator. Commodity pricing data sources and API availability must be confirmed with the project mentor. Any simulated or mock data must be clearly identified as synthetic.

---

**Project:** AtmoSync – Micro-Climate Arbitrage Analytics  
**Project Period:** 5 November – 2 December 2026  
**Documentation Owner:** Lav Kumar
