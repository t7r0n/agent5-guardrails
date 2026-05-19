# Agent5 Guardrails

A live evaluation + policy conformance harness that turns Open's webhook stream into an auditable "Agent 5 didn't break the rules this week" dashboard, with zevals compatible regression suites synthesised from real handoffs.

## Why This Exists

Open's $7M thesis is "we win regulated enterprise (fintech/healthcare) by resolving L2/L3 issues autonomously" and Agent 5's marketing leans hard on "every decision, every confidence score, every mistake" being visible (agent5). But the evaluation primitive they ship publicly is zevals - binary LLM as judge assertions over single conversations (zevals).

## What It Builds

- Replays synthetic `thesis` and `regulated` cases against the project's evidence rules.
- Scores `thesis_coverage`, `regulated_risk`, and `enterprise_precision` so regressions are visible in CSV and JSON.
- Plants `thesis drift` and `regulated gap` failures as negative controls.
- Writes citation-locked decision claims; unsupported claims fail verification.
- Exports a review dashboard and demo pack for `agent5-guardrails` without hosted services.

## Local Run

```bash
uv sync
uv run agent5-guardrails all
uv run pytest -q
uv run ruff check .
```

## Outputs

- `outputs/analysis.json`
- `outputs/scenario_report.csv`
- `outputs/decision_report.md`
- `outputs/evidence_packet.md`
- `outputs/dashboard.html`
- `outputs/demo_pack.zip`

## Sources

- https://www.open.cx/agent5
- https://docs.open.cx/introduction
- https://github.com/opencx-labs
- https://github.com/opencx-labs/zevals
- https://github.com/opencx-labs/copilot
- https://wasssl.com/opencx-raises-usd-7-million-to-scale-ai-customer-communication-across-enterprises/
- https://theaiinsider.tech/2025/01/13/open-cx-closes-1-52m-funding-round-to-disrupt-customer-support-with-advanced-ai-solutions/
- https://www.linkedin.com/posts/gharabat_we-have-released-opens-public-apis-likely-activity-7237491696177938433-YCOK
- https://www.linkedin.com/posts/gharabat_introducing-companion-the-agentic-version-activity-7449507043876519936-FW4C

## Boundary

This repository uses synthetic fixtures only. It has no credentials, no customer data, no outreach data, and no dependency on a hosted API.
