# Agent5 Guardrails

A live evaluation + policy conformance harness that turns Open's webhook stream into an auditable "Agent 5 didn't break the rules this week" dashboard, with zevals compatible regression suites synthesised from real handoffs.

![Agent5 Guardrails working dashboard](outputs/project_working.svg)

## Why it exists

Open's $7M thesis is "we win regulated enterprise (fintech/healthcare) by resolving L2/L3 issues autonomously" and Agent 5's marketing leans hard on "every decision, every confidence score, every mistake" being visible (agent5). But the evaluation primitive they ship publicly is zevals — binary LLM as judge assertions over single conversations (zevals).

The project is intentionally built as a local replay harness instead of a slide. It creates fixtures, plants realistic failure modes, produces citation-locked evidence, and turns the result into a dashboard a reviewer can inspect without credentials or hosted services.

## What is inside

- Deterministic fixture generation for the company-specific risk surface.
- Strategy code in `src/agent5_guardrails/strategy.py` with project-specific scoring and visual evidence.
- Citation-locked reports where every decision claim points to a generated evidence ID.
- Two regenerated visual artifacts: `outputs/project_working.svg` and `outputs/evidence_map.svg`.
- A portable demo pack with JSON, CSV, Markdown, HTML, SVG, benchmark, and test artifacts.

![Agent5 Guardrails evidence map](outputs/evidence_map.svg)

## Signals it measures

- `thesis coverage`
- `regulated risk`
- `enterprise precision`
- `fintech latency`

## Failure modes it plants

- thesis drift
- regulated gap
- enterprise misroute
- fintech blindspot

## Run it locally

```bash
uv sync
uv run agent5-guardrails all
uv run pytest -q
uv run ruff check .
```

## Outputs worth opening

- `outputs/dashboard.html`
- `outputs/project_working.svg`
- `outputs/evidence_map.svg`
- `outputs/operator_brief.md`
- `outputs/decision_report.md`
- `outputs/strategy_model.json`
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

Everything runs locally against synthetic fixtures. There are no credentials, no customer records, no outreach files, and no hosted API dependency.
