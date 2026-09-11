# Maxxwell downloads

Latest release: [v0.1.64](https://github.com/rindler-ai/ide-releases/releases/tag/v0.1.64)

## Release identity

- Version: v0.1.64
- Build: global-109
- Source commit: 682108d243f7ac13be89bd27339fca3a4d1e4d5a
- Staged: September 11, 2026 at 2:26:33 AM PDT

| Platform | Download | Install |
| --- | --- | --- |
| macOS arm64 | [`Maxxwell-darwin-arm64.tar.gz`](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.64/Maxxwell-darwin-arm64.tar.gz) | `tar -xzf Maxxwell-darwin-arm64.tar.gz` |
| macOS x64 | [`Maxxwell-darwin-x64.tar.gz`](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.64/Maxxwell-darwin-x64.tar.gz) | `tar -xzf Maxxwell-darwin-x64.tar.gz` |
| Linux tar | [`Maxxwell-linux-x64.tar.gz`](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.64/Maxxwell-linux-x64.tar.gz) | \`tar -xzf Maxxwell-linux-x64.tar.gz\` |
| Linux deb | [`maxxwell_0.1.64-global-109_amd64.deb`](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.64/maxxwell_0.1.64-global-109_amd64.deb) | \`sudo apt install ./maxxwell_0.1.64-global-109_amd64.deb\` |
| Windows x64 (unsigned) | [`Maxxwell-windows-x64.zip`](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.64/Maxxwell-windows-x64.zip) | `Expand-Archive .\Maxxwell-windows-x64.zip` (SmartScreen will warn) |

[SHA256SUMS.txt](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.64/SHA256SUMS.txt) verifies every published artifact.

## Platform build status

| Platform | Status | Evidence |
| --- | --- | --- |
| macOS | BUILT | arm64 packaged, signed, notarized and stapled on a real Mac, and the .dmg verified against Gatekeeper; target Mach-O modules validated; packaged GUI launch and the native workspace-folder picker were confirmed end-to-end by the founder on v0.1.42 (2026-09-05) -- not independently re-verified per release |
| Linux | BUILT | self-hosted native .tar.gz, .deb, and standalone CLI tarball validated |
| Windows | BUILT | Linux-cross-built unsigned x64 app/CLI ZIPs; target PE modules validated; SmartScreen will warn; packaged GUI launch remains UNVERIFIED |

No declared platform artifacts are pending.
