# Baby Supply Chain Planning submission runner

This public fork is prepared for a reproducible submission by
[`onejumpinc/baby-scp-deterministic-agent`](https://github.com/onejumpinc/baby-scp-deterministic-agent).
It does not run on pushes. The workflow is manual-only and intentionally remains
non-runnable until the participant has a real AgentBeats UUID.

The participant release passed 200/200 scored public tasks across 40 live A2A
evaluations, two routes, and two fresh container pairs in
[`Run 35666304510`](https://github.com/onejumpinc/baby-scp-deterministic-agent/actions/runs/35666304510).
The exact public image is:

```text
ghcr.io/onejumpinc/baby-scp-deterministic-agent@sha256:db5bde2587af8f5a9c685907ff277e3c2207fa9398e7bff2f9939869374b7459
```

This release validation is not represented as an official AgentBeats score.
Only a completed green-agent run can produce a leaderboard submission.

## Benchmark and exact gate

The green agent sends five public supply-chain problems (`p1` through `p5`). A
participant must return the expected JSON plan for each problem. The workflow
creates a submission branch only when all five task results pass, the reported
pass rate is exactly 1.0, the task order and result schemas are exact, all three
container images match immutable digests, and GitHub Actions provenance matches
the running workflow.

Any missing prerequisite, registration mismatch, topology drift, partial result,
failed task, non-finite value, mutable image, or provenance mismatch stops the
workflow before a submission branch is created.

## Remaining prerequisites

1. Register the participant on AgentBeats with this immutable manifest:
   `https://raw.githubusercontent.com/onejumpinc/baby-scp-deterministic-agent/647496455c0cf2cc187a8c4078286825861d2409/amber-manifest.json5`.
2. Replace `BABY_SCP_AGENT_ID` in both `scenario.toml` and the workflow with the
   returned lowercase UUID.
3. Manually dispatch **Run Scenario**. If and only if the exact 5/5 gate passes,
   use the generated comparison link to open the upstream pull request.
