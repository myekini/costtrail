# CostTrail

**Cloud cost allocation you can trace.**

> **Status: in development.** Nothing below is claimed as built until it ships. This README is updated as each piece lands.

**The question:** can engineering and finance trace an allocated cost back to its source and see why it changed?

## What v1 will do

- Billed and amortized (effective) cost views over synthetic, FOCUS 1.4-shaped AWS billing data, defined and documented separately
- Direct and shared-cost allocation rules that **preserve totals to the cent**, with every allocation traceable to its source rows
- Tag-coverage and data-quality checks
- A reconciliation check against the source, for the same period, currency and cost definition only
- A small read-only cost explorer
- **An LLM variance explainer.** The pipeline computes the change, the model explains it citing those figures, and code checks every number. If a required fact is missing, it says so instead of guessing.

Evaluation for the explainer: numerical fidelity, unsupported claims, references present, latency and cost per explanation.

## What it won't do (yet)

Multiple cloud providers, every private-pricing case, full commitment optimization, automated infrastructure changes, a natural-language query agent.

## Stack

Python · DuckDB and Parquet · dbt (dbt-duckdb) once the models need it · FastAPI and Streamlit · GitHub Actions · Docker Compose

## Architecture

Diagram when it exists.

## Quick start

One command (`docker compose up`) when it exists.

## Known limitations

- Data is synthetic with planted faults. Results show performance against the generator's assumptions, not production impact.
- FOCUS is a billing-data specification, not an amortization method. The amortization rules used will be documented here.
- Invoice totals and amortized allocations are different views. Zero variance is only claimed between matching periods, currencies and definitions.

## Running cost

Stated when it exists.

## License

MIT
