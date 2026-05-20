# Decision Report: Agent5 Guardrails

A live evaluation + policy conformance harness that turns Open's webhook stream into an auditable "Agent 5 didn't break the rules this week" dashboard, with zevals compatible regression suites synthesised from real handoffs.

## Evidence-Grounded Findings

CLAIM: enterprise regression harness should `open a regression issue with trace and benchmark delta` because blocks=3 reviews=5 mean_severity=2.528. [EVID: ev_0066]
CLAIM: fintech operator packet should `accept only if decision claims cite fixture evidence` because blocks=4 reviews=5 mean_severity=2.556. [EVID: ev_0011]
CLAIM: regulated boundary probe should `route to reviewer with evidence packet` because blocks=3 reviews=4 mean_severity=2.528. [EVID: ev_0033]
CLAIM: thesis evidence replay should `block release until cited evidence is regenerated` because blocks=4 reviews=5 mean_severity=2.611. [EVID: ev_0044]
