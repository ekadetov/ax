---
description: "Stage, commit, and push skill changes"
---

Stage, commit (conventional), and push all current changes to the ax plugin.

## Steps

1. **Inspect changes** — run `git status` and `git diff` to understand what changed. Run `git log --oneline -5` to match commit style.

2. **Stage files** — add changed files by name. Never use `git add -A` or `git add .`. Never stage `.env` or credential files.

3. **Write a conventional commit message** — format: `type(scope): description`. Types: `feat`, `fix`, `chore`, `docs`. Scope is optional (e.g. `feat(write-a-prd): ...`). Keep subject under 72 characters. If `$ARGUMENTS` contains text, use it as guidance.

4. **Commit** using HEREDOC:
   ```bash
   git commit -m "$(cat <<'EOF'
   type: subject
   EOF
   )"
   ```

5. **Push** to current branch's remote.

6. **Verify** with `git status`.

## Rules

- One atomic commit per invocation.
- Never amend, force push, or skip hooks.
