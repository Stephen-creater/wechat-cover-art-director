# Repository operating rules

These rules apply to the entire `wechat-cover-art-director` repository.

## Preserve user work

- Preserve all existing user content and unrelated changes. Do not overwrite, delete, reformat, or reorganize files outside the explicitly requested scope.
- Before editing, inspect `git status` and the relevant files. If unrelated changes exist, keep them intact and commit only the files produced by the current task.
- A candidate cover that the user has not explicitly adopted, approved, or used must not enter `assets/approved-covers/`, `references/cases/`, `references/approved-index.md`, or any other positive case or routing record.
- When the user rejects a batch without giving per-image reasons, record only the batch-level rejection evidence. Never invent a reason for an individual image.

## Local verification before version control

- The local Skill repository and GitHub `main` must remain synchronized.
- Any change to images, examples, prompts, preferences, routing, rules, indexes, documentation, or repository metadata must be validated locally before it is committed.
- At minimum, verify file existence and references, inspect `git diff`, inspect `git status`, and check that no credentials, private source material, generated candidates, or unrelated user changes are included.

## Commit, push, and remote readback

- Every completed repository change must have a meaningful Git commit and be pushed to `origin/main` in the same task, unless the user explicitly requests a local-only draft.
- After pushing, read back the remote `main` commit hash and the changed key files from GitHub. Confirm that the remote content, not merely the local working tree or push command output, contains the intended update.
- Do not claim completion while any task change is uncommitted, unpushed, absent from remote `main`, or not verified by remote readback.
- Keep local `main`, `origin/main`, and GitHub `main` aligned at task completion.
