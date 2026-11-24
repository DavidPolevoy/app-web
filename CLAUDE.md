# Code repo linked to a product repo

- Records about this code (ADRs, specs, decisions, QA runs) live in the product repo named in
  `.product-link.json`, on the branch with the same name as this one. Load the `product-records`
  skill before writing one.
- Merges happen in GitHub. Never merge a pull request, push a protected branch
  (`.product-link.json` → `protected`), or force-push. `node bin/sandbox.mjs pr create` opens a PR.
- Feature branches: umbrella `feature/<f>/main`, sub-branches `feature/<f>/<part>`. Never a bare
  `feature/<f>`.
