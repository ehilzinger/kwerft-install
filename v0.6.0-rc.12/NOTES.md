Disk health: wear alone is a warning, not a failing disk. An NVMe drive
past its rated endurance sets critical warning 0x04 and smartctl reports
it FAILED; such a drive stays usable while its spare blocks are above
their threshold. It now raises "Disk worn" and shows as a disk to watch;
"Disk failing" fires for the other warning bits, spare below threshold, a
FAILED status with another cause, and new media errors.

License: SPDX headers on every source file; the contributor license
agreement (CLA.md, a draft pending legal review) with a "cla" check on pull
requests; the trademark policy (TRADEMARKS.md).

e2e: the harness locks the output buffer it shares between stdout and
stderr, and asks the registry check again when its answer is empty.

## Install

On a fresh Ubuntu server (Hetzner Cloud or dedicated); re-run it on an existing
Kwerft server to upgrade:

```bash
curl -fsSL https://kwerft.dev/v0.6.0-rc.12/install.sh | sudo bash -s -- --domain ops.example.com --yes
```

The `install.sh` attached here is the same file; `SHA256SUMS` lists both scripts.

| | |
|---|---|
| Image | `ghcr.io/ehilzinger/kwerft:0.6.0-rc.12` (linux/amd64, linux/arm64) · `ghcr.io/ehilzinger/kwerft@sha256:f37eb92b0cbfc4673a9c8f5a6fae4ec2783befae7d3157b54bdcec0ad6cc2896` |
| Helm chart | `oci://ghcr.io/ehilzinger/charts/kwerft` version `0.6.0-rc.12` · `ghcr.io/ehilzinger/charts/kwerft@sha256:1f43ba455511187a1ceeb1d5b8c23e03f75f55c4e536193cd364321f2249ab50` |
| Kubernetes | k3s `v1.37.1+k3s1` for new installs |
| Upgrades from | 0.4.0 and later |



**Full Changelog**: https://github.com/ehilzinger/kwerft/compare/v0.6.0-rc.11...v0.6.0-rc.12
