# Failure-mode notes

What each injected fault teaches about an agent under test:

- **timeout / connection_error** — does the agent hedge or invent? The most
  common real-world failure, and the cheapest to inject.
- **wrong_but_plausible** — the dangerous case: correct shape, wrong substance.
  A confident answer built on corrupted data is worse than a crash.
- **truncated / empty** — parsing robustness: does the loop feed the parse
  error back for self-correction or give up?
- **slow** — correct answer, delayed: latency budgeting under load.