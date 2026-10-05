Phase 6 release candidate: upgrades from the console (Kwerft and k3s, with
rollback), backups to Object Storage encrypted with a recovery key and
install.sh --restore onto a new server, secret sets, Docker Compose import
and templates.

## Install

On a fresh Ubuntu server (Hetzner Cloud or dedicated); re-run it on an existing
Kwerft server to upgrade:

```bash
curl -fsSL https://kwerft.dev/v0.6.0-rc.1/install.sh | sudo bash -s -- --domain ops.example.com --yes
```

The `install.sh` attached here is the same file; `SHA256SUMS` lists both scripts.

| | |
|---|---|
| Image | `ghcr.io/ehilzinger/kwerft:0.6.0-rc.1` (linux/amd64, linux/arm64) · `ghcr.io/ehilzinger/kwerft@sha256:9d0147e3250bc8d24dff350761ab96857dec295d7c1719a525d2cb785f174f97` |
| Helm chart | `oci://ghcr.io/ehilzinger/charts/kwerft` version `0.6.0-rc.1` · `ghcr.io/ehilzinger/charts/kwerft@sha256:3d4cbff212cee9fa39d26ab5e8392c589cf682c6b191fbd2c74535a16b095c16` |
| Kubernetes | k3s `v1.37.1+k3s1` for new installs |
| Upgrades from | 0.4.0 and later |



**Full Changelog**: https://github.com/ehilzinger/kwerft/compare/v0.5.0-rc.3...v0.6.0-rc.1
