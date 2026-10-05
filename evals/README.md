# Evaluations

Keep versioned cases in `cases/` and deterministic sample inputs in `fixtures/`. Store generated run results, latency, cost, and traces in `.var/runs/<run-id>/`.

`cases/context-routing.json` is a manual starter evaluation for the context-routing behavior. It uses a fictional fixture, not actual business policy. Run it through the chosen agent, inspect its visible tool trace and response, and compare against the criteria. There is no automated evaluator installed.

Add cases when a workflow needs a repeatable quality check. Do not turn every transient error into a permanent evaluation.
