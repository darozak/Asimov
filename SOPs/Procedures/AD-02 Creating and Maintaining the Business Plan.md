# SOP AD-02: Creating and Maintaining the Business Plan

**ID:** AD-02
**Title:** Creating and Maintaining the Business Plan
**Category:** Administration
**Revision:** 1.1
**Last updated:** 2026-09-09

## Purpose

To govern the Asimov Project's business plan as a dynamic, living Markdown document in
this repository, so that the plan always reflects the organization's current strategy,
is revised through reviewed changes, and records its own history.

The Asimov Project is a nonprofit whose mission is to promote legislation that fosters
the beneficial interaction of human and machine intelligences. The business plan is
the organization's primary strategic document.

## Applicability

This SOP applies to the creation of the business plan and to every subsequent change
to it, including scheduled reviews and ad hoc revisions. It governs where the plan is
stored, its structure, how changes are proposed and adopted, and the review cadence.

It does not set the organization's strategy — it defines how the strategy is
documented and maintained. Detailed financial models or appendices may be kept as
AD-02 attachments.

This SOP is invoked when the User asks to create, review, or revise the business
plan, or when a scheduled review falls due.

## Roles and Responsibilities

| Role | Responsibilities |
| ---- | ---------------- |
| User | Owns the organization's strategy; supplies and approves plan content; decides when a revision is adopted; authorizes merges per AD-01; sets the review cadence. |
| AI | Maintains the plan's structure against [AD-02-T1](../Attachments/AD-02-T1%20Business%20Plan%20Template.md); drafts and revises content at the User's direction; keeps the metadata block and changelog current; tracks the next review date and flags it when due; opens issues for open questions; delivers all changes through [AD-01](./AD-01%20Posting%20and%20Responding%20to%20GitHub%20Issues.md). |

## Required Resources

- Write access to this repository and the `gh` GitHub CLI, authenticated.
- [AD-02-T1 — Business Plan Template](../Attachments/AD-02-T1%20Business%20Plan%20Template.md)
- [AD-01 — Posting and Responding to GitHub Issues](./AD-01%20Posting%20and%20Responding%20to%20GitHub%20Issues.md)
- [QA-01 — Writing Standard Operating Procedures](./QA-01%20Writing%20Standard%20Operating%20Procedures.md)
- The living plan at `Business Plan/Asimov Business Plan.md`.

## General Guidelines

- Before using this SOP, the User and the AI must review the current version of this
  document in the repository to confirm it has not changed since last use.
- This SOP follows the formatting requirements defined in
  [QA-01](./QA-01%20Writing%20Standard%20Operating%20Procedures.md).
- After performing this SOP, the User and the AI actively identify any ways this SOP
  could be improved and post a GitHub issue for each one, following
  [AD-01](./AD-01%20Posting%20and%20Responding%20to%20GitHub%20Issues.md).
- The business plan is a single living document at `Business Plan/Asimov Business
  Plan.md`. There is one authoritative copy; superseded content is captured by the
  changelog and Git history, not by parallel versions.
- Every change to the plan is delivered through the AD-01 issue and branch workflow.
  The plan is never edited directly on `main`.
- Every adopted revision updates the metadata block (**Version**, **Last updated**,
  **Next review**) and adds a **Changelog** row. Use `MAJOR.MINOR`: MAJOR for a change
  in strategic direction, MINOR for refinements and updates.
- Keep the plan honest about its own gaps: unresolved items live in **Open Questions**
  with a linked GitHub issue for each.
- The plan conforms to the section skeleton in AD-02-T1. Do not delete a section; if
  it does not yet apply, mark it "To be developed" and record it in **Open
  Questions**.
- Published white papers (see
  [PB-01](./PB-01%20Researching%2C%20Drafting%2C%20Editing%2C%20and%20Publishing%20White%20Papers.md))
  are a primary evidence base for plan revisions. When a white paper changes the
  strategy, revise the affected sections per §2 and cite the paper.

## Procedures

### 1. Create the business plan (first time only)

1. Create the top-level `Business Plan/` directory.
2. Copy [AD-02-T1](../Attachments/AD-02-T1%20Business%20Plan%20Template.md) to
   `Business Plan/Asimov Business Plan.md` and remove the template guidance
   blockquote.
3. Set the metadata block: **Version** `0.1`, **Last updated** today, **Next review**
   a date the User chooses, **Owner**, **Status** `Draft`.
4. With the User, draft content for each section. Where a section cannot be completed,
   mark it "To be developed" and add an entry to **Open Questions**.
5. Add the first **Changelog** row (`0.1`, today, "Initial draft", issue/PR link).
6. Deliver through [AD-01](./AD-01%20Posting%20and%20Responding%20to%20GitHub%20Issues.md).

### 2. Revise the plan (ad hoc)

1. Confirm with the User the scope of the revision and whether it is MAJOR or MINOR.
2. On the issue branch, edit only the affected sections.
3. If the revision resolves an **Open Questions** item, remove it and close its issue;
   if it raises new ones, add them with linked issues.
4. Update the metadata block: bump **Version**, set **Last updated** to today, and set
   **Next review** if the cadence changed.
5. Add a **Changelog** row summarizing the change with the issue/PR link.
6. Update the **Executive Summary** if the change is material.
7. Deliver through AD-01.

### 3. Scheduled review

1. When today is on or after **Next review**, the AI raises it with the User and opens
   a review issue.
2. Walk each section with the User: is it still accurate, still the strategy, still
   supported by evidence? Note every section that needs work.
3. Apply the resulting edits as a revision per §2 (usually MINOR unless the review
   changes direction).
4. Set **Next review** to the next scheduled date even if little changed, and add a
   **Changelog** row recording that the review occurred.

### 4. Manage attachments

If the plan needs a detailed model or appendix (for example, a multi-year financial
projection), create it as an AD-02 attachment per
[QA-01](./QA-01%20Writing%20Standard%20Operating%20Procedures.md) §2 (for example,
`AD-02-A1` for an appendix, `AD-02-F1` for a form), store it in `SOPs/Attachments/`,
and link it from the relevant plan section and from **References** below.

## References

- [AD-02-T1](../Attachments/AD-02-T1%20Business%20Plan%20Template.md) — Business Plan Template (section skeleton the living plan conforms to)
- [Asimov Business Plan](../../Business%20Plan/Asimov%20Business%20Plan.md) — the living business plan this SOP maintains
- [AD-01](./AD-01%20Posting%20and%20Responding%20to%20GitHub%20Issues.md) — Posting and Responding to GitHub Issues (workflow for delivering plan changes)
- [PB-01](./PB-01%20Researching%2C%20Drafting%2C%20Editing%2C%20and%20Publishing%20White%20Papers.md) — Researching, Drafting, Editing, and Publishing White Papers (white papers inform plan revisions)
- [QA-01](./QA-01%20Writing%20Standard%20Operating%20Procedures.md) — Writing Standard Operating Procedures
- [IRS: Measuring Lobbying Activity — 501(c)(3)](https://www.irs.gov/charities-non-profits/measuring-lobbying-activity-substantial-part-test) — nonprofit lobbying limits relevant to the plan's policy strategy
