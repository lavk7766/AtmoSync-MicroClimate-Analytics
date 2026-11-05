# AtmoSync – Data Dictionary

**Project:** AtmoSync – Micro-Climate Arbitrage Analytics  
**Date:** 5 November 2026  
**Status:** Initial proposed data dictionary

## 1. Purpose

This document describes the proposed data fields used in the AtmoSync project. It provides a common reference for sensor telemetry, container metadata, commodity pricing and route information.

## 2. Sensor Telemetry

| Field | Data Type | Description | Example |
|---|---|---|---|
| event_id | STRING | Unique sensor event identifier | EVT001 |
| container_id | STRING | Container identifier | CONT001 |
| timestamp | TIMESTAMP | Event generation time in UTC | 2026-11-05T10:30:00Z |
| temperature_c | FLOAT | Temperature in Celsius | 8.5 |
| humidity_pct | FLOAT | Relative humidity percentage | 72.5 |
| vibration_g | FLOAT | Vibration measurement in g units | 0.35 |
| source_type | STRING | Origin of the data | synthetic_simulated |

## 3. Container Metadata

| Field | Data Type | Description | Example |
|---|---|---|---|
| container_id | STRING | Unique container identifier | CONT001 |
| product_name | STRING | Product transported | Fresh Apples |
| quantity | FLOAT | Quantity of product | 1000 |
| quantity_unit | STRING | Unit of measurement | kg |
| origin | STRING | Shipment starting location | Mumbai |
| destination | STRING | Planned destination | Delhi |
| batch_id | STRING | Product batch identifier | BATCH001 |
| source_type | STRING | Origin of the metadata | mentor_provided |

## 4. Commodity Pricing

| Field | Data Type | Description | Example |
|---|---|---|---|
| product_name | STRING | Product name | Fresh Apples |
| market_name | STRING | Market name | Delhi Market |
| price | FLOAT | Product price | 120.50 |
| currency | STRING | Currency code | INR |
| price_timestamp | TIMESTAMP | Price observation time | 2026-11-05T10:00:00Z |
| source_type | STRING | Origin of price data | public_source |

## 5. Route Information

| Field | Data Type | Description | Example |
|---|---|---|---|
| origin | STRING | Starting location | Mumbai |
| destination | STRING | Destination location | Delhi |
| distance_km | FLOAT | Route distance in kilometres | 1150 |
| estimated_travel_hours | FLOAT | Estimated travel duration | 22 |
| transport_cost | FLOAT | Estimated transportation cost | 15000 |
| currency | STRING | Currency code for transport cost | INR |
| source_type | STRING | Origin of route information | synthetic_simulated |

## 6. Data Quality Requirements

- Unique identifiers should be maintained for events and containers.
- Timestamps should use UTC consistently.
- Numeric fields should contain valid numeric values.
- Humidity percentage should remain between 0 and 100.
- Missing values should be identified and documented.
- Product names and units should be consistent across datasets.
- Source provenance should be retained for all relevant datasets.
- Simulated data must be clearly distinguished from real-world data.

## 7. Data Integration Relationships

| Dataset | Relationship |
|---|---|
| Sensor Telemetry | Linked to Container Metadata using container_id |
| Container Metadata | Identifies product, quantity, origin and destination |
| Commodity Pricing | Matched using product and market |
| Route Information | Matched using origin and destination |

## 8. Important Notes

This is an initial proposed data dictionary. The technical team must review the fields, data types, units and relationships before implementation.

Example values are illustrative and do not represent verified live market prices or actual shipment records.