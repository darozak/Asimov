# SOP AD-01: Posting and Responding to GitHub Issues

**ID:** AD-01
**Title:** Posting and Responding to GitHub Issues
**Category:** Administration
**Revision:** 1.0
**Last updated:** 2026-09-09

## Purpose

To define how issues are posted to the project's GitHub repository and how open issues
are addressed, so that every change is proposed on its own branch, reviewed by the
User before it reaches `main`, and merged only on the User's explicit instruction.

## Applicability

This SOP applies whenever an issue is filed on the repository and whenever the User
asks Claude to address, work, or resolve an open issue. It governs branch creation,
pushing changes for review, merging, and branch cleanup for issue work. It does not
govern changes made outside the issue process.

This SOP is invoked when the User says, in effect, "post an issue for …" or "address
issue #N".

## Roles and Responsibilities

| Role | Responsibilities |
| ---- | ---------------- |
| User | Files or requests issues; confirms the scope of an issue before work begins; reviews the pushed branch and requests changes; gives explicit authorization to merge a specific branch into `main`; decides when an issue is done. |
| AI | Writes well-formed issues; confirms scope with the User; creates one branch per issue; makes all issue changes on that branch; runs [QA-01-M1](../Attachments/QA-01-M1%20SOP%20Compliance%20Inspection.md) when the work touches an SOP; pushes the branch and a pull request for review; iterates on feedback; merges **only** when the User instructs it; deletes the merged branch; posts a closing summary comment. |

## Required Resources

- Write access to this repository and the `gh` GitHub CLI, authenticated.
- A clean working tree on an up-to-date `main` before starting issue work.
- [AD-01-M1 — Addressing an Open Issue](../Attachments/AD-01-M1%20Addressing%20an%20Open%20Issue.md)
- [QA-01 — Writing Standard Operating Procedures](./QA-01%20Writing%20Standard%20Operating%20Procedures.md)
- [QA-01-M1 — SOP Compliance Inspection](../Attachments/QA-01-M1%20SOP%20Compliance%20Inspection.md)

## General Guidelines

- Before using this SOP, the User and the AI must review the current version of this
  document in the repository to confirm it has not changed since last use.
- This SOP follows the formatting requirements defined in
  [QA-01](./QA-01%20Writing%20Standard%20Operating%20Procedures.md).
- One issue per branch and one branch per issue. Issue work is never committed
  directly to `main`.
- The AI pushes changes for the User to review and never merges into `main` without
  the User's explicit authorization for that specific branch. A branch being
  "acceptable" is not, by itself, authorization to merge.
- After a merge, the AI deletes the merged branch from both the local repository and
  `origin`.
- A problem discovered while addressing an issue that is out of that issue's scope is
  filed as a follow-up issue linking back to the original; the branch's scope is not
  expanded.
- Every commit message ends with the required `Co-Authored-By` trailer; the commit
  that completes the work includes `Closes #<number>`.

## Procedures

### 1. Posting an issue

1. Write the issue with a specific, action-oriented title.
2. In the body, state the problem or goal, the scope, the acceptance criteria, and
   any concrete deliverables (files, behaviors).
3. If the issue arises from another issue, link back to it.
4. File it with `gh issue create`.

### 2. Addressing an open issue

Follow the machine instructions in
[AD-01-M1 — Addressing an Open Issue](../Attachments/AD-01-M1%20Addressing%20an%20Open%20Issue.md).
In summary:

1. **Confirm scope.** Read the issue and its comments, restate the goal and
   acceptance criteria to the User, and wait for confirmation.
2. **Create the issue branch.** From an up-to-date `main`, create
   `issue-<number>-<slug>`. All work happens here.
3. **Do the work.** Make focused commits. If the work creates or changes an SOP or
   attachment, run [QA-01-M1](../Attachments/QA-01-M1%20SOP%20Compliance%20Inspection.md)
   against each affected SOP until it reports **COMPLIANT**.
4. **Push for review.** Push the branch and open a pull request into `main` whose
   body contains `Closes #<number>`. Present the branch name, PR link, a summary of
   changes, any QA-01-M1 report, and how the branch meets each acceptance criterion.
   Do not merge.
5. **Iterate.** Apply the User's feedback on the branch and push each revision until
   the User states the branch is acceptable.
6. **Merge on instruction.** When — and only when — the User explicitly instructs the
   merge, merge the branch into `main` with `gh pr merge <pr> --merge
   --delete-branch`. The `Closes #<number>` reference closes the issue.
7. **Clean up.** Ensure the merged branch is deleted locally and on `origin`, then
   update local `main` with `git pull --ff-only`.
8. **Close out.** Confirm the issue is closed and post a comment summarizing the
   solution, the merge commit, and any follow-up issues.

## References

- [AD-01-M1](../Attachments/AD-01-M1%20Addressing%20an%20Open%20Issue.md) — Addressing an Open Issue (machine instructions Claude follows to work an open issue)
- [QA-01](./QA-01%20Writing%20Standard%20Operating%20Procedures.md) — Writing Standard Operating Procedures
- [QA-01-M1](../Attachments/QA-01-M1%20SOP%20Compliance%20Inspection.md) — SOP Compliance Inspection
- [GitHub CLI manual](https://cli.github.com/manual/) — `gh issue` and `gh pr` command reference
