# Verdict taxonomy — how each classification is decided

- **CORRECT_WITH_FAULTS** — every expected keyword (words > 2 chars) AND every
  expected number appear in the agent's answer. Numbers are matched separately:
  "8" would be filtered by a word-length rule but is exactly what tool outputs
  return.
- **DEGRADED** — the answer contains hedging markers ("unable", "failed",
  "something went wrong") — the agent noticed the fault and said so.
- **SILENT_FAILURE** — the answer lacks the expected data AND contains no
  hedging: a confident statement built on corrupted tool data. This is the
  metric that matters.
- **CRASHED** — empty answer; the loop died.
- **UNVERIFIABLE** — no expected outcome was provided for the scenario.
