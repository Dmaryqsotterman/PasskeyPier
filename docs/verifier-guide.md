# Consuming a report from a verifier (sketch)

A proposal for discussion. The lab produces reports; this is about the other half -
what a relying party or a verifier is supposed to do with one.

## The shape of the decision

A report answers one question: did the ceremonies in it behave the way the
specification says they must? Everything else a caller needs is already in the
report, but three things are worth spelling out.

### 1. Read the verdict, not the counts

```json
{ "result": "findings present", "exitCode": 1 }
```

`exitCode` is what the process returned. If a report is archived from CI, that
field is the answer; a caller that recomputes a verdict from the finding list will
eventually disagree with the tool.

### 2. Treat an absent scenario as a gap, not a pass

A report covers the scenarios that ran. If a deployment only runs the honest
ceremony, an attacker-focused scenario is not "passing" - it did not run. The
matrix in `docs/SPEC.md` section 8 is the list to check against.

### 3. A failed ceremony is data about the artifact, not about the lab

When a scenario fails because the artifact under test does the wrong thing, the
report is doing its job. The failure has to survive the pipeline; it is the
finding, not noise around it.

## Open questions

- Should the report carry the scenario list it covered, so a caller can detect a
  gap without knowing the expected list out of band?
- Is there a place for a machine-readable per-scenario verdict, or is the finding
  list enough?
- Do we need to say which specification revision the scenarios were written
  against?
