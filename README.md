# 🚫💩 lint-staged-mr

Run linters against staged or MR/PR git diff files and don't let :poop: slip into your code base!

GitLab MR:

```shell
git diff --diff-filter=d --name-only origin/${CI_MERGE_REQUEST_TARGET_BRANCH_NAME} ${CI_COMMIT_SHA} > .git-staged-files
npx lint-staged-mr
```

GitHub PR:

```shell
git diff --diff-filter=d --name-only origin/${GITHUB_BASE_REF} ${GITHUB_HEAD_REF} > .git-staged-files
npx lint-staged-mr
```

local staged:

```
$ git commit

✔ Preparing lint-staged...
❯ Running tasks for staged files...
  ❯ packages/frontend/.lintstagedrc.json — 1 file
    ↓ *.js — no files [SKIPPED]
    ❯ *.{json,md} — 1 file
      ⠹ prettier --write
  ↓ packages/backend/.lintstagedrc.json — 2 files
    ❯ *.js — 2 files
      ⠼ eslint --fix
    ↓ *.{json,md} — no files [SKIPPED]
◼ Applying modifications from tasks...
◼ Cleaning up temporary files...
```

Other features are consistent with the official package, please check the official documentation: https://github.com/okonet/lint-staged
