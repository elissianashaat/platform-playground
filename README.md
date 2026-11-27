# platform-playground

A GitOps lab for trying platform tools on Kubernetes, one experiment at a time.
A single Argo CD hub manages a small fleet of local clusters, and every change
reaches `main` through a pull request with automated checks.

## Roadmap

- [ ] CI checks for every pull request
- [ ] Argo CD hub bootstrapped from this repo
- [ ] Kyverno: policy as code, tested in CI
- [ ] Multi-cluster fleet with ApplicationSets
