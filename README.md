# Maxxwell downloads

Latest release: [v0.1.69](https://github.com/rindler-ai/ide-releases/releases/tag/v0.1.69)

## Release identity

- Version: v0.1.69
- Build: global-114
- Source commit: 7406e90c4e8c3009ee72b162a7550472e6caebd4
- Staged: September 12, 2026 at 2:30:16 AM PDT

| Platform | Download | Install |
| --- | --- | --- |
| macOS arm64 | [`Maxxwell-darwin-arm64.tar.gz`](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.69/Maxxwell-darwin-arm64.tar.gz) | `tar -xzf Maxxwell-darwin-arm64.tar.gz` |
| macOS x64 | [`Maxxwell-darwin-x64.tar.gz`](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.69/Maxxwell-darwin-x64.tar.gz) | `tar -xzf Maxxwell-darwin-x64.tar.gz` |
| Linux tar | [`Maxxwell-linux-x64.tar.gz`](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.69/Maxxwell-linux-x64.tar.gz) | \`tar -xzf Maxxwell-linux-x64.tar.gz\` |
| Linux deb | [`maxxwell_0.1.69-global-114_amd64.deb`](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.69/maxxwell_0.1.69-global-114_amd64.deb) | \`sudo apt install ./maxxwell_0.1.69-global-114_amd64.deb\` |
| Windows x64 (unsigned) | [`Maxxwell-windows-x64.zip`](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.69/Maxxwell-windows-x64.zip) | `Expand-Archive .\Maxxwell-windows-x64.zip` (SmartScreen will warn) |

[SHA256SUMS.txt](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.69/SHA256SUMS.txt) verifies every published artifact.

## If `maxxwell self-update` fails with HTTP 404

The standalone `maxxwell` CLI at v0.1.61 or earlier can't update itself. Its `self-update`
downloads from a repository that is no longer public, so it stops with
`read the release checksums: GET https://github.com/rindler-ai/maxxwell-cli/...: HTTP 404`
and leaves the old version in place.

**If you use the desktop app, update the app instead of running anything below.** The app is not
affected: it updates itself from this repository and replaces its bundled `maxxwell` when it does,
and its `maxxwell` on your `PATH` is a link into the app.

Otherwise, reinstall the CLI once from this release, over the old executable:

macOS arm64:

```sh
curl -fLO https://github.com/rindler-ai/ide-releases/releases/download/v0.1.69/maxxwell-darwin-cli-arm64-global-114.tar.gz
tar -xzf maxxwell-darwin-cli-arm64-global-114.tar.gz
install -m 0755 maxxwell "$(command -v maxxwell)"
```

macOS x64:

```sh
curl -fLO https://github.com/rindler-ai/ide-releases/releases/download/v0.1.69/maxxwell-darwin-cli-x64-global-114.tar.gz
tar -xzf maxxwell-darwin-cli-x64-global-114.tar.gz
install -m 0755 maxxwell "$(command -v maxxwell)"
```

Linux x64:

```sh
curl -fLO https://github.com/rindler-ai/ide-releases/releases/download/v0.1.69/maxxwell-linux-cli-x64-global-114.tar.gz
tar -xzf maxxwell-linux-cli-x64-global-114.tar.gz
install -m 0755 maxxwell "$(command -v maxxwell)"
```

If that path is not writable, the last command fails and changes nothing; re-run it with `sudo`.

From v0.1.62 on, `maxxwell self-update` downloads from this repository.

## Platform build status

| Platform | Status | Evidence |
| --- | --- | --- |
| macOS | BUILT | arm64 packaged, signed, notarized and stapled on a real Mac, and the .dmg verified against Gatekeeper; target Mach-O modules validated; packaged GUI launch and the native workspace-folder picker were confirmed end-to-end by the founder on v0.1.42 (2026-09-05) -- not independently re-verified per release |
| Linux | BUILT | self-hosted native .tar.gz, .deb, and standalone CLI tarball validated |
| Windows | BUILT | Linux-cross-built unsigned x64 app/CLI ZIPs; target PE modules validated; SmartScreen will warn; packaged GUI launch remains UNVERIFIED |

No declared platform artifacts are pending.
