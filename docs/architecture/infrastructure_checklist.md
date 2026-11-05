# AtmoSync – Infrastructure Setup Checklist

**Date:** 5 November 2026

## 1. Purpose

This document tracks the infrastructure and environment requirements for the AtmoSync analytics pipeline.

## 2. Python and IoT Simulator

**Responsible:** Aditya Singh Bisht

- [ ] Python environment verified.
- [ ] Required Python libraries identified.
- [ ] Project directory structure prepared.
- [ ] Sensor event schema reviewed.
- [ ] Sample telemetry generated.
- [ ] Simulator execution tested.

## 3. Apache Kafka

**Responsible:** Aditya Singh Bisht

- [ ] Kafka installation or service availability checked.
- [ ] Kafka broker connection details confirmed.
- [ ] Required topics identified.
- [ ] `container_sensor_telemetry` topic planned.
- [ ] Producer configuration requirements documented.
- [ ] Consumer configuration requirements documented.
- [ ] Message delivery test planned.

## 4. Snowflake

**Responsible:** Manash Mandal

- [ ] Snowflake account access verified.
- [ ] Database requirements confirmed.
- [ ] RAW schema requirements confirmed.
- [ ] Raw sensor table structure designed.
- [ ] Required columns aligned with the event schema.
- [ ] Data ingestion approach documented.
- [ ] Access permissions reviewed.

## 5. dbt

**Responsible:** Manash Mandal

- [ ] dbt installation requirements identified.
- [ ] Snowflake adapter requirements identified.
- [ ] Snowflake connection configuration planned.
- [ ] dbt project structure reviewed.
- [ ] Initial staging model requirements documented.

## 6. Apache Superset

**Responsible:** ANKUSH PAL

- [ ] Superset deployment availability checked.
- [ ] Superset access verified.
- [ ] Snowflake connectivity requirements reviewed.
- [ ] Database connection prerequisites documented.
- [ ] Dashboard access roles identified.
- [ ] Initial dashboard KPIs identified.

## 7. Integration Requirements

| Integration | Responsible Members | Requirement |
|---|---|---|
| Python → Kafka | Aditya | Publish sensor events |
| Kafka → Snowflake | Aditya and Manash | Confirm ingestion mechanism and data flow |
| Snowflake → dbt | Manash | Transform raw telemetry |
| Snowflake → Superset | Manash and Ankush | Establish analytical data connection |
| Complete pipeline | All members | Validate end-to-end integration |

## 8. Security and Configuration

- [ ] Credentials stored securely.
- [ ] `.env` files excluded from Git.
- [ ] No passwords or access tokens committed.
- [ ] Required environment variables documented.
- [ ] Access permissions reviewed.

## 9. Blockers and Pending Decisions

Record unresolved setup issues here:

| Component | Issue / Decision | Owner | Status |
|---|---|---|---|
| Kafka | To be confirmed | Aditya | Pending |
| Snowflake | To be confirmed | Manash | Pending |
| dbt | To be confirmed | Manash | Pending |
| Superset | To be confirmed | Ankush | Pending |

## 10. Important Notes

- Checklist items must only be marked complete after verification.
- Actual service availability and access must be confirmed by the responsible member.
- Kafka-to-Snowflake ingestion mechanism must be agreed upon before implementation.
- All credentials must remain outside the GitHub repository.
- This checklist will be updated as infrastructure setup progresses.