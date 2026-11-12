# Instructions for agent definitions

- Define each agent by a bounded responsibility and explicit non-responsibilities.
- Specify inputs, outputs, tools, permissions, and required context.
- State what evidence the agent must consult and how it should cite or reference it.
- Define approval gates and conditions requiring human escalation.
- Specify failure handling, retry limits, and what must never be done.
- Keep the agent's role distinct from reusable skills and directory instructions.
- Prefer deterministic scripts for deterministic transformations.
- Do not grant broad write, network, execution, or release permissions by default.
- Include evaluation cases before describing an agent as reliable or production-ready.
- Keep vendor-specific prompt or tool adapters separate from the agent's core contract.
