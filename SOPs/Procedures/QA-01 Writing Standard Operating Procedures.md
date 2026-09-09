# SOP QA-01: Writing Standard Operating Procedures

**ID:** QA-01
**Title:** Writing Standard Operating Procedures
**Category:** Quality Assurance
**Revision:** 1.0
**Last updated:** 2026-09-09

## Purpose

To define how Standard Operating Procedures (SOPs) for The Asimov Project are
numbered, structured, named, stored, and maintained, so that every SOP is
consistent, discoverable, and safe to act on for both the User and the AI.

## Applicability

This SOP applies to the creation of any new SOP, the revision of any existing SOP,
and the creation or revision of any attachment to an SOP. It applies to every SOP
category defined below. Every other SOP in the repository is required to conform to
this document.

This SOP is invoked whenever the User asks for a new or updated SOP, or when the AI
proposes one.

## Roles and Responsibilities

| Role | Responsibilities |
| ---- | ---------------- |
| User | Requests new or revised SOPs; supplies the subject-matter content and intent; reviews and approves the draft; confirms the assigned ID does not collide with an existing SOP. |
| AI | Applies this SOP; assigns the correct ID and category; drafts the SOP from the current template ([QA-01-T1](../Attachments/QA-01-T1%20Standard%20Operating%20Procedure%20Template.md)); names and files the SOP and its attachments correctly; ensures all References resolve as hyperlinks; flags conflicts or ambiguities to the User. |

## Required Resources

- Write access to this repository.
- [QA-01-T1 — Standard Operating Procedure Template](../Attachments/QA-01-T1%20Standard%20Operating%20Procedure%20Template.md)
- The `SOPs/Procedures/` directory (all SOPs).
- The `SOPs/Attachments/` directory (all attachments).
- A Markdown editor or viewer capable of rendering GitHub-flavored Markdown.

## General Guidelines

- Before using this SOP, the User and the AI must review the current version of this
  document in the repository to confirm it has not changed since last use.
- This SOP follows the formatting, numbering, and structural requirements defined in
  QA-01 (this document).
- Write all SOPs in Markdown using GitHub-flavored Markdown elements. Do not use
  word-processor-style formatting.
- Keep language concrete and imperative. Prefer numbered steps for anything that is
  performed in sequence.
- When revising an SOP, increment its **Revision** and update its **Last updated**
  date. Do not change an SOP's ID once assigned, even if its title changes.
- If a required template or referenced attachment does not yet exist, create it in
  `SOPs/Attachments/` as part of the same change.

## Procedures

### 1. Determine the category and assign an ID

1. Identify the SOP's category and its two-character designator:

   | Category | Designator |
   | -------- | ---------- |
   | Quality Assurance | `QA` |
   | Administration | `AD` |
   | Publishing | `PB` |

2. Assign an ID in the format `CC-NN`:
   - `CC` is the two-character category designator from the table above.
   - `NN` is a two-digit, zero-padded number that distinguishes SOPs within that
     category (`01`, `02`, … `10`, …).
3. Choose `NN` by scanning `SOPs/Procedures/` for the highest existing number in that
   category and adding one. Confirm with the User that the number is not already
   reserved. An ID, once assigned, is permanent.

### 2. Assign IDs to attachments

Many SOPs have attachments. Number each attachment `CC-NN-XN`:

- `CC-NN` is the ID of the SOP the attachment belongs to.
- `X` is the attachment-type code:

  | Attachment type | Code |
  | --------------- | ---- |
  | Template | `T` |
  | Appendix | `A` |
  | Form | `F` |
  | Machine Instructions | `M` |
  | Scripts | `S` |

- `N` is a one-based sequential number **within that attachment type** for that SOP
  (for example, the first template is `-T1`, the second is `-T2`; the first form is
  `-F1`).

Give each attachment the file type that suits its intended use (for example, `.md`
for a template, `.csv` or `.md` for a form, `.sh` or `.py` for scripts, `.json` or
`.yaml` for machine instructions). There is no requirement that attachments be
Markdown.

### 3. Name the files

Name every SOP and attachment file with its ID followed by a space and its title,
using the file type appropriate to the document:

- SOP: `CC-NN <Title>.md`
  — e.g. `QA-01 Writing Standard Operating Procedures.md`
- Attachment: `CC-NN-XN <Title>.<ext>`
  — e.g. `QA-01-T1 Standard Operating Procedure Template.md`

### 4. Store the files

- Place every SOP in `SOPs/Procedures/`.
- Place every attachment in `SOPs/Attachments/`.

### 5. Draft the SOP from the template

1. Copy [QA-01-T1](../Attachments/QA-01-T1%20Standard%20Operating%20Procedure%20Template.md)
   into `SOPs/Procedures/` and rename it per step 3.
2. Complete every one of the following required sections, in this order:

   | Section | Contents |
   | ------- | -------- |
   | Title | The SOP's ID and title, plus the ID / Title / Category / Revision / Last updated metadata block. |
   | Purpose | Why the SOP exists and what outcome it guarantees. |
   | Applicability | When the SOP applies, who invokes it, what triggers it, and what is out of scope. |
   | Roles and Responsibilities | Each role and what it is accountable for. |
   | Required Resources | Files, tools, access, templates, and reference documents needed. |
   | General Guidelines | Standing rules (see step 3 below for mandatory entries). |
   | Procedures | The ordered steps to execute the procedure. |
   | References | Associated attachments first, then other relevant documents; all hyperlinked. |

3. In **General Guidelines**, include these two entries in every SOP:
   - A guideline requiring the User and the AI to review the current version of the
     SOP in the repository before use, in case it has changed.
   - A guideline stating that the SOP follows the formatting requirements defined in
     [QA-01](./QA-01%20Writing%20Standard%20Operating%20Procedures.md).
4. In **References**, list each associated attachment by ID and title, then any other
   relevant documents. Every entry must be a working hyperlink (relative links for
   files in this repository, absolute URLs for external documents).
5. Remove all template guidance notes and bracketed placeholders.

### 6. Review and finalize

1. Verify the ID is unique, the file is named and located per steps 3–4, and all
   eight sections are present and complete.
2. Verify every link in **References** resolves.
3. Present the draft to the User for approval.
4. On approval, commit the SOP and any new or changed attachments together.

## References

- [QA-01-T1](../Attachments/QA-01-T1%20Standard%20Operating%20Procedure%20Template.md) — Standard Operating Procedure Template (required structure for all SOPs)
- [GitHub Flavored Markdown Spec](https://github.github.com/gfm/) — Markdown formatting reference
