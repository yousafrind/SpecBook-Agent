# Instructions for tests and verification

- Tests should verify observable behaviour and stated acceptance criteria.
- Prefer deterministic tests with explicit setup and teardown.
- Cover expected behaviour, boundary conditions, and relevant failure paths.
- Keep unit, integration, contract, end-to-end, performance, and security tests distinguishable.
- Do not weaken or delete tests merely to make a change pass without an approved reason.
- Record commands and environment assumptions for important checks.
- Treat test success as evidence with limits, not proof of absence of defects.
- Never use production secrets or sensitive customer data in test fixtures.
- Report skipped, flaky, and unexecuted checks honestly.
