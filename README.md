# selfradiance

Open-source reference implementations for **runtime accountability in AI agent systems**.

I started building about a month ago from zero coding background — I direct AI coding tools (primarily Claude Code) and make the design and architecture decisions myself. What I care about is a simple question:

**How do we make autonomous agents economically accountable for what they do, what they're allowed to do, and what happens when they fail?**
<img width="1440" height="1102" alt="image" src="https://github.com/user-attachments/assets/a1f1e527-cdfb-4825-ad7e-8e9c98136dd4" />

---

**Core engine:** [AgentGate](https://github.com/selfradiance/agentgate) · **Proof ladder:** Agents 001–006 · **Extensions:** Delegation, MCP Firewall, Epistemic Poisoning · **Standards:** RestaRules

---

## AgentGate

[**agentgate**](https://github.com/selfradiance/agentgate) — A collateralized execution engine for AI agents. Before an agent can take a high-impact action, it must post a bond as collateral. Good behavior releases the bond. Bad behavior slashes it. Ed25519 signed identities, reusable bonds, progressive trust tiers, prediction markets, and an auto-slash sweeper.

Everything below is built on top of AgentGate or extends its model.

---

## Reference Agents

Each agent proves a different verification regime on the same substrate. Built in sequence, each one harder than the last.

**[001 — Bonded File Transform](https://github.com/selfradiance/agentgate-bonded-file-transform)** · Deterministic verification — machine checks machine. 60 tests.

**[002 — File Guardian](https://github.com/selfradiance/agentgate-bonded-file-guardian)** · Command-based verification + rollback on failure. 50 tests.

**[003 — Email Rewriter](https://github.com/selfradiance/agentgate-bonded-email-rewriter)** · Human judgment in the loop — human decides pass/fail. 11 tests.

**[004 — Red Team Simulator](https://github.com/selfradiance/agentgate-red-team-simulator)** · Adversarial probing against live AgentGate from the outside over HTTP. Five stages: solo attacker → adaptive → recursive → coordinated team → 9-agent swarm. Includes Sleeper Agent (v0.6.0) for temporal reconnaissance. 330 tests.

**[005 — Recursive Verifier](https://github.com/selfradiance/agentgate-recursive-verifier)** · Proof-style verification — generates executable scripts, runs them in a sandbox, scores outcomes, iterates. Three modes: test, review, design. 149 tests.

**[006 — Incentive Wargame](https://github.com/selfradiance/agentgate-incentive-wargame)** · Stress-tests incentive rules with AI-generated economic strategies. Found a real contribution-cap bug in its own governance rules. 301 tests.

---

## Governance Extensions

**[Delegation Identity Proof](https://github.com/selfradiance/agentgate-delegation-proof)** · Bounded human-to-agent delegation with dual bonds and a 6-state machine. Who delegated what authority to which agent, under what scope. v0.1.0 shipped. 88 tests.

**[MCP Firewall](https://github.com/selfradiance/agentgate-mcp-firewall)** · Governance proxy for MCP tool calls. Sits between MCP clients and servers, requires bonded authorization before forwarding, slashes on bad outcomes. v0.1.0 shipped. 36 tests.

**[Epistemic Poisoning Simulato](https://https://github.com/selfradiance/agentgate-epistemic-poisoning)r** · Tests whether bond-and-slash can govern knowledge integrity — a saboteur agent corrupts shared knowledge to cause a target agent to make catastrophic mistakes. v0.1.0 shipped. 129 tests.

---

## Standards

**[RestaRules](https://github.com/selfradiance/restarules)** · Machine-readable agent conduct rules for restaurants. A `/.well-known/restarules.json` discovery model with formal decision procedures. A different angle on the same question: how do environments publish enforceable norms for AI agents?

---

## Why This Exists

Most agent systems rely on a binary trust model: either the agent has access or it doesn't, either it's authenticated or it isn't, either the model is "safe" or it isn't.

I'm building toward a missing middle layer: economic accountability, delegated authority with scope, runtime enforcement, tool governance, and knowledge integrity.

---

## Where to Start

1. **[AgentGate](https://github.com/selfradiance/agentgate)** — the core engine
2. **[Red Team Simulator](https://github.com/selfradiance/agentgate-red-team-simulator)** — what happens when you attack it
3. **[MCP Firewall](https://github.com/selfradiance/agentgate-mcp-firewall)** — how it connects to what the industry is deploying now
4. **[Recursive Verifier](https://github.com/selfradiance/agentgate-recursive-verifier)** — proof-style verification as a reusable tool

---

## Process

Every project goes through the same pipeline: multi-AI design audit (Claude, ChatGPT, Gemini, Grok in rotating roles), Claude Code implementation, 8-round Claude Code audit, Codex cold-eyes audit, and Claude Code cross-verification. I write companion articles on [Medium](https://medium.com/@selfradiance) and post shorter versions on X.

This GitHub is the canonical source for the actual builds.
