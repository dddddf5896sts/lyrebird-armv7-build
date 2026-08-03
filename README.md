# lyrebird-armv7-build

GitHub Actions cross-compiles [Tor Project Lyrebird](https://gitlab.torproject.org/tpo/anti-censorship/pluggable-transports/lyrebird) for Linux ARMv7 (`GOARCH=arm`, `GOARM=7`).

## Provenance

The workflow pins Lyrebird `lyrebird-0.8.1` at commit `44c34e6535fdece76c7214b805eef2a3d1c01f91` and verifies the official GitLab source archive SHA256 before extracting it. It also runs `go mod verify` and the upstream test suite.

## Artifact

Successful workflow runs upload `lyrebird` and `SHA256SUMS` as a 30-day artifact. Verify after download:

```bash
sha256sum -c SHA256SUMS
file lyrebird
```

Expected binary: ELF 32-bit ARM Linux. No repository secrets or releases are used.
