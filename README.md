# homelab-arc

ArgoCD-managed Actions Runner Controller (ARC) configuration for the homelab.

## Contents

- `arc-controller-app.yaml`: installs the ARC controller via Helm.
- `arc-runners-app.yaml`: installs RunnerScaleSet and secrets after CRDs exist.
- `arc-namespaces.yaml`: creates `arc-systems` and `arc-runners` namespaces.
- `runners/arc-github-secret.yaml`: SealedSecret with GitHub token for ARC.
- `runners/arc-runner-scale-set.yaml`: RunnerScaleSet definition.

## Notes

- Update `githubConfigUrl` in `runners/arc-runner-scale-set.yaml` to your repo/org URL.
- Runners are configured to be ephemeral and scaled between 0 and 5 by default.
- If you see `RunnerScaleSet.actions.github.com not found`, wait for the
	`arc-controller` app to finish installing CRDs, then refresh `arc-runners`.
