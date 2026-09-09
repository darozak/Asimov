# SOP PB-01: Researching, Drafting, Editing, and Publishing White Papers

**ID:** PB-01
**Title:** Researching, Drafting, Editing, and Publishing White Papers
**Category:** Publishing
**Revision:** 1.0
**Last updated:** 2026-09-09

## Purpose

To govern how the Asimov Project's research is documented as formal Markdown white
papers in this repository — from framing the research question through publication —
so that white papers are well-sourced, honestly qualified, consistently structured,
and reliable enough to serve as the basis for board and business-plan decisions.

## Applicability

This SOP applies to every white paper: its creation, each revision, its editorial
review, its publication, and its later supersession or withdrawal. It governs where
white papers are stored, how they are identified, their structure, and the states
they move through.

It does not govern informal research notes, internal memos, or the board's use of a
published paper. Detailed datasets or models supporting a paper may be kept as PB-01
attachments or alongside the paper in `White Papers/`.

This SOP is invoked when the User asks to start, revise, review, or publish a white
paper.

## Roles and Responsibilities

| Role | Responsibilities |
| ---- | ---------------- |
| User | Sets research priorities and approves the question and scope; reviews drafts; **approves publication**; decides whether to request board review; authorizes merges per AD-01; decides when a paper is superseded or withdrawn. |
| AI | Frames sub-questions; conducts and documents the research; drafts the paper from [PB-01-T1](../Attachments/PB-01-T1%20White%20Paper%20Template.md); self-edits against [PB-01-A1](../Attachments/PB-01-A1%20White%20Paper%20Review%20Checklist.md); maintains IDs, metadata, and the changelog; flags business-plan linkage; delivers all changes through [AD-01](./AD-01%20Posting%20and%20Responding%20to%20GitHub%20Issues.md). |
| Board | Optional reviewer. When review is requested, considers the paper and records its response; a paper does not require board approval to be published. |

## Required Resources

- Write access to this repository and the `gh` GitHub CLI, authenticated.
- [PB-01-T1 — White Paper Template](../Attachments/PB-01-T1%20White%20Paper%20Template.md)
- [PB-01-A1 — White Paper Review Checklist](../Attachments/PB-01-A1%20White%20Paper%20Review%20Checklist.md)
- [PB-01-M1 — Producing a White Paper Draft](../Attachments/PB-01-M1%20Producing%20a%20White%20Paper%20Draft.md)
- [AD-01 — Posting and Responding to GitHub Issues](./AD-01%20Posting%20and%20Responding%20to%20GitHub%20Issues.md)
- [QA-01 — Writing Standard Operating Procedures](./QA-01%20Writing%20Standard%20Operating%20Procedures.md)
- The `White Papers/` directory.

## General Guidelines

- Before using this SOP, the User and the AI must review the current version of this
  document in the repository to confirm it has not changed since last use.
- This SOP follows the formatting requirements defined in
  [QA-01](./QA-01%20Writing%20Standard%20Operating%20Procedures.md).
- After performing this SOP, the User and the AI actively identify any ways this SOP
  could be improved and post a GitHub issue for each one, following
  [AD-01](./AD-01%20Posting%20and%20Responding%20to%20GitHub%20Issues.md).
- White papers are Markdown and live in the top-level `White Papers/` directory. Each
  paper is a single file; its history is the changelog and Git, not parallel copies.
- Every change to a white paper is delivered through the AD-01 issue and branch
  workflow. White papers are never edited directly on `main`.
- Every factual claim must be traceable to a cited source. Never use a fabricated or
  unverified citation; mark unsupported claims as such or remove them.
- Keep findings separate from interpretation, and state limitations honestly. A white
  paper's authority comes from being trustworthy about its own uncertainty.
- Publication requires the User's approval. Board review is optional; when it occurs,
  record it in the paper's metadata. The paper does not need board approval to reach
  **Published**.
- When a published paper informs the business plan, note the linkage in the paper's
  **Discussion** and open an issue or AD-02 revision so the plan reflects it.

## Procedures

### 1. Assign an ID

1. IDs are `WP-YYYY-NN`: `YYYY` is the current year; `NN` is a two-digit, zero-padded
   sequence within that year, starting at `01`.
2. Choose `NN` by scanning `White Papers/` for the highest existing number for the
   current year and adding one. An ID, once assigned, is permanent.

### 2. Frame the research

1. With the User, state the research question, its sub-questions, the scope (in and
   out), and the intended audience (default: the board).
2. Confirm the paper is worth writing now and record the question in the issue that
   authorizes the work.

### 3. Research and draft

Follow [PB-01-M1 — Producing a White Paper Draft](../Attachments/PB-01-M1%20Producing%20a%20White%20Paper%20Draft.md):
frame the sub-questions, gather and document sources (primary sources for load-bearing
claims), outline for the User's review, then draft from
[PB-01-T1](../Attachments/PB-01-T1%20White%20Paper%20Template.md) with an inline
citation on every factual claim. Create the file as
`White Papers/<ID> <Title>.md` with **Status** `Draft`, **Version** `0.1`.

### 4. Name and store the file

- Name the file `<ID> <Title>.md` (for example, `WP-2026-01 Shared Accountability in
  Automated Decisions.md`).
- Store it in `White Papers/`.

### 5. Edit

1. Run the full [PB-01-A1 — White Paper Review Checklist](../Attachments/PB-01-A1%20White%20Paper%20Review%20Checklist.md)
   against the draft. Record the result and resolve every `FAIL` until the verdict is
   **READY**.
2. Set **Status** to `In Review` and present the draft, the PB-01-A1 result, and the
   source list to the User.
3. Apply the User's edits on the issue branch, bumping **Version** and adding a
   **Changelog** row for each round. Re-run PB-01-A1 after substantive changes.

### 6. Publish

1. When the User approves publication, set **Status** to `Published`, set
   **Last updated** to today, bump **Version** (to `1.0` on first publication), and
   add a **Changelog** row.
2. If the User requested board review, record the outcome in **Board review** before
   or after publication as directed.
3. Deliver through [AD-01](./AD-01%20Posting%20and%20Responding%20to%20GitHub%20Issues.md);
   merge on the User's explicit instruction.
4. If the paper informs the business plan, open the follow-up issue or AD-02 revision
   noted in **Discussion**.

### 7. Revise, supersede, or withdraw a published paper

- **Minor revision** (corrections, added sources): edit in place per §5, bump the
  MINOR version, add a **Changelog** row, keep **Status** `Published`.
- **Supersede**: when new work replaces a paper, publish the new paper with a
  `Supersedes` entry, and set the old paper's **Status** to `Superseded` with a
  `Superseded by` entry. Do not delete the old file.
- **Withdraw**: if a paper is found unsound and has no replacement, set **Status** to
  `Withdrawn`, add a **Changelog** row stating why, and note it wherever the paper was
  relied upon.

## References

- [PB-01-T1](../Attachments/PB-01-T1%20White%20Paper%20Template.md) — White Paper Template
- [PB-01-A1](../Attachments/PB-01-A1%20White%20Paper%20Review%20Checklist.md) — White Paper Review Checklist
- [PB-01-M1](../Attachments/PB-01-M1%20Producing%20a%20White%20Paper%20Draft.md) — Producing a White Paper Draft (machine instructions)
- [AD-01](./AD-01%20Posting%20and%20Responding%20to%20GitHub%20Issues.md) — Posting and Responding to GitHub Issues (workflow for delivering white paper changes)
- [AD-02](./AD-02%20Creating%20and%20Maintaining%20the%20Business%20Plan.md) — Creating and Maintaining the Business Plan (white papers inform plan revisions)
- [QA-01](./QA-01%20Writing%20Standard%20Operating%20Procedures.md) — Writing Standard Operating Procedures
