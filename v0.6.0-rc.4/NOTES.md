The console copies its database the first time a new version starts,
before migrating it: an upgrade by re-running install.sh now leaves a copy
to roll back to as well (backups/pre-<version>-from-<previous>.db, the
newest 3 kept).

Secret sets: App pod templates carry a keyed hash of their secrets.

The release's e2e run upgrades from v0.6.0-rc.3 through the console, the
first release run to do so.

## Install

On a fresh Ubuntu server (Hetzner Cloud or dedicated); re-run it on an existing
Kwerft server to upgrade:

```bash
curl -fsSL https://kwerft.dev/v0.6.0-rc.4/install.sh | sudo bash -s -- --domain ops.example.com --yes
```

The `install.sh` attached here is the same file; `SHA256SUMS` lists both scripts.

| | |
|---|---|
| Image | `ghcr.io/ehilzinger/kwerft:0.6.0-rc.4` (linux/amd64, linux/arm64) · `ghcr.io/ehilzinger/kwerft@sha256:6a67c8d21bdb628cdd1184fcbc4548edeac26eaf64dc290d1dd563299be979b2` |
| Helm chart | `oci://ghcr.io/ehilzinger/charts/kwerft` version `0.6.0-rc.4` · `ghcr.io/ehilzinger/charts/kwerft@sha256:d431ae6ee56f2303daa5e56005f37811a9820d1bd9ed8443e756e65381ec6479` |
| Kubernetes | k3s `v1.37.1+k3s1` for new installs |
| Upgrades from | 0.4.0 and later |



**Full Changelog**: https://github.com/ehilzinger/kwerft/compare/v0.6.0-rc.3...v0.6.0-rc.4
