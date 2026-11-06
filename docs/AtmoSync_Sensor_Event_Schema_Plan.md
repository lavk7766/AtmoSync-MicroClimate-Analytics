# AtmoSync – Sensor Event Schema Proposal

**Status:** Proposed – pending team approval  
**Owner:** Python IoT Simulator / Kafka  
**Purpose:** Define a consistent telemetry event produced by the Python simulator and consumed by Kafka and Snowflake.

## 1. Proposed sensor event

Use one combined event per container per sampling interval. Each event contains the temperature, humidity and vibration readings captured for that container at the same observation time.

| Field | Proposed data type | Unit / format | Description |
|---|---|---|---|
| `event_id` | STRING | UUID | Unique identifier for each event |
| `container_id` | STRING | — | Identifier of the container |
| `timestamp` | TIMESTAMP | UTC, ISO 8601 in JSON | Time when the readings were captured |
| `temperature_c` | FLOAT | Degrees Celsius (°C) | Container temperature |
| `humidity_pct` | FLOAT | Percent (%) | Relative humidity |
| `vibration_g` | FLOAT | g (standard gravity) | Vibration acceleration measurement |
| `source_type` | STRING | e.g. `synthetic_simulated` | Identifies whether the event is simulated or from a real sensor |
| `schema_version` | STRING | e.g. `1.0` | Optional schema version for future changes |

## 2. Example JSON event

```json
{
  "event_id": "550e8400-e29b-41d4-a716-446655440000",
  "container_id": "CONT001",
  "timestamp": "2026-11-06T08:30:00Z",
  "temperature_c": 8.5,
  "humidity_pct": 72.5,
  "vibration_g": 0.35,
  "source_type": "synthetic_simulated",
  "schema_version": "1.0"
}
```

## 3. Proposed validation rules

- `event_id` must be present and unique for each event.
- `container_id` must be present and non-empty.
- `timestamp` must be a valid UTC timestamp.
- `temperature_c`, `humidity_pct` and `vibration_g` must be numeric and non-null.
- `humidity_pct` must be between 0 and 100.
- Temperature and vibration should be checked against agreed sensor/device operating ranges. Do not reject unusual but valid readings solely because they may indicate a spoilage or handling risk.
- `source_type` must use an agreed value, such as `synthetic_simulated` for generated data.
- If `schema_version` is adopted, it must be populated consistently.

## 4. Measurement clarification required

The field `vibration_g` specifies the unit but does not yet define the measurement method. The team must decide whether it represents RMS acceleration, peak acceleration, or a specific axis measurement.

**Recommendation:** Use RMS acceleration in g as the initial definition if that matches the intended sensor and analytical use case. Confirm this with the team before implementation.

## 5. Design decisions to confirm with the team

1. Approve the seven existing fields and their proposed data types.
2. Confirm whether to add the optional `schema_version` field.
3. Confirm that one combined event per container per sampling interval is required.
4. Define the meaning of `vibration_g` (RMS, peak, or axis-specific).
5. Agree on valid operating ranges for simulated temperature and vibration readings.
6. Confirm the allowed `source_type` values.
7. Confirm that timestamps are UTC and serialized as ISO 8601 strings in JSON.

## 6. Kafka alignment

- **Proposed topic:** `container_sensor_telemetry`
- **Message format:** JSON
- **Suggested message key:** `container_id`, to group events by container and support per-container ordering within a Kafka partition.
- The final field names and types should match the downstream Snowflake raw table.

## 7. Scope note

This document is a proposal for team review, not a finalized contract. Keep the event schema stable across the simulator, Kafka producer and Snowflake ingestion. Any changes should be agreed with the team before implementation.
