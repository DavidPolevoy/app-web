---
name: product-records
description: Use when a decision, spec, ADR, research finding or QA result comes up while working on this code branch — those records live in the linked product repo, on the product branch that matches this code branch, and reach it only through a pull request.
---

# Product records for this code branch

This code repo is linked to a product repo (`.product-link.json`). Product, design, dev and QA
records for the code on this branch live on the product branch of the SAME name. Staging and
production branches map by role, as recorded in the product repo's `data/repos/*.repo.yaml`
(`staging_branch`, `production_branch`).

1. `node bin/sandbox.mjs link resolve` — prints the product repo, the matching product branch and
   the product clone's path. If `product_branch_exists` is false, the GitHub follow workflow has
   not created it yet; push this code branch first, or ask the user.
2. In the product clone, follow its `shared-repo-pr-workflow` skill with `--base <product_branch>`:
   `node bin/sandbox.mjs start <topic> --base <product_branch>`, write with `npx dreamteamer`,
   `npx dreamteamer check`, commit, push, `node bin/sandbox.mjs pr create`.
3. Report the PR link. Never merge it; GitHub does.

Code merges are never blocked by the product repo. When this code branch merges in GitHub, a follow
workflow opens the matching product PR on its own.
