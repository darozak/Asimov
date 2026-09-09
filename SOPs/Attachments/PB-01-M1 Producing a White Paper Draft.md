# PB-01-M1: Producing a White Paper Draft

> **Attachment:** PB-01-M1 — Machine Instructions
> **Parent SOP:** [PB-01](../Procedures/PB-01%20Researching%2C%20Drafting%2C%20Editing%2C%20and%20Publishing%20White%20Papers.md)
> **Audience:** Claude (AI). Read the whole file, then execute the steps in order.
> This procedure covers research through a self-edited draft (PB-01 §2–§5). It does
> not publish the paper — the User does that per PB-01 §6.

## When to run

Run when the User asks Claude to research and draft a white paper, or to advance an
existing Draft after a scope change.

## Inputs

- **Topic and question** — the research question, from the User or an approved issue.
- **Scope** — what is in and out of scope, and the intended audience (default: the
  board).
- **ID** — the `WP-YYYY-NN` ID assigned per PB-01 §2. If not yet assigned, propose one.
- **Issue branch** — created per [AD-01](../Procedures/AD-01%20Posting%20and%20Responding%20to%20GitHub%20Issues.md); all work happens there.

## Procedure

### Step 1 — Frame the question

1. Restate the research question, sub-questions, scope, and audience to the User.
2. Identify what kind of evidence would answer each sub-question (statutes, case law,
   peer-reviewed work, agency data, reputable reporting).
3. Get the User's confirmation before researching.

### Step 2 — Research

1. Gather sources for each sub-question. Prefer primary sources for load-bearing
   claims. Record for every source: full citation, URL if any, access date, and which
   sub-question it addresses.
2. Note where sources conflict or evidence is thin — these become **Limitations** and
   **Open Questions**.
3. Do not proceed to drafting until each sub-question has either supporting evidence
   or an explicit note that it cannot be answered from available sources.

### Step 3 — Outline

1. Create `White Papers/<ID> <Title>.md` from
   [PB-01-T1](./PB-01-T1%20White%20Paper%20Template.md); remove the guidance
   blockquote; fill the metadata block (Status `Draft`, Version `0.1`).
2. Under each section heading, write a bullet outline: the points to be made and, for
   Findings, which sources support each point.
3. Present the outline to the User and incorporate feedback before writing prose.

### Step 4 — Draft

1. Write each section from the outline. Attach an inline `[n]` citation to every
   factual claim and build the numbered **References** list as you go.
2. Keep authors' interpretation clearly separated from what the evidence shows.
3. Write **Limitations** honestly. Write **Recommendations** so each traces to a
   finding; for board recommendations, state the decision requested.
4. Write the **Abstract** last. Add the `0.1` **Changelog** row with the issue/PR
   link.

### Step 5 — Self-edit against PB-01-A1

1. Run the full [PB-01-A1 — White Paper Review Checklist](./PB-01-A1%20White%20Paper%20Review%20Checklist.md)
   against the draft.
2. Resolve every `FAIL`. Re-run until the checklist verdict is **READY**.
3. Verify all reference links resolve and every `[n]` marker has a matching entry.

### Step 6 — Hand off

1. Push the branch and open the pull request per AD-01.
2. Present to the User: the draft, the completed PB-01-A1 result, the source list, and
   a short note of the open questions and any recommended business-plan linkage.
3. Do not change Status beyond `Draft` / `In Review`. Publication is the User's step
   (PB-01 §6).

## Guardrails

- No fabricated citations. If a source cannot be located or verified, say so and treat
  the claim as unsupported.
- Quote and attribute third-party material; do not reproduce beyond fair use.
- Distinguish "no evidence found" from "evidence of absence".
- Stay within the organization's advocacy limits (see
  [AD-02](../Procedures/AD-02%20Creating%20and%20Maintaining%20the%20Business%20Plan.md) §13).

## References

- [PB-01](../Procedures/PB-01%20Researching%2C%20Drafting%2C%20Editing%2C%20and%20Publishing%20White%20Papers.md) — Researching, Drafting, Editing, and Publishing White Papers
- [PB-01-T1](./PB-01-T1%20White%20Paper%20Template.md) — White Paper Template
- [PB-01-A1](./PB-01-A1%20White%20Paper%20Review%20Checklist.md) — White Paper Review Checklist
- [AD-01](../Procedures/AD-01%20Posting%20and%20Responding%20to%20GitHub%20Issues.md) — Posting and Responding to GitHub Issues
