# ClawGauge

[![OpenClaw](https://img.shields.io/badge/OpenClaw-skill-EA4AAA)](https://openclaw.ai)
[![ShellBench](https://img.shields.io/badge/ShellBench-compatible-2563EB)](https://github.com/openclaw/shellbench)
[![Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?logo=python&logoColor=white)](https://www.python.org/)

Gauge models as working agents, not just leaderboard entries.

This OpenClaw skill combines:

- **ShellBench** for deterministic capability, trajectory quality, repeated
  reliability, failure modes, latency, tokens, and cost.
- **OpenClaw Personal Agent QA** as a fail-closed ten-scenario safety and
  regression gate.
- **Blind character evaluation** for persona/naturalness evidence, kept
  separate from deterministic capability and general intent claims.
- **Versioned evidence envelopes** that prove the exact requested and observed
  route, reasoning/fast state, fallback state, commits, task fingerprint,
  judge identity, campaign protocol, and optional pricing provenance.

## What it answers

- Can this model operate reliably as an OpenClaw-style agent?
- Which model performs better on the same tasks and tool surface?
- Does a cheaper model still win after explicit quality, reliability, and
  worst-of-n floors are enforced?
- What failure modes appear across repeated runs?
- Which route should handle daily operation, coding, research/browser work,
  background tasks, persona, or escalation?

It does **not** claim that a single score measures general intelligence or user
intent understanding. For those questions, use representative tasks and an
explicit rubric.

## Install

Copy this repository into your OpenClaw workspace skills directory:

```bash
git clone https://github.com/clawSean/clawgauge \
  ~/.openclaw/workspace/skills/clawgauge
```

Then start a new OpenClaw session so the skill catalog refreshes.

## Start here

Read [`SKILL.md`](SKILL.md) for the workflow and safety constraints.

The main helpers are:

- `scripts/inspect_checkouts.py` — record Mac/checkouts, commits, dirty state,
  and upstream drift without fetching.
- `scripts/run_personal_agent_preflight_isolated.sh` — provider-free isolated
  QA harness proof.
- `scripts/run_openclaw_qa_gate.py` — full-profile, exact-route QA campaigns.
- `scripts/score_qa_suite.py` — fail-closed attempt and terminal-result scoring.
- `scripts/build_evidence_envelope.py` — wrap untouched ShellBench results with
  ClawGauge-owned provenance.
- `scripts/compare_clawbench_results.py` — protocol-aware quality/value
  comparison with capability floors.
- `scripts/summarize_character_eval.py` — attested blind persona evidence.
- `scripts/self_test.py` — provider-free regression and adversarial checks.

The included fixtures are synthetic, and the QA helpers isolate state and
allowlist environment variables. Do not feed private chats, real credentials,
or personal memory into benchmark runs.

## Repository model

The live source is maintained in Sean's OpenClaw workspace. This repository and
the SkillReef copy are generated from the same scrubbed build so the public
surfaces stay synchronized.
