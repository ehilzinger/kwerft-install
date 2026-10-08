What v0.6.0-rc.13 was meant to be (its release stopped on a test and
published nothing), plus:

Restores say why the backup's contents cannot be read ("Reading the
backup's contents failed, retrying: the storage answered 403 …") and fail
with that error after 2 minutes, instead of waiting without a word.

From rc.13: DNS can change and delete wildcard records again (adding a
second node's address to *.apps.<domain> failed with "not found"); the
plan's Rebalance action and App autoscaling; e2e runs wait for the
Hetzner project's resource limits.

## Install

On a fresh Ubuntu server (Hetzner Cloud or dedicated); re-run it on an existing
Kwerft server to upgrade:

```bash
curl -fsSL https://kwerft.dev/v0.6.0-rc.14/install.sh | sudo bash -s -- --domain ops.example.com --yes
```

The `install.sh` attached here is the same file; `SHA256SUMS` lists both scripts.

| | |
|---|---|
| Image | `ghcr.io/ehilzinger/kwerft:0.6.0-rc.14` (linux/amd64, linux/arm64) · `ghcr.io/ehilzinger/kwerft@sha256:b18ab74ddc065e66b6711af86b88d6db32657689bc6bc6b0cc54962a09c2d317` |
| Helm chart | `oci://ghcr.io/ehilzinger/charts/kwerft` version `0.6.0-rc.14` · `ghcr.io/ehilzinger/charts/kwerft@sha256:7c5e9a0fae3b1553f616909cbc23e098d071e05cbfa8c8c52f32cb6a459d4f24` |
| Kubernetes | k3s `v1.37.1+k3s1` for new installs |
| Upgrades from | 0.4.0 and later |



**Full Changelog**: https://github.com/ehilzinger/kwerft/compare/v0.6.0-rc.12...v0.6.0-rc.14
