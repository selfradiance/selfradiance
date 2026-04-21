# selfradiance

I build narrow open-source proofs for AI agent accountability and governance. The work is organized around specific seams where agent systems fail: instruction intake, pre-execution policy, governed execution, delegated authority, bonded human judgment, substrate, and adversarial pressure. Each repo makes a deliberately small claim and stays local-first when possible.

## Start here

If you're new, use this order:

1. [agentgate-governed-writefile-demo](https://github.com/selfradiance/agentgate-governed-writefile-demo) — the fastest outsider-readable proof path through governed `write_file`
2. [agentgate-mcp-firewall](https://github.com/selfradiance/agentgate-mcp-firewall) — the verification layer that checks whether governed filesystem calls produced the effects they claimed
3. [agentgate](https://github.com/selfradiance/agentgate) — the deeper accountability substrate underneath that path

## Ecosystem map

### Instruction intake
- [governed-repo-intake](https://github.com/selfradiance/governed-repo-intake) — local deterministic intake gate for instruction-bearing repo surfaces; explicit human acknowledgment is required before approval, and approval is not a safety verdict

### Pre-execution policy gates
- [ActionProof](https://github.com/selfradiance/ActionProof) — deterministic allow/deny gate for one credentialed tool request before execution; asks whether a call should happen at all
- [SecretBoundary](https://github.com/selfradiance/SecretBoundary) — deterministic gate for one outbound webhook-style payload crossing explicit secret boundaries before execution

### Governed execution / effect verification
- [agentgate-governed-writefile-demo](https://github.com/selfradiance/agentgate-governed-writefile-demo) — smallest outsider-readable proof path through governed `write_file`: intended call, real on-disk effect, and inspectable audit artifacts
- [agentgate-mcp-firewall](https://github.com/selfradiance/agentgate-mcp-firewall) — thin governance proxy; on its current shipped proof surfaces it independently verifies two narrow filesystem effects (`write_file` and `delete_file`) instead of trusting upstream success claims

### Delegated authority
- [agentgate-delegation-proof](https://github.com/selfradiance/agentgate-delegation-proof) — bounded delegated authority with a checkpointed execution path and a local append-only transparency log; not tamper-evident anchoring

### Bonded human judgment
- [agentgate-bonded-email-rewriter](https://github.com/selfradiance/agentgate-bonded-email-rewriter) — bonded rewriting where a human approve/reject judgment settles the outcome
- [agent-007-bonded-email-triage](https://github.com/selfradiance/agent-007-bonded-email-triage) — bonded inbox triage where exact-category human correction settles the outcome

### Substrate
- [agentgate](https://github.com/selfradiance/agentgate) — collateralized execution engine and accountability substrate underneath much of the ecosystem

### Adversarial evaluation and simulation
- [agentgate-red-team-simulator](https://github.com/selfradiance/agentgate-red-team-simulator) — adversarial pressure against AgentGate from the outside
- [agentgate-recursive-verifier](https://github.com/selfradiance/agentgate-recursive-verifier) — recursive proof-oriented verifier; its strongest public path right now is pre-build API spec auditing
- [agentgate-incentive-wargame](https://github.com/selfradiance/agentgate-incentive-wargame) — stress-tests incentive systems under adversarial adaptive strategies
- [agentgate-epistemic-poisoning](https://github.com/selfradiance/agentgate-epistemic-poisoning) — poisoning simulation around decision integrity under bond
- [restarules](https://github.com/selfradiance/restarules) — machine-readable venue conduct rules for agents

## How these fit together

AgentGate is the substrate. Some repos govern what instruction-bearing material gets admitted before work starts. Some ask whether a tool call should happen at all. MCP Firewall then handles a narrower and different question: whether a governed filesystem call produced the effect it claimed after execution on its current proof surfaces. Other repos explore bounded delegation, bonded human judgment, or adversarial pressure. The point is layered narrow proofs, not one giant framework.

## Strongest proof path right now

For the fastest concrete entry point, start with [agentgate-governed-writefile-demo](https://github.com/selfradiance/agentgate-governed-writefile-demo). If you want the current filesystem verification layer behind that demo, read [agentgate-mcp-firewall](https://github.com/selfradiance/agentgate-mcp-firewall) next. If you want the deeper engine underneath both, read [agentgate](https://github.com/selfradiance/agentgate) after that. It is the substrate, not the first repo most cold visitors should begin with.

## Other notable projects
- [agentgate-bonded-file-transform](https://github.com/selfradiance/agentgate-bonded-file-transform) — early deterministic verification proof on the same substrate
- [agentgate-bonded-file-guardian](https://github.com/selfradiance/agentgate-bonded-file-guardian) — command-based file verification with rollback on failure
