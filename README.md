# selfradiance

I build narrow proofs for governing AI agents before, during, and after they act.
This profile is a map of governed agent harness primitives: small local repos that
test one seam at a time. It is not a completed framework, not a platform, and not
a claim that agents are safe.

AgentGate remains central as the after-action accountability substrate: identity,
bonds, action records, settlement, slash/release. The wider ecosystem now also
touches before-ingestion, before-context, before-action, during-execution,
after-mutation, and adversarial-testing seams.

## Start here

If you're new, use this order:

1. [agentgate-governed-writefile-demo](https://github.com/selfradiance/agentgate-governed-writefile-demo) - the fastest outsider-readable proof path through governed `write_file`.
2. [agentgate-mcp-firewall](https://github.com/selfradiance/agentgate-mcp-firewall) - the narrow execution layer that checks whether governed filesystem calls produced the effects they claimed.
3. [agentgate](https://github.com/selfradiance/agentgate) - the deeper after-action accountability substrate underneath that path.

## Governed agent lifecycle map

These are narrow local proofs and partial proofs, not a finished harness. The fuller
topology is in [HARNESS_MAP.md](HARNESS_MAP.md).

- Before ingestion: [governed-repo-intake](https://github.com/selfradiance/governed-repo-intake), [SkillGate](https://github.com/selfradiance/skillgate), [mcp-config-inventory](https://github.com/selfradiance/mcp-config-inventory), [mcp-server-intake](https://github.com/selfradiance/mcp-server-intake), [dependency-drift-gate](https://github.com/selfradiance/dependency-drift-gate)
- Before context: [ContextGate](https://github.com/selfradiance/contextgate), [MemLedger](https://github.com/selfradiance/memledger)
- Before action: [ActionProof](https://github.com/selfradiance/ActionProof), [ActionWarrant](https://github.com/selfradiance/actionwarrant), [SecretBoundary](https://github.com/selfradiance/SecretBoundary), [reapproval-gate](https://github.com/selfradiance/reapproval-gate), [agent-intent-ledger](https://github.com/selfradiance/agent-intent-ledger), [restarules](https://github.com/selfradiance/restarules) as machine-readable venue/host conduct rules that can constrain proposed agent actions, not an enforcement layer by itself
- During execution: [agentgate-mcp-firewall](https://github.com/selfradiance/agentgate-mcp-firewall)
- After mutation: [rollback-receipt](https://github.com/selfradiance/rollback-receipt), [work-session-ledger](https://github.com/selfradiance/work-session-ledger)
- After action: [agentgate](https://github.com/selfradiance/agentgate), [agentgate-governed-writefile-demo](https://github.com/selfradiance/agentgate-governed-writefile-demo), [agentgate-delegation-proof](https://github.com/selfradiance/agentgate-delegation-proof), [agentgate-bonded-email-rewriter](https://github.com/selfradiance/agentgate-bonded-email-rewriter), [agent-007-bonded-email-triage](https://github.com/selfradiance/agent-007-bonded-email-triage), [agentgate-bonded-file-transform](https://github.com/selfradiance/agentgate-bonded-file-transform), [agentgate-bonded-file-guardian](https://github.com/selfradiance/agentgate-bonded-file-guardian)
- Adversarial testing: [agentgate-red-team-simulator](https://github.com/selfradiance/agentgate-red-team-simulator), [agentgate-recursive-verifier](https://github.com/selfradiance/agentgate-recursive-verifier), [agentgate-incentive-wargame](https://github.com/selfradiance/agentgate-incentive-wargame), [agentgate-epistemic-poisoning](https://github.com/selfradiance/agentgate-epistemic-poisoning)

## AgentGate arc

For the strongest current proof path, start with
[agentgate-governed-writefile-demo](https://github.com/selfradiance/agentgate-governed-writefile-demo).
Then read [agentgate-mcp-firewall](https://github.com/selfradiance/agentgate-mcp-firewall)
for the current filesystem-effect verification layer. Read
[agentgate](https://github.com/selfradiance/agentgate) after that if you want the
accountability engine underneath both; it is the substrate, not the first repo most
cold visitors should begin with.
