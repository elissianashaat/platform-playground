# platform-playground

A GitOps lab for trying platform tools on Kubernetes, one experiment at a time.
A single Argo CD hub manages a small fleet of local clusters, and every change
reaches `main` through a pull request with automated checks.

## Roadmap

- [x] CI checks for every pull request
- [ ] Argo CD hub bootstrapped from this repo
- [ ] Kyverno: policy as code, tested in CI
- [ ] Multi-cluster fleet with ApplicationSets

## Checks on every pull request

| Check | Catches |
| ----- | ------- |
| yamllint (strict) | Invalid or inconsistent YAML |
| actionlint | Mistakes in GitHub Actions workflows |
| shellcheck | Shell script bugs |
| gitleaks | Secrets committed anywhere in the PR's history |
| zizmor | Security issues in workflows (injection, over-broad permissions, unpinned actions) |
| `ci-ok` | One required check that passes only when every job above passed |

Every third-party action is pinned to a full commit SHA, and each job gets the minimum token permissions.
