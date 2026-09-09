# AD-01-M1: Addressing an Open Issue

> **Attachment:** AD-01-M1 — Machine Instructions
> **Parent SOP:** [AD-01](../Procedures/AD-01%20Posting%20and%20Responding%20to%20GitHub%20Issues.md)
> **Audience:** Claude (AI). Read the whole file, then execute every step in order.

## When to run

Run this procedure whenever the User asks Claude to address, work, or resolve an open
GitHub issue on this repository.

## Inputs

- **Issue number** — the issue to address.
- **Repository state** — a clean working tree on an up-to-date `main`.
- **User** — available to review the branch and to authorize the merge.

## Procedure

### Step 1 — Understand and confirm scope

1. Read the issue with `gh issue view <number>` including its comments.
2. Restate the issue's goal, deliverables, and acceptance criteria to the User in
   your own words.
3. Ask any clarifying questions. Do not proceed until the User confirms the scope.

### Step 2 — Create the issue branch

1. Ensure the working tree is clean and `main` is current:
   `git checkout main && git pull --ff-only`.
2. Create a branch named `issue-<number>-<slug>`, where `<slug>` is a short
   kebab-case summary of the issue (for example, `issue-7-github-issue-sop`):
   `git checkout -b issue-<number>-<slug>`.
3. All work for this issue happens on this branch. Never commit issue work directly
   to `main`.

### Step 3 — Do the work

1. Make the changes the issue calls for, in focused commits.
2. If the work creates or modifies any SOP or SOP attachment, run
   [QA-01-M1](./QA-01-M1%20SOP%20Compliance%20Inspection.md) against each affected SOP
   and resolve every `FAIL` until the report reads **COMPLIANT**. Include the
   inspection report in your summary to the User.
3. If the work reveals a separate problem out of scope for this issue, file a
   follow-up issue that links back to this one; do not expand the branch's scope.
4. End every commit message with the required co-author trailer and include
   `Closes #<number>` in the message that completes the work.

### Step 4 — Push the branch for review

1. Push the branch: `git push -u origin issue-<number>-<slug>`.
2. Open a pull request targeting `main` whose body contains `Closes #<number>`.
3. Present to the User: the branch name, the PR link, a summary of the changes, any
   QA-01-M1 report, and a short statement of how the branch satisfies each
   acceptance criterion.
4. **Do not merge.** Wait for the User.

### Step 5 — Iterate

1. Apply the User's feedback on the branch.
2. Commit and push each revision. Re-run QA-01-M1 if an SOP changed.
3. Repeat until the User states the branch is acceptable.

### Step 6 — Merge (only on explicit User instruction)

1. Do not merge until the User explicitly instructs it (for example, "merge and
   close"). The branch being "acceptable" is not by itself authorization to merge.
2. Confirm the PR is mergeable and its checks (if any) pass.
3. Merge into `main`: `gh pr merge <pr> --merge --delete-branch`.
   - The `Closes #<number>` reference closes the issue automatically.

### Step 7 — Clean up

1. Delete the merged branch if `--delete-branch` did not:
   `git branch -d issue-<number>-<slug>` and
   `git push origin --delete issue-<number>-<slug>`.
2. Update local `main`: `git checkout main && git pull --ff-only`.
3. Verify the working tree is clean and the issue branch no longer exists locally or
   on `origin`.

### Step 8 — Close out

1. Confirm the issue is `CLOSED`.
2. Post a comment on the issue summarizing the solution: what changed, the merge
   commit, and any follow-up issues created.

## Guardrails

- One issue per branch; one branch per issue.
- Never merge without explicit User authorization for that specific merge.
- Never force-push a branch under User review; add commits instead.
- If `main` has advanced while the branch was in review, rebase or merge `main` into
  the branch and re-push before merging.

## References

- [AD-01](../Procedures/AD-01%20Posting%20and%20Responding%20to%20GitHub%20Issues.md) — Posting and Responding to GitHub Issues
- [QA-01](../Procedures/QA-01%20Writing%20Standard%20Operating%20Procedures.md) — Writing Standard Operating Procedures
- [QA-01-M1](./QA-01-M1%20SOP%20Compliance%20Inspection.md) — SOP Compliance Inspection
