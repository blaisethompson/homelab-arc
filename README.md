# homelab-arc

ArgoCD-managed Actions Runner Controller (ARC) configuration for the homelab.

## Contents

- `arc-controller-app.yaml`: installs the ARC controller via Helm.
- `arc-namespaces.yaml`: creates `arc-systems` and `arc-runners` namespaces.
- `arc-github-secret.yaml`: SealedSecret with GitHub token for ARC.
- `arc-runner-scale-set.yaml`: RunnerScaleSet definition.

## Notes

- Update `githubConfigUrl` in `arc-runner-scale-set.yaml` to your repo/org URL.
- Runners are configured to be ephemeral and scaled between 0 and 5 by default.
