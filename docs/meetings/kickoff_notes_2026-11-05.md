# AtmoSync – Project Kickoff Meeting Notes

**Date:** 5 November 2026  
**Meeting:** Project Kickoff – Day 1  
**Project:** AtmoSync – Micro-Climate Arbitrage Analytics

## 1. Meeting Objective

To establish a common understanding of the project scope, objectives, team responsibilities, development milestones, technical architecture and communication process.

## 2. Project Scope

AtmoSync aims to monitor environmental conditions inside shipping containers using temperature, humidity and vibration telemetry.

The system will process sensor data, combine it with commodity pricing and market information, estimate potential spoilage risks and identify alternative-market opportunities.

## 3. Assigned Team Responsibilities

| Member | Role |
|---|---|
| Lav Kumar | Project Coordinator, Documentation and Integration Manager |
| Aditya Singh Bisht | Python IoT Simulator and Apache Kafka Developer |
| Manash Mandal | Snowflake, dbt and SQL Data Engineer |
| ANKUSH PAL | Apache Superset, BI Dashboard and Alerts Developer |

## 4. Proposed Technical Workflow

1. Python generates simulated IoT sensor telemetry.
2. Apache Kafka streams sensor events.
3. Snowflake stores raw sensor data.
4. dbt cleans and transforms the data.
5. Analytical models estimate spoilage risk and market opportunities.
6. Apache Superset displays analytical results.
7. Slack or email alerts communicate important findings.

## 5. Initial Data Requirements

The proposed sensor event fields are:

- event_id
- container_id
- timestamp
- temperature_c
- humidity_pct
- vibration_g
- source_type

The final field definitions and data types must be reviewed by the simulator and data engineering members.

## 6. GitHub Collaboration

The team will use individual branches for development.

| Member | Branch |
|---|---|
| Lav Kumar | lav-kumar |
| Aditya Singh Bisht | Aditya-Singh-Bisht |
| Manash Mandal | manash |
| ANKUSH PAL | To be created |
| Main branch | main |

Members should commit their work to their assigned branches and raise pull requests for review.

## 7. Development Milestones

| Week | Main Focus |
|---|---|
| Week 1 | Ingestion architecture and BI foundations |
| Week 2 | Data engineering and integration |
| Week 3 | Spoilage and arbitrage analytics |
| Week 4 | Automation, dashboard finalization and documentation |

## 8. Initial Decisions and Pending Confirmations

| Item | Status |
|---|---|
| Project scope | To be confirmed by team |
| Member responsibilities | Assigned; team confirmation pending |
| Sensor event schema | Proposed; technical review pending |
| Kafka topic | Proposed; implementation pending |
| Snowflake access | Verification pending |
| Superset deployment | Verification pending |
| Commodity pricing source | Mentor confirmation pending |
| Kafka-to-Snowflake ingestion method | Technical decision pending |

## 9. Day 1 Action Items

| Member | Action |
|---|---|
| Lav Kumar | Maintain project documentation, GitHub Issues and coordination |
| Aditya Singh Bisht | Verify Python environment and prepare simulator skeleton |
| Manash Mandal | Verify Snowflake access and design raw sensor table |
| ANKUSH PAL | Check Superset deployment and Snowflake connection prerequisites |

## 10. Communication and Reporting

- Members will report their progress daily.
- Daily updates will be collected at 11:00 PM.
- Each member should share completed tasks, GitHub links, evidence and blockers.
- The Project Coordinator will verify work before updating completion status.

## 11. Meeting Outcome

This document records the initial project kickoff plan and proposed technical direction. Decisions should be updated after confirmation by the relevant team members and mentor.

**Prepared by:** Lav Kumar  
**Role:** Project Coordinator and Documentation Manager