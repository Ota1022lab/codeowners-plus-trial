# codeowners-plus-trial

A sandbox repository for trying out [codeowners-plus](https://github.com/multimediallc/codeowners-plus),
a GitHub Action that enforces code owner approvals with more flexibility than GitHub's
built-in CODEOWNERS support.

## What's here

| File | Purpose |
| --- | --- |
| [.codeowners](.codeowners) | Owner rules. Currently every path is owned by `@Ota1022` and `@io2210`. |
| [codeowners.toml](codeowners.toml) | Action configuration (self-approval, enforcement). |
| [.github/workflows/codeowners.yml](.github/workflows/codeowners.yml) | Workflow that runs the action on pull requests. |

## Configuration

```toml
allow_self_approval = true

[enforcement]
fail_check = true
```

- `allow_self_approval` — the PR author can satisfy their own ownership requirement.
- `enforcement.fail_check` — the check fails (rather than just warning) when required
  approvals are missing.

## How it runs

The workflow triggers on `pull_request` events (`opened`, `reopened`, `synchronize`,
`ready_for_review`, `labeled`, `unlabeled`), checks out the full history so the action
can diff against the base branch, and reports missing approvals back on the PR.

## Trying it out

1. Create a branch and change any file.
2. Open a pull request.
3. Check the **Run Codeowners Plus** job in the Actions tab to see which owners are
   required and whether the check passes.
