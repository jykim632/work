---
name: perf
description: Investigate and improve runtime performance in APIs, database queries, background jobs, and other code using reproducible measurements and behavior-preserving changes.
---

# Perf

Find a measured bottleneck and evaluate changes against a comparable baseline.

## Working approach

- Follow applicable project instructions and existing user preferences for tooling, Git workflow, conventions, and approvals.
- Establish the slow workflow, representative workload, environment, and metric that matters, such as latency, throughput, memory, or resource consumption.
- For browser loading and Core Web Vitals, prefer a dedicated web performance workflow when available. Keep this workflow focused on the requested runtime behavior.

## Measure and diagnose

- Reproduce the symptom safely and record a baseline before optimizing. Separate warm-up, cache state, input size, concurrency, and external dependency effects when they influence the result.
- Use existing profiling, tracing, query plans, or benchmarks to locate the bottleneck. Distinguish observations from hypotheses and avoid inferring a bottleneck solely from code appearance.
- Do not run load against production or spend substantial external resources without authorization. When representative measurement is unavailable, state the limitation and avoid claiming a confirmed speedup.

## Improve and compare

- An analysis-only request ends with findings and recommendations. When improvements are requested, implement the smallest change supported by the measurements.
- Preserve outputs, ordering, error handling, authorization, and consistency. Explain material memory, latency, freshness, or complexity tradeoffs before changing the contract.
- Compare before and after under equivalent conditions, using repeated samples when noise matters. Report absolute values, workload, and variability rather than an unsupported percentage alone.
- Run relevant correctness tests and inspect shared consumers for regressions. Keep reusable benchmarks only when they provide ongoing value within the project's existing tools.
- Report the bottleneck evidence, changes, measured results, tradeoffs, and remaining limits.
