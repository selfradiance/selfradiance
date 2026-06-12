# Governed Agent Harness Map

This is an evolving map of narrow, local proof repos exploring how AI-agent work
can be governed before, during, and after action. It is not a completed framework,
not a safety claim, and not a platform. Its purpose is to make covered seams,
partial seams, and unresolved seams visible so future builds can be selected
deliberately.

## Purpose

The thesis is simple: narrow proofs for governing AI agents before, during, and
after they act. Each repo should make one modest claim, expose its limits, and
stay useful to real human-agent supervision work.

AgentGate is still the after-action accountability substrate: identity, bonds,
action records, settlement, slash/release. The map around it asks what has to be
checked before work enters the system, before context is assembled, before a tool
call happens, during execution, after local mutation, and under adversarial
pressure.

## Lifecycle seam map

- Before ingestion: decide what instruction-bearing or dependency-bearing material may enter the work surface.
- Before context: decide what memory, repo state, and prior work should be assembled for the agent.
- Before action: decide whether a specific proposed action is allowed, warranted, or needs reapproval.
- During execution: observe or mediate the action while it is being attempted.
- After mutation: record what changed and whether rollback material exists.
- After action: settle accountability against identity, bonds, records, and human judgment.
- Adversarial testing: pressure the assumptions, incentives, and proof paths.

## Current selection state

- No new build is selected by this map.
- `policy-conflict-receipt` is shipped and covered under the before-action policy conflict seam.
- `agent-interrupt-receipt` is shipped and covered under the before-action human interruption semantics seam.
- `mcp-config-inventory` is shipped through released `v0.2.0`; do not treat the drift-diff release as local-only or unreleased.
- Claude's observed-effect receipt idea is parked pending a narrower spec; `observed-effect-receipt`, `rollback-chain`, `work-session-ledger v0.2`, `dependency-drift-gate v0.2`, and new repos are not selected by this audit.
- Maintenance-only source-of-truth cleanup is an acceptable outcome when it prevents stale notes from reselecting already-shipped work.
- Pause builds after this maintenance cleanup.

## Covered seams

### Before ingestion

- [governed-repo-intake](https://github.com/selfradiance/governed-repo-intake) - local intake gate for instruction-bearing repo surfaces.
- [SkillGate](https://github.com/selfradiance/skillgate) - narrow review surface for agent skill material before use.
- [mcp-config-inventory](https://github.com/selfradiance/mcp-config-inventory) - inventory and drift-diff of MCP config exposure before agent work; released through `v0.2.0`.
- [mcp-server-intake](https://github.com/selfradiance/mcp-server-intake) - intake proof for MCP server/package review.
- [dependency-drift-gate](https://github.com/selfradiance/dependency-drift-gate) - local review of dependency drift before accepting changes.

### Before context

- [ContextGate](https://github.com/selfradiance/contextgate) - narrow gate for context assembly decisions.
- [MemLedger](https://github.com/selfradiance/memledger) - ledger-oriented proof for memory admission and review.

### Before action

- [ActionProof](https://github.com/selfradiance/ActionProof) - deterministic allow/deny gate for one credentialed tool request.
- [ActionWarrant](https://github.com/selfradiance/actionwarrant) - warrant-style proof for a proposed agent action.
- [SecretBoundary](https://github.com/selfradiance/SecretBoundary) - deterministic gate for one outbound payload crossing explicit secret boundaries.
- [reapproval-gate](https://github.com/selfradiance/reapproval-gate) - local proof for deciding when a changed situation needs fresh approval.
- [agent-intent-ledger](https://github.com/selfradiance/agent-intent-ledger) - ledger for stated intent before or around action.
- [policy-conflict-receipt](https://github.com/selfradiance/policy-conflict-receipt) - local deterministic CLI that compares one proposed agent action against declared policy/source constraints and emits a conflict receipt before execution.
- [agent-interrupt-receipt](https://github.com/selfradiance/agent-interrupt-receipt) - before-action interrupt receipt for later human instructions overriding or narrowing an active work order.
- [restarules](https://github.com/selfradiance/restarules) - machine-readable venue/host conduct rules that can constrain proposed agent actions; not an enforcement layer by itself.

### During execution

- [agentgate-mcp-firewall](https://github.com/selfradiance/agentgate-mcp-firewall) - thin governance proxy for narrow filesystem-effect verification.

### After mutation

- [rollback-receipt](https://github.com/selfradiance/rollback-receipt) - proof around rollback material after local change.
- [work-session-ledger](https://github.com/selfradiance/work-session-ledger) - ledger for work-session records and handoff material.

### After action

- [agentgate](https://github.com/selfradiance/agentgate) - accountability substrate for identity, bonds, action records, settlement, slash/release.
- [agentgate-governed-writefile-demo](https://github.com/selfradiance/agentgate-governed-writefile-demo) - small proof path through intended write, actual effect, and audit artifacts.
- [agentgate-delegation-proof](https://github.com/selfradiance/agentgate-delegation-proof) - delegated-authority checkpoint that spans pre-action scope checks and after-action AgentGate settlement.
- [agentgate-bonded-email-rewriter](https://github.com/selfradiance/agentgate-bonded-email-rewriter) - bonded rewriting settled by human approve/reject judgment.
- [agent-007-bonded-email-triage](https://github.com/selfradiance/agent-007-bonded-email-triage) - bonded inbox triage settled by exact-category human correction.
- [agentgate-bonded-file-transform](https://github.com/selfradiance/agentgate-bonded-file-transform) - early deterministic verification proof on the AgentGate substrate.
- [agentgate-bonded-file-guardian](https://github.com/selfradiance/agentgate-bonded-file-guardian) - command-based file verification with rollback on failure.

### Adversarial testing

- [agentgate-red-team-simulator](https://github.com/selfradiance/agentgate-red-team-simulator) - adversarial pressure against AgentGate from the outside.
- [agentgate-recursive-verifier](https://github.com/selfradiance/agentgate-recursive-verifier) - design-time adversarial spec auditor; listed here because it pressure-tests assumptions before implementation.
- [agentgate-incentive-wargame](https://github.com/selfradiance/agentgate-incentive-wargame) - incentive-system stress tests under adaptive strategies.
- [agentgate-epistemic-poisoning](https://github.com/selfradiance/agentgate-epistemic-poisoning) - poisoning simulation around decision integrity under bond.

## Partially Covered Seams

- Human-agent handoff receipts - touched by work-session and bonded-demo records, not generalized.
- Session assembly - adjacent to ContextGate and MemLedger, not a full session authority model.
- Rollback preparation - explored in rollback-receipt and file-guardian paths, not chained rollback orchestration.
- Reapproval thresholds - explored in reapproval-gate, not settled across tools or time.
- Intent drift detection - adjacent to agent-intent-ledger, not a complete drift detector.
- Dependency drift review - covered locally by dependency-drift-gate, not a broad supply-chain review system.
- MCP config/package intake - covered by inventory and intake proofs, not runtime containment.

## Unresolved / Intentionally Absent Seams

- Approval UX
- Runtime containment / sandboxing
- Long-running task supervision
- Delegated memory authority
- Capability leasing
- Scoped credential issuance
- Trust decay
- Rollback orchestration chains
- Provenance across chained agents
- Multi-agent coordination governance
- Semantic drift across planning layers
- Production authorization integration
- Hosted service / dashboard

## Non-goals

- Not a finished agent framework
- Not a SaaS product
- Not a general AI safety claim
- Not a malware/vulnerability scanner suite
- Not proof that agents are safe
- Not a replacement for sandboxing, auth, or production security controls

## Build-selection rule

Future builds should fill a visible seam only if they pass:

- One narrow claim
- Local-first where possible
- Runnable demo
- Tests/typecheck/build verification
- Honest README
- Explicit non-goals
- Maps to a named lifecycle seam, partial seam, or intentionally absent seam
- Useful to James's own human-agent supervision workflow
- No broad framework claims
- No assumption that a visible gap automatically authorizes a build
