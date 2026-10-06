What v0.6.0-rc.5 was meant to be (its release stopped on a flaky test
and published nothing):

Upgrades from the console get past their Backup step: the runner lists
Helm releases with flags Helm 4 still has (--all is gone). A console on
rc.4 or earlier still has the old runner: move it to rc.6 with install.sh
once; console upgrades work from rc.6 on.

Disk health on dedicated servers: md RAID and SMART readings (an exporter
on dedicated nodes), alerts for a degraded array, a failing or wearing
disk and missing readings, and disk health under Clusters › Nodes.

The e2e runs wait for a just-published installer; two backup tests no
longer race an earlier test's encryption key.

## Install

On a fresh Ubuntu server (Hetzner Cloud or dedicated); re-run it on an existing
Kwerft server to upgrade:

```bash
curl -fsSL https://kwerft.dev/v0.6.0-rc.6/install.sh | sudo bash -s -- --domain ops.example.com --yes
```

The `install.sh` attached here is the same file; `SHA256SUMS` lists both scripts.

| | |
|---|---|
| Image | `ghcr.io/ehilzinger/kwerft:0.6.0-rc.6` (linux/amd64, linux/arm64) · `ghcr.io/ehilzinger/kwerft@sha256:85bc9a0eef0833de9fb4adced6ea5470ea216d4bd1c707cc6df4b5b99cac31a4` |
| Helm chart | `oci://ghcr.io/ehilzinger/charts/kwerft` version `0.6.0-rc.6` · `ghcr.io/ehilzinger/charts/kwerft@sha256:f6f5cc1e89cf2efe08543604a2d14bb1b71215bfde90ec8deff26b47fc6c6a2c` |
| Kubernetes | k3s `v1.37.1+k3s1` for new installs |
| Upgrades from | 0.4.0 and later |



**Full Changelog**: https://github.com/ehilzinger/kwerft/compare/v0.6.0-rc.4...v0.6.0-rc.6
