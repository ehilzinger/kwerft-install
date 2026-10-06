Upgrades from the console start the installer: the runner starts the
installer's unit from a short host unit it waits for (a systemd-run that
neither waits nor pipes cannot reach systemd from the pod). The first
console upgrade on a real server (rc.6 → rc.7) succeeded with that step
done by hand. A console on rc.7 or earlier has the old runner: move it
to rc.8 with install.sh once; console upgrades work from rc.8 on.

Tasks and Apps with egress https reach their own cluster's hostnames
(TCP 443 to the host and remote nodes); Task network policies are
CiliumNetworkPolicies. A Task killed for memory says so: terminationReason
and memoryLimit in its status, Ready reason OutOfMemory, "out of memory
(limit 256Mi)" in the console.

## Install

On a fresh Ubuntu server (Hetzner Cloud or dedicated); re-run it on an existing
Kwerft server to upgrade:

```bash
curl -fsSL https://kwerft.dev/v0.6.0-rc.8/install.sh | sudo bash -s -- --domain ops.example.com --yes
```

The `install.sh` attached here is the same file; `SHA256SUMS` lists both scripts.

| | |
|---|---|
| Image | `ghcr.io/ehilzinger/kwerft:0.6.0-rc.8` (linux/amd64, linux/arm64) · `ghcr.io/ehilzinger/kwerft@sha256:89f285fbdeec17a8aa22091e6f7bee72e7d3c0fb506eed064eaf99a5085260f3` |
| Helm chart | `oci://ghcr.io/ehilzinger/charts/kwerft` version `0.6.0-rc.8` · `ghcr.io/ehilzinger/charts/kwerft@sha256:fcb8764bcaaac3cf82ce7270145c679b104cd4614f4b4d72bc090af5cb7d020e` |
| Kubernetes | k3s `v1.37.1+k3s1` for new installs |
| Upgrades from | 0.4.0 and later |



**Full Changelog**: https://github.com/ehilzinger/kwerft/compare/v0.6.0-rc.7...v0.6.0-rc.8
