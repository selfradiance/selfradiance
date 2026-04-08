selfradiance - 
Open-source reference implementations for runtime accountability in AI agent systems.
I started building about a month ago from zero coding background — I direct AI coding tools (primarily Claude Code) and make the design and architecture decisions myself. What I care about is a simple question:
How do we make autonomous agents economically accountable for what they do, what they're allowed to do, and what happens when they fail?

The Core
AgentGate — a collateralized execution engine for AI agents. Before an agent can take a high-impact action, it must post a bond as collateral. Good behavior releases the bond. Bad behavior slashes it. Ed25519 signed identities, reusable bonds, progressive trust tiers, prediction markets, and an auto-slash sweeper.
Everything below is built on top of AgentGate or extends its model.

Reference Agents — A Progressive Build
Each agent proves a different verification regime on the same substrate. They were built in sequence, each one harder than the last.
#AgentWhat it provesRepo001Bonded File TransformDeterministic verification — machine checks machineagentgate-bonded-file-transform002File GuardianCommand-based verification + rollback on failureagentgate-bonded-file-guardian003Email RewriterHuman judgment in the loop — human decides pass/failagentgate-bonded-email-rewriter004Red Team SimulatorAdversarial probing against live AgentGate from the outside over HTTP. Five stages: solo attacker → adaptive → recursive → coordinated team → 9-agent swarm. Includes Sleeper Agent (v0.6.0) for temporal reconnaissance.agentgate-red-team-simulator005Recursive VerifierProof-style verification — generates executable verification scripts, runs them in a sandbox, scores outcomes, iteratesagentgate-recursive-verifier006Incentive WargameStress-tests incentive rules with AI-generated economic strategies. Found a real contribution-cap bug in its own governance rules.agentgate-incentive-wargame

Governance Extensions
ProjectWhat it addsStatusRepoDelegation Identity ProofBounded human-to-agent delegation with dual bonds and a 6-state machine. Who delegated what authority to which agent, under what scope.v0.1.0 shippedagentgate-delegation-proofMCP FirewallGovernance proxy for MCP tool calls. Sits between MCP clients and servers, requires bonded authorization before forwarding, slashes on bad outcomes.v0.1.0 shippedagentgate-mcp-firewallEpistemic Poisoning SimulatorTests whether bond-and-slash can govern knowledge integrity — a saboteur agent corrupts shared knowledge to cause a target agent to make catastrophic mistakes.Design stage—

Standards / Protocol Work
RestaRules — machine-readable agent conduct rules for restaurants. A /.well-known/restarules.json discovery model with formal decision procedures. A different angle on the same question: how do environments publish enforceable norms for AI agents?

Why This Exists
Most agent systems still rely on a binary trust model: either the agent has access or it doesn't, either it's authenticated or it isn't, either the model is "safe" or it isn't.
I'm building toward a missing middle layer:

Economic accountability — bad actions cost something
Delegated authority with scope — not just identity, but bounded permission
Runtime enforcement — not policy documents, but code that runs
Tool governance — MCP calls go through a checkpoint, not an open pipe
Knowledge integrity — what happens when the data itself is poisoned


Where to Start

AgentGate — the core engine
Red Team Simulator — what happens when you attack it
MCP Firewall — how it connects to what the industry is deploying now
Recursive Verifier — proof-style verification as a reusable tool


Process
Every project goes through the same pipeline: multi-AI design audit (Claude, ChatGPT, Gemini, Grok in rotating roles), Claude Code implementation, 8-round Claude Code audit, Codex cold-eyes audit, and Claude Code cross-verification. I write companion articles on Medium and post shorter versions on X.
This GitHub is the canonical source for the actual builds.

<!--
**selfradiance/selfradiance** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
