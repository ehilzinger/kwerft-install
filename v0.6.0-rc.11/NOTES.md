Compose import and templates review again: a plan without problems sent
"problems": null, and the Review step crashed ("Cannot read properties of
null (reading 'length')"). Found deploying a template on kwerft-dev-test.

The Overview map: lanes above the servers, labels off the chips,
selections clear of the inspector.

## Install

On a fresh Ubuntu server (Hetzner Cloud or dedicated); re-run it on an existing
Kwerft server to upgrade:

```bash
curl -fsSL https://kwerft.dev/v0.6.0-rc.11/install.sh | sudo bash -s -- --domain ops.example.com --yes
```

The `install.sh` attached here is the same file; `SHA256SUMS` lists both scripts.

| | |
|---|---|
| Image | `ghcr.io/ehilzinger/kwerft:0.6.0-rc.11` (linux/amd64, linux/arm64) · `ghcr.io/ehilzinger/kwerft@sha256:eea89e0c65470053ec7accc70e27b24edf622d3bc17ec5837a09b0cdc0e5f98d` |
| Helm chart | `oci://ghcr.io/ehilzinger/charts/kwerft` version `0.6.0-rc.11` · `ghcr.io/ehilzinger/charts/kwerft@sha256:41b4e59d64690455d7bfde2bfd3bd03f7e178d4bd16fc7ce7b134ad580a3fa8a` |
| Kubernetes | k3s `v1.37.1+k3s1` for new installs |
| Upgrades from | 0.4.0 and later |



**Full Changelog**: https://github.com/ehilzinger/kwerft/compare/v0.6.0-rc.10...v0.6.0-rc.11
