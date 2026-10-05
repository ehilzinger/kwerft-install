The Overview has an infrastructure map: apps by project, jobs, volumes,
domains, traffic rules with their counts, dropped connections and the server
firewall, in a Traffic view and a Placement view (what runs on which server).
Click anything to see what it talks to; Needs attention items link to it.

Read-only volume mounts are read-only in the container only, and a volume
that does not mount says why.

## Install

On a fresh Ubuntu server (Hetzner Cloud or dedicated); re-run it on an existing
Kwerft server to upgrade:

```bash
curl -fsSL https://kwerft.dev/v0.6.0-rc.2/install.sh | sudo bash -s -- --domain ops.example.com --yes
```

The `install.sh` attached here is the same file; `SHA256SUMS` lists both scripts.

| | |
|---|---|
| Image | `ghcr.io/ehilzinger/kwerft:0.6.0-rc.2` (linux/amd64, linux/arm64) · `ghcr.io/ehilzinger/kwerft@sha256:cc7fea4dc55c20e38232b2b8e444faaffc30f4b915d3355abfaf26aceb1484fe` |
| Helm chart | `oci://ghcr.io/ehilzinger/charts/kwerft` version `0.6.0-rc.2` · `ghcr.io/ehilzinger/charts/kwerft@sha256:f56e917ee27bd22517940fc54666af28e843ec555d03f188aed652f0eef9d2e9` |
| Kubernetes | k3s `v1.37.1+k3s1` for new installs |
| Upgrades from | 0.4.0 and later |



**Full Changelog**: https://github.com/ehilzinger/kwerft/compare/v0.6.0-rc.1...v0.6.0-rc.2
