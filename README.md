# Maxxwell downloads

Latest release: [v0.1.75](https://github.com/rindler-ai/ide-releases/releases/tag/v0.1.75)

## Release identity

- Version: v0.1.75
- Build: global-120
- Source commit: 07dff9b5146b06f0212439e2fbba5fee809f3530
- Staged: September 12, 2026 at 5:19:30 PM PDT

| Platform | Download | Install |
| --- | --- | --- |
| macOS arm64 | [`Maxxwell-darwin-arm64.tar.gz`](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.75/Maxxwell-darwin-arm64.tar.gz) | `tar -xzf Maxxwell-darwin-arm64.tar.gz` |
| macOS x64 | [`Maxxwell-darwin-x64.tar.gz`](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.75/Maxxwell-darwin-x64.tar.gz) | `tar -xzf Maxxwell-darwin-x64.tar.gz` |
| Linux tar | [`Maxxwell-linux-x64.tar.gz`](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.75/Maxxwell-linux-x64.tar.gz) | `tar -xzf Maxxwell-linux-x64.tar.gz` |
| Linux deb | [`maxxwell_0.1.75-global-120_amd64.deb`](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.75/maxxwell_0.1.75-global-120_amd64.deb) | `sudo apt install ./maxxwell_0.1.75-global-120_amd64.deb` |
| Windows x64 (unsigned) | [`Maxxwell-windows-x64.zip`](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.75/Maxxwell-windows-x64.zip) | `Expand-Archive .\Maxxwell-windows-x64.zip` (SmartScreen will warn) |

[SHA256SUMS.txt](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.75/SHA256SUMS.txt) verifies every published artifact.

## If `maxxwell self-update` fails with HTTP 404

The standalone `maxxwell` CLI at v0.1.61 or earlier can't update itself. Its `self-update`
downloads from a repository that is no longer public, so it stops with
`read the release checksums: GET https://github.com/rindler-ai/maxxwell-cli/...: HTTP 404`
and leaves the old version in place.

**Check what `maxxwell` on your `PATH` actually is before running anything below:**

```sh
command ls -l "$(command -v maxxwell)"
```

(`command` keeps an `ls` alias out of the way.)

- **A link (`->`) into the desktop app** — `Maxxwell.app` on macOS, `/opt/maxxwell` or
  wherever the app was unpacked on Linux. **Update the app instead of running anything
  below.** On macOS or a Linux tarball install the app updates itself; a Linux `.deb` install
  can't (it owns nothing writable under `/opt/maxxwell`), so update it as you installed it:
  `sudo apt install` the new `.deb`.
- **A plain file (no `->`)** is a standalone CLI that the app will not replace, even if the
  app is also installed: it never overwrites a real file with a link. Reinstall it with the
  commands below.
- **A link to anything else:** run `command ls -l` on the path after the `->` (a relative
  path there is relative to the link's own directory), repeat until it is no longer a link,
  and apply the two rules above to where it ends.
- **`No such file` naming `maxxwell` or an alias:** a shell alias or function called
  `maxxwell` is in the way. `type -a maxxwell` lists the file it really runs; check that one,
  and use its path in place of `"$(command -v maxxwell)"` below.
- **`No such file` for an empty name** (`ls: : No such file…` or `cannot access ''`):
  nothing called `maxxwell` is on your `PATH`, so this does not apply to you.

To reinstall, run the block for your platform:

macOS arm64:

```sh
cd "$(mktemp -d)"
curl -fLO https://github.com/rindler-ai/ide-releases/releases/download/v0.1.75/maxxwell-darwin-cli-arm64-global-120.tar.gz
tar -xzf maxxwell-darwin-cli-arm64-global-120.tar.gz
install -m 0755 maxxwell "$(command -v maxxwell)"
```

macOS x64:

```sh
cd "$(mktemp -d)"
curl -fLO https://github.com/rindler-ai/ide-releases/releases/download/v0.1.75/maxxwell-darwin-cli-x64-global-120.tar.gz
tar -xzf maxxwell-darwin-cli-x64-global-120.tar.gz
install -m 0755 maxxwell "$(command -v maxxwell)"
```

Linux x64:

```sh
cd "$(mktemp -d)"
curl -fLO https://github.com/rindler-ai/ide-releases/releases/download/v0.1.75/maxxwell-linux-cli-x64-global-120.tar.gz
tar -xzf maxxwell-linux-cli-x64-global-120.tar.gz
install -m 0755 maxxwell "$(command -v maxxwell)"
```

If the `install` line fails because that location is not writable, nothing has changed;
re-run just that line with `sudo`.

From v0.1.62 on, `maxxwell self-update` downloads from this repository.

## Platform build status

| Platform | Status | Evidence |
| --- | --- | --- |
| macOS | BUILT | arm64 packaged, signed, notarized and stapled on a real Mac, and the .dmg verified against Gatekeeper; target Mach-O modules validated; packaged GUI launch and the native workspace-folder picker were confirmed end-to-end by the founder on v0.1.42 (2026-09-05) -- not independently re-verified per release |
| Linux | BUILT | self-hosted native .tar.gz, .deb, and standalone CLI tarball validated |
| Windows | BUILT | Linux-cross-built unsigned x64 app/CLI ZIPs; target PE modules validated; SmartScreen will warn; packaged GUI launch remains UNVERIFIED |

No declared platform artifacts are pending.
