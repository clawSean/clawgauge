# ClawGauge

[![OpenClaw](https://img.shields.io/badge/OpenClaw-skill-EA4AAA)](https://openclaw.ai)
[![ClawBench](https://img.shields.io/badge/ClawBench-compatible-2563EB)](https://github.com/openclaw/clawbench)
[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)](https://www.python.org/)

Gauge models as working agents, not just leaderboard entries.

This OpenClaw skill combines:

- **ClawBench** for scored task completion, trajectory quality, reliability,
  latency, token use, and cost.
- **OpenClaw Personal Agent QA** for safety and regression gates around tool use,
  verification, approvals, and honest completion.
- **Repeated-run reporting** so stalls and one-off lucky passes do not masquerade
  as dependable capability.

## What it answers

- Can this model operate reliably as an OpenClaw-style agent?
- Which model performs better on the same tasks and tool surface?
- Does a cheaper model still win after retries, latency, and cost per successful
  task are included?
- What failure modes appear across repeated runs?

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

- `scripts/run_personal_agent_preflight_isolated.sh` — isolated QA preflight.
- `scripts/run_model_quality_benchmark.sh` — repeated live scenario runner.
- `scripts/score_qa_suite.py` — artifact-derived QA scoring.
- `scripts/compare_clawbench_results.py` — comparable ClawBench result report.

The skill deliberately uses synthetic fixtures and isolated state. Do not feed
private chats, real credentials, or personal memory into public benchmark runs.

## Repository model

The live source is maintained in Sean's OpenClaw workspace. This repository and
the SkillReef copy are generated from the same scrubbed build so the public
surfaces stay synchronized.
