# QA-01-M1: SOP Compliance Inspection

> **Attachment:** QA-01-M1 — Machine Instructions
> **Parent SOP:** [QA-01](../Procedures/QA-01%20Writing%20Standard%20Operating%20Procedures.md)
> **Audience:** Claude (AI). These are machine instructions: read the whole file,
> then execute every step in order and report the result.

## When to run

Run this inspection whenever a new SOP is drafted, an existing SOP is revised, or the
User asks for an SOP to be checked. It is invoked as part of QA-01 §6 ("Review and
finalize") and may also be run on its own.

## Inputs

- **Target SOP** — the path to the SOP file under review (in `SOPs/Procedures/`).
- **Repository state** — the current contents of `SOPs/Procedures/` and
  `SOPs/Attachments/`.
- **Reference SOP** — the current version of
  [QA-01](../Procedures/QA-01%20Writing%20Standard%20Operating%20Procedures.md) and
  the template
  [QA-01-T1](./QA-01-T1%20Standard%20Operating%20Procedure%20Template.md).

## Procedure

### Step 0 — Load context

1. Re-read the current version of `QA-01` and `QA-01-T1` from the repository. Do not
   rely on memory; they may have changed.
2. Read the full text of the target SOP.
3. List every file currently in `SOPs/Procedures/` and `SOPs/Attachments/`.

### Step 1 — Compliance checks (against QA-01)

Evaluate each check. Record `PASS`, `FAIL`, or `N/A`. For every `FAIL`, record the
exact location (section, line, or filename) and a concrete suggested fix.

| # | Check |
| - | ----- |
| C1 | **ID format** — the SOP's ID matches `^(QA|AD|PB)-\d{2}$`. The category word in the metadata block matches the designator (QA→Quality Assurance, AD→Administration, PB→Publishing). |
| C2 | **ID uniqueness** — no other file in `SOPs/Procedures/` uses this ID. If this is a revision, the ID is unchanged from the previous version. |
| C3 | **Location** — the SOP file is in `SOPs/Procedures/`. Every attachment it defines or references is in `SOPs/Attachments/`. |
| C4 | **File name** — the SOP file is named `<ID> <Title>.md`. The `<Title>` in the filename matches the **Title** in the document (allowing for characters not permitted in filenames). |
| C5 | **Markdown format** — the file is GitHub-flavored Markdown: headings use `#`, lists use `-`/`1.`, emphasis uses `*`/`**`. No HTML-only or word-processor constructs. |
| C6 | **Metadata block** — the document states ID, Title, Category, Revision, and Last updated. "Last updated" is an ISO date (`YYYY-MM-DD`). |
| C7 | **Required sections present** — all eight headings exist: `Purpose`, `Applicability`, `Roles and Responsibilities`, `Required Resources`, `General Guidelines`, `Procedures`, `References` (plus the title block). |
| C8 | **Section order** — the eight sections appear in the QA-01 order, with no extra top-level sections interleaved. |
| C9 | **Mandatory General Guidelines** — the **General Guidelines** section contains (a) a guideline requiring the User and the AI to review the current version of the SOP before use in case it changed, (b) a guideline stating the SOP follows QA-01 for formatting requirements, and (c) a guideline requiring the User and the AI, after performing the SOP, to actively identify ways the SOP could be improved and post a GitHub issue for each, following AD-01. |
| C10 | **References QA-01** — the SOP links to `QA-01` at least once (in General Guidelines and/or References). The target SOP itself may be QA-01, in which case the self-reference is expected; mark `N/A` for the "links to" wording but confirm it still states it defines its own rules. |
| C11 | **Attachment IDs** — every attachment defined or referenced matches `^(QA|AD|PB)-\d{2}-[TAFMS]\d+$`, the `CC-NN` portion matches this SOP's ID, and the per-type numbers are sequential from 1 with no gaps or duplicates. |
| C12 | **Attachment naming & location** — each attachment file is named `<attachment-ID> <Title>.<ext>` and lives in `SOPs/Attachments/`. The extension suits the attachment's purpose. |
| C13 | **References completeness** — every attachment of this SOP is listed in **References**; attachments are listed before other documents. |
| C14 | **Hyperlinks resolve** — every link in **References** (and elsewhere in the SOP) is a real hyperlink. Repo links are relative and point to a file that exists; external links are absolute URLs. Flag any bare filename or plain-text reference that should be a link. |
| C15 | **Template residue removed** — no `[bracketed placeholders]`, no "Note to AI" / "How to use this template" guidance blocks, no `CC-NN` literal left unresolved. |

### Step 2 — Consistency checks (against existing SOPs)

Compare the target SOP with the other SOPs already in `SOPs/Procedures/`. Record
`PASS`/`FAIL`/`N/A` with location and suggested fix for each `FAIL`. If the target is
the only SOP in the directory, mark all of Step 2 `N/A`.

| # | Check |
| - | ----- |
| K1 | **Structural style** — heading levels, the metadata-block layout, and table vs. list choices match the prevailing style of existing SOPs. |
| K2 | **Terminology** — role names and key terms match those used elsewhere (e.g. "User" and "AI", not "operator"/"assistant"/"the model" if the others say "User"/"AI"). |
| K3 | **Scope overlap** — the SOP's Purpose and Applicability do not duplicate or contradict an existing SOP's scope. If it supersedes another SOP, that is stated explicitly. |
| K4 | **Category fit** — the chosen category matches how similar existing SOPs are categorized. |
| K5 | **Bidirectional cross-references** — if this SOP references another SOP for a shared step, and that relationship should be mutual, the other SOP references back (note as a follow-up if editing the other SOP is out of scope). |
| K6 | **Numbering continuity** — `NN` is the next unused number in its category, not an arbitrary jump. |

### Step 3 — Report

Produce a report in this exact shape:

```
# QA-01-M1 Compliance Inspection — <SOP ID> <Title>
Inspected: <YYYY-MM-DD>
QA-01 revision referenced: <revision>

## Compliance (QA-01)
C1  ID format ............................ PASS
C2  ID uniqueness ........................ FAIL — SOPs/Procedures/ already has "AD-02 ...". Renumber to AD-03.
...

## Consistency (existing SOPs)
K1  Structural style ..................... PASS
...

## Verdict
NOT COMPLIANT — 2 failures (C2, K3). Fix and re-run QA-01-M1.
```

Rules for the verdict:

- **COMPLIANT** — every check is `PASS` or `N/A`.
- **NOT COMPLIANT** — one or more `FAIL`. List the failing check IDs.

Do not modify the target SOP as part of this inspection. Report only. Apply fixes only
if the User asks, and re-run this inspection afterward.

## References

- [QA-01](../Procedures/QA-01%20Writing%20Standard%20Operating%20Procedures.md) — Writing Standard Operating Procedures
- [QA-01-T1](./QA-01-T1%20Standard%20Operating%20Procedure%20Template.md) — Standard Operating Procedure Template
- [AD-01](../Procedures/AD-01%20Posting%20and%20Responding%20to%20GitHub%20Issues.md) — Posting and Responding to GitHub Issues (referenced by mandatory General Guideline C9c)
