Database copies (before an upgrade, on a version's first start, and for
backups) are readable by their owner only (0600), like the database.

The first release a console on rc.6 can upgrade to from Settings ›
Updates; its e2e run upgrades from rc.6 through the console.

## Install

On a fresh Ubuntu server (Hetzner Cloud or dedicated); re-run it on an existing
Kwerft server to upgrade:

```bash
curl -fsSL https://kwerft.dev/v0.6.0-rc.7/install.sh | sudo bash -s -- --domain ops.example.com --yes
```

The `install.sh` attached here is the same file; `SHA256SUMS` lists both scripts.

| | |
|---|---|
| Image | `ghcr.io/ehilzinger/kwerft:0.6.0-rc.7` (linux/amd64, linux/arm64) · `ghcr.io/ehilzinger/kwerft@sha256:672661c2959ceafded1d5066da949e95e8ec6b0934bd32966441900f138bc7e4` |
| Helm chart | `oci://ghcr.io/ehilzinger/charts/kwerft` version `0.6.0-rc.7` · `ghcr.io/ehilzinger/charts/kwerft@sha256:088c7077686ab0eff68463344a89ff78e491170d614430b83f750ad38d29aff3` |
| Kubernetes | k3s `v1.37.1+k3s1` for new installs |
| Upgrades from | 0.4.0 and later |



**Full Changelog**: https://github.com/ehilzinger/kwerft/compare/v0.6.0-rc.6...v0.6.0-rc.7
