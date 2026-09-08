# Maxxwell downloads

Latest release: [v0.1.46](https://github.com/rindler-ai/ide-releases/releases/tag/v0.1.46)

## Release identity

- Version: v0.1.46
- Build: global-91
- Source commit: 201d247dcd06ea3ed641dfe85f149010badd7a6f
- Staged: September 7, 2026 at 5:54:14 PM PDT

| Platform | Download | Install |
| --- | --- | --- |
| macOS arm64 | [`Maxxwell-darwin-arm64.tar.gz`](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.46/Maxxwell-darwin-arm64.tar.gz) | `tar -xzf Maxxwell-darwin-arm64.tar.gz` |
| macOS x64 | [`Maxxwell-darwin-x64.tar.gz`](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.46/Maxxwell-darwin-x64.tar.gz) | `tar -xzf Maxxwell-darwin-x64.tar.gz` |
| Linux tar | [`Maxxwell-linux-x64.tar.gz`](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.46/Maxxwell-linux-x64.tar.gz) | \`tar -xzf Maxxwell-linux-x64.tar.gz\` |
| Linux deb | [`maxxwell_0.1.46-global-91_amd64.deb`](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.46/maxxwell_0.1.46-global-91_amd64.deb) | \`sudo apt install ./maxxwell_0.1.46-global-91_amd64.deb\` |
| Windows x64 (unsigned) | [`Maxxwell-windows-x64.zip`](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.46/Maxxwell-windows-x64.zip) | `Expand-Archive .\Maxxwell-windows-x64.zip` (SmartScreen will warn) |

[SHA256SUMS.txt](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.46/SHA256SUMS.txt) verifies every published artifact.

## Platform build status

| Platform | Status | Evidence |
| --- | --- | --- |
| macOS | BUILT | arm64 packaged, signed, notarized and stapled on a real Mac, and the .dmg verified against Gatekeeper; target Mach-O modules validated; packaged GUI launch and the native workspace-folder picker were confirmed end-to-end by the founder on v0.1.42 (2026-09-05) -- not independently re-verified per release |
| Linux | BUILT | self-hosted native .tar.gz, .deb, and standalone CLI tarball validated |
| Windows | BUILT | Linux-cross-built unsigned x64 app/CLI ZIPs; target PE modules validated; SmartScreen will warn; packaged GUI launch remains UNVERIFIED |

No declared platform artifacts are pending.
