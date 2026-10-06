Registry credentials: every push to the in-cluster registry needs a
credential, and each project's builds push with their own, to their own
repositories only (a build in one project can no longer push into
another's). Kwerft keeps tags with its own credential; pulls stay
anonymous (nodes, console and build pods; App pods cannot reach the
registry). No console role can read the credentials. Existing installs:
the nodes and running Apps are untouched, the registry restarts once,
builds running across the upgrade finish as before.

install.sh --config with an owner: block creates that owner: the console
reads it from the installer, creates the owner and removes the password
from the cluster. Without owner:, or when the owner is rejected, the
install hands out a setup token as before.

## Install

On a fresh Ubuntu server (Hetzner Cloud or dedicated); re-run it on an existing
Kwerft server to upgrade:

```bash
curl -fsSL https://kwerft.dev/v0.6.0-rc.10/install.sh | sudo bash -s -- --domain ops.example.com --yes
```

The `install.sh` attached here is the same file; `SHA256SUMS` lists both scripts.

| | |
|---|---|
| Image | `ghcr.io/ehilzinger/kwerft:0.6.0-rc.10` (linux/amd64, linux/arm64) · `ghcr.io/ehilzinger/kwerft@sha256:f3c98c4c5e64559ccc29baebc6d77a0783a5bb4f9e59267fc7d819414e077613` |
| Helm chart | `oci://ghcr.io/ehilzinger/charts/kwerft` version `0.6.0-rc.10` · `ghcr.io/ehilzinger/charts/kwerft@sha256:1ee0eee6054d3f7c4a334d00d25beae5f39d3183cdd9af9f1d3147055c1ad4c6` |
| Kubernetes | k3s `v1.37.1+k3s1` for new installs |
| Upgrades from | 0.4.0 and later |



**Full Changelog**: https://github.com/ehilzinger/kwerft/compare/v0.6.0-rc.9...v0.6.0-rc.10
