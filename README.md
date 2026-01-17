# GSD for Antigravity

> **Get Shit Done** — A spec-driven, context-engineered development methodology adapted for Google Antigravity.

[![Based on GSD](https://img.shields.io/badge/based%20on-GSD-blue)](https://github.com/glittercowboy/get-shit-done)

## Quick Start

1. **Define your project** — Fill out `.gsd/SPEC.md` with vision and goals
2. **Plan phases** — Run `/plan` to decompose into executable phases
3. **Execute** — Run `/execute 1` to implement Phase 1
4. **Verify** — Run `/verify 1` to confirm it works
5. **Repeat** — Continue through all phases

## Commands

| Command | Role | Purpose |
|---------|------|---------|
| `/map` | The Architect | Analyze codebase → ARCHITECTURE.md, STACK.md |
| `/plan [N]` | The Strategist | Requirements → ROADMAP.md phases with XML tasks |
| `/execute [N]` | The Engineer | Wave-based execution with atomic commits |
| `/verify [N]` | The Auditor | Must-haves validation with empirical proof |
| `/debug [desc]` | The Debugger | Systematic debugging with 3-strike rule |
| `/progress` | Navigator | Show current position and next steps |
| `/pause` | — | Save state for session handoff |
| `/resume` | — | Restore from last session |

## Core Rules (GEMINI.md)

1. **Planning Lock** 🔒 — No code until SPEC.md is finalized
2. **State Persistence** 💾 — Update STATE.md after every task
3. **Context Hygiene** 🧹 — 3 failures → state dump → fresh session
4. **Empirical Validation** ✅ — Proof required, no "it should work"

## Agent Skills

| Skill | Purpose |
|-------|---------|
| `planner` | Task anatomy, goal-backward methodology |
| `executor` | Atomic commits, Need-to-Know context |
| `verifier` | Must-haves extraction, evidence requirements |
| `debugger` | 3-strike rule, systematic diagnosis |
| `codebase-mapper` | Structure analysis, debt discovery |
| `plan-checker` | Plan validation before execution |
| `context-health-monitor` | Prevents context rot |
| `empirical-validation` | Requires proof for changes |

## File Structure

```
.gsd/
├── SPEC.md              # Project vision (finalize before coding)
├── ROADMAP.md           # Phased execution plan
├── STATE.md             # Living memory across sessions
├── ARCHITECTURE.md      # System design (updated by /map)
├── STACK.md             # Technology inventory
├── DECISIONS.md         # Architecture decision records
├── JOURNAL.md           # Session chronicle
└── templates/           # Templates for plans, verification, etc.
    ├── PLAN.md
    ├── VERIFICATION.md
    ├── RESEARCH.md
    └── SUMMARY.md

.gemini/
└── GEMINI.md            # Global rules enforcement

.agent/
├── workflows/           # 8 slash commands
│   ├── map.md
│   ├── plan.md
│   ├── execute.md
│   ├── verify.md
│   ├── debug.md
│   ├── progress.md
│   ├── pause.md
│   └── resume.md
└── skills/              # 8 specialized agents
    ├── planner/
    ├── executor/
    ├── verifier/
    ├── debugger/
    ├── codebase-mapper/
    ├── plan-checker/
    ├── context-health-monitor/
    └── empirical-validation/
```

## Philosophy

- **Plan before building** — Specs matter (but no enterprise theater)
- **Fresh context > polluted context** — State dumps prevent hallucinations
- **Proof over trust** — Screenshots and command outputs, not "looks right"
- **Aggressive atomicity** — 2-3 tasks per plan, atomic commits

## XML Task Structure

Plans use semantic XML for precision:

```xml
<task type="auto">
  <name>Create login endpoint with JWT</name>
  <files>src/app/api/auth/login/route.ts</files>
  <action>
    POST endpoint accepting {email, password}.
    Use bcrypt for password comparison.
    Return JWT in httpOnly cookie.
    AVOID: jsonwebtoken (CommonJS issues)
    USE: jose library instead
  </action>
  <verify>curl -X POST localhost:3000/api/auth/login returns 200 + Set-Cookie</verify>
  <done>Valid creds → 200 + cookie, invalid → 401</done>
</task>
```

---

*Adapted from [glittercowboy/get-shit-done](https://github.com/glittercowboy/get-shit-done) for Google Antigravity*
