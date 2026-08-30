# Engineering Reliability into AI Agent Code Generation

A three-part field report for engineering leaders, architects, and practitioners deciding how to adopt AI agents for real software delivery.

It comes out of building and operating a multi-agent code-generation pipeline through real product deliveries — and out of one delivery in particular, where the pipeline reported **seven of seven work units passed, every requirement covered**, while the shipped UI looked dramatically different from the approved design. Every dashboard was green. The work was wrong.

The thesis, up front: **reliability in agent systems does not come from better prompts. It comes from treating agent output as untrusted input to an engineering system** — deterministic control flow, evidence-backed verification, and human judgment placed where it is cheap.

## Read it

| | |
|---|---|
| **[Part I — The Problems, the Patterns, and the Architecture](part-1-problems-patterns-architecture.md)** | Eight documented failure modes of agent code generation (context rot, self-assessed success, silent gate disengagement, …), a mapping onto the agentic-design-patterns catalog, and the high-level architecture: the control loop, the phase pipeline, the roles. |
| **[Part II — The Components](part-2-components.md)** | Each component in detail: deterministic guards, the evidence model, context engineering, adversarial evaluation, the connector contract, traceability, and escalation — plus the three proposed patterns in catalog form. |
| **[Part III — Teams of Agents, a Post-Mortem, and the Frontier](part-3-teams-casestudy-frontier.md)** | The team-of-agents layer (coordination that is never requested), the full false-green post-mortem, what remains unsolved, and an incremental adoption ladder. |

All diagrams are Mermaid and render directly on GitHub — no external images needed.

Every failure mode and design claim is backed by published research (arXiv, Anthropic engineering, METR, DORA, Google SRE); full reference lists at the end of each part.

## Three proposed patterns

Part II's appendix writes up three mechanisms in agentic-patterns-catalog form, proposed as first-class additions:

- **Deterministic Control Boundary** — workflow control stays in code; models act within states, never between them.
- **Evidence-Gated Progress** — no claim moves the system forward without an artifact a deterministic verifier can inspect.
- **Earned Capability** — a capability flag is true only when its backing artifacts exist; a check that cannot run records SKIPPED, never PASS — and where a reference exists, SKIPPED is a violation.

## Also published at

| | | |
|---|---|---|
| **Part I** | [dev.to](https://dev.to/sashua/engineering-reliability-into-ai-agent-code-generation-546d) | [Medium](https://oleksandrtranchenko.medium.com/engineering-reliability-into-ai-agent-code-generation-ba177b3e30a8) |
| **Part II** | [dev.to](https://dev.to/sashua/engineering-reliability-into-ai-agent-code-generation-part-ii-1d0d) | [Medium](https://oleksandrtranchenko.medium.com/engineering-reliability-into-ai-agent-code-generation-36d8060716ca) |
| **Part III** | [dev.to](https://dev.to/sashua/engineering-reliability-into-ai-agent-code-generation-part-iii-jdg) | [Medium](https://oleksandrtranchenko.medium.com/engineering-reliability-into-ai-agent-code-generation-989d9a4372ba) |

## Author

Alex — [LinkedIn](https://www.linkedin.com/in/oleksandr-tranchenko-ai/) AI engineer, team lead, the tech trailblazer

Questions, disagreements, and experience reports are welcome — open an issue.

## License

Text and diagrams © 2026, licensed under [CC BY-SA 4.0](LICENSE.md). Cite freely with attribution.
