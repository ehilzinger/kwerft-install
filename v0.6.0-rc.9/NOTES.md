The same code as v0.6.0-rc.8, released again so that a console on rc.8
(the first with a working upgrade runner) has a newer version to upgrade
to from Settings › Updates: the first console upgrade without any step
by hand, on kwerft-dev-test and in this release's e2e run.

## Install

On a fresh Ubuntu server (Hetzner Cloud or dedicated); re-run it on an existing
Kwerft server to upgrade:

```bash
curl -fsSL https://kwerft.dev/v0.6.0-rc.9/install.sh | sudo bash -s -- --domain ops.example.com --yes
```

The `install.sh` attached here is the same file; `SHA256SUMS` lists both scripts.

| | |
|---|---|
| Image | `ghcr.io/ehilzinger/kwerft:0.6.0-rc.9` (linux/amd64, linux/arm64) · `ghcr.io/ehilzinger/kwerft@sha256:139f1f0b26fb304eb711d00cd6fa557b7643d6e40b43a1a2d667d66e6c861ba2` |
| Helm chart | `oci://ghcr.io/ehilzinger/charts/kwerft` version `0.6.0-rc.9` · `ghcr.io/ehilzinger/charts/kwerft@sha256:0852669190663b1055ede70963d749c3889cacc74203fbfb01af1e96e68be8b2` |
| Kubernetes | k3s `v1.37.1+k3s1` for new installs |
| Upgrades from | 0.4.0 and later |



**Full Changelog**: https://github.com/ehilzinger/kwerft/compare/v0.6.0-rc.7...v0.6.0-rc.9
