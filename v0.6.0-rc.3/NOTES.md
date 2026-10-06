Upgrades started from the console work on Ubuntu: the upgrade runner
reaches the host's systemd (it was refused with "Access denied" in the
Backup step). A server on rc.2 or earlier moves to rc.3 with install.sh
once; console upgrades work from rc.3 on.

A failed upgrade stops alerting once its version runs, e.g. after
install.sh was run by hand.

Monitoring leaves out the controller manager, scheduler and etcd, which
k3s runs inside its own process: no more alerts that always fire
(KubeControllerManagerDown, KubeSchedulerDown, ScrapePoolHasNoTargets,
RecordingRulesNoData), and vmagent is no longer CPU-throttled.

## Install

On a fresh Ubuntu server (Hetzner Cloud or dedicated); re-run it on an existing
Kwerft server to upgrade:

```bash
curl -fsSL https://kwerft.dev/v0.6.0-rc.3/install.sh | sudo bash -s -- --domain ops.example.com --yes
```

The `install.sh` attached here is the same file; `SHA256SUMS` lists both scripts.

| | |
|---|---|
| Image | `ghcr.io/ehilzinger/kwerft:0.6.0-rc.3` (linux/amd64, linux/arm64) · `ghcr.io/ehilzinger/kwerft@sha256:bb76b6897c962f1f8f9b5dbaa04ed9ae72b19c42ad2afab0bc20baff8d2549b2` |
| Helm chart | `oci://ghcr.io/ehilzinger/charts/kwerft` version `0.6.0-rc.3` · `ghcr.io/ehilzinger/charts/kwerft@sha256:718e3d305f054d7069c0a29566ef506f842c5b394554b8a9ff193a791269a2e0` |
| Kubernetes | k3s `v1.37.1+k3s1` for new installs |
| Upgrades from | 0.4.0 and later |



**Full Changelog**: https://github.com/ehilzinger/kwerft/compare/v0.6.0-rc.2...v0.6.0-rc.3
