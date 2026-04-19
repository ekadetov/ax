---
description: "Bump version in plugin.json, commit, and push"
---

Increment the version in `.claude-plugin/plugin.json`, commit, and push.

`$ARGUMENTS` specifies the bump type: `patch` (default), `minor`, or `major`.

## Steps

1. **Read current version** from `.claude-plugin/plugin.json`.

2. **Compute new version** using semver rules:
   - `patch`: `1.2.3` → `1.2.4`
   - `minor`: `1.2.3` → `1.3.0`
   - `major`: `1.2.3` → `2.0.0`
   - Default to `patch` if `$ARGUMENTS` is empty.

3. **Update** the `version` field in `.claude-plugin/plugin.json`.

4. **Commit**:
   ```bash
   git commit -m "chore: bump version to <new-version>"
   ```

5. **Push** to origin main.

6. **Print** the old → new version for confirmation.

## Rules

- Only modify the `version` field in `plugin.json`. Touch nothing else.
- Never bump if the working tree has uncommitted changes to other files — warn and stop.
