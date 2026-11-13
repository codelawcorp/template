[More about git hooks](https://githooks.com/)

Configure this path to be used for githooks:
`git config core.hooksPath .githooks`

`pre-commit` and `commit-msg` are the stubs of Max's shared commit hooks (magzim21/utilities, README "Shared commit
hooks"): they run `~/scripts/git-hooks-pre-commit` (branch name, then `pre-commit.local`, then gitleaks) and
`~/scripts/git-hooks-commit-msg` (`commit-msg.local` when there is one, then the commitlint rules of
`.commitlintrc.yml`). Never edit the stubs: a project's own checks (its unit tests, a personal data guard, Terraform)
go into `pre-commit.local`. Check a repository: `cd ~/Developer/github/magzim21/utilities && ./git-hooks-install --status <repo>`.

### Gitleaks
If false positive, add `gitleaks:allow` comment next to exclude it.
