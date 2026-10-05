# Maxxwell downloads

Latest release: [v0.1.171](https://github.com/rindler-ai/ide-releases/releases/tag/v0.1.171)

## Release identity

- Version: v0.1.171
- Build: global-437
- Source commit: c845fb052cdbe48d3816d3b443e0d11a02c29764
- Staged: October 4, 2026 at 11:25:37 PM PDT

| Platform | Download | Install |
| --- | --- | --- |
| macOS arm64 | [`Maxxwell-darwin-arm64.tar.gz`](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.171/Maxxwell-darwin-arm64.tar.gz) | `tar -xzf Maxxwell-darwin-arm64.tar.gz` |
| macOS x64 | [`Maxxwell-darwin-x64.tar.gz`](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.171/Maxxwell-darwin-x64.tar.gz) | `tar -xzf Maxxwell-darwin-x64.tar.gz` |
| Linux tar | [`Maxxwell-linux-x64.tar.gz`](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.171/Maxxwell-linux-x64.tar.gz) | `tar -xzf Maxxwell-linux-x64.tar.gz` |
| Linux deb | [`maxxwell_0.1.171-global-437_amd64.deb`](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.171/maxxwell_0.1.171-global-437_amd64.deb) | `sudo apt install ./maxxwell_0.1.171-global-437_amd64.deb` |
| Windows x64 (unsigned) | [`Maxxwell-windows-x64.zip`](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.171/Maxxwell-windows-x64.zip) | `Expand-Archive .\Maxxwell-windows-x64.zip` (SmartScreen will warn) |

[SHA256SUMS.txt](https://github.com/rindler-ai/ide-releases/releases/download/v0.1.171/SHA256SUMS.txt) verifies every published artifact.

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
curl -fLO https://github.com/rindler-ai/ide-releases/releases/download/v0.1.171/maxxwell-darwin-cli-arm64-global-437.tar.gz
tar -xzf maxxwell-darwin-cli-arm64-global-437.tar.gz
install -m 0755 maxxwell "$(command -v maxxwell)"
```

macOS x64:

```sh
cd "$(mktemp -d)"
curl -fLO https://github.com/rindler-ai/ide-releases/releases/download/v0.1.171/maxxwell-darwin-cli-x64-global-437.tar.gz
tar -xzf maxxwell-darwin-cli-x64-global-437.tar.gz
install -m 0755 maxxwell "$(command -v maxxwell)"
```

Linux x64:

```sh
cd "$(mktemp -d)"
curl -fLO https://github.com/rindler-ai/ide-releases/releases/download/v0.1.171/maxxwell-linux-cli-x64-global-437.tar.gz
tar -xzf maxxwell-linux-cli-x64-global-437.tar.gz
install -m 0755 maxxwell "$(command -v maxxwell)"
```

If the `install` line fails because that location is not writable, nothing has changed;
re-run just that line with `sudo`.

From v0.1.62 on, `maxxwell self-update` downloads from this repository.

## Platform build status

| Platform | Status | Evidence |
| --- | --- | --- |
| macOS | BUILT | arm64 packaged, signed, notarized and stapled on a real Mac, and the .dmg verified against Gatekeeper; target Mach-O modules validated; no walk of this build was recorded when it was staged; last recorded walk v0.1.42 (2026-09-05): packaged GUI launch and the native workspace-folder picker, end to end, by the founder |
| Linux | BUILT | self-hosted native .tar.gz, .deb, and standalone x64 CLI tarball validated; no walk of this build was recorded when it was staged; last recorded walk v0.1.137 (2026-09-30): update in-app from v0.1.123 with the workspace trust kept and the first send answered |
| Linux arm64 | CLI ONLY | the standalone arm64 CLI tarball is cross-built by the Linux job (pure Go); there is no arm64 app or .deb, because the Electron bundle and node-pty need host-native packaging. Like the x64 CLI tarball it carries the `maxxwell` executable alone and NO bundled tmux -- the tmux pin manifest declares one asset, darwin-arm64 -- so the host supplies tmux, which is what the .deb's `Depends: tmux` already assumes |
| Windows | BUILT | Linux-cross-built unsigned x64 app/CLI ZIPs; target PE modules validated; SmartScreen will warn; no walk of this build was recorded when it was staged; last recorded walk v0.1.137 (2026-09-30): first run to a working seat and two sends (J1) 3/3; update in-app and by ZIP from v0.1.134, v0.1.135 and v0.1.136 6/6; the seat resumed after its tmux server was killed (J3) |

No declared platform artifacts are pending.

Release bar for this build's candidate (its release-bar/<platform> commit statuses on c845fb052cdbe48d3816d3b443e0d11a02c29764, read before publish):
PASS = walked and passed; FAIL = walked and failed; NOT MEASURED = no walk result for this release run.

- linux PASS (release-bar/linux success: rel2: v0.1.171 run 37270379442 fresh5 5/5 refused 0; fresh-kill 5/5; race+race-ml 0/6 doubled; M1 16/16 G-K https://github.com/rindler-ai/maxxwell-ide/actions/runs/37270379442)
- windows PASS (release-bar/windows success: win: v0.1.171 candidate run_id=37270379442 J1 x5 rewalk (orig 5 NO_STEPS: stale app): bar 5/5 (refused distinct 0/0/0/0/0); J1 5/5 https://github.com/rindler-ai/maxxwell-ide/actions/runs/37270379442)
- darwin NOT MEASURED (Mac offline) -- not measured on darwin (no release-bar/darwin status on c845fb052cdbe48d3816d3b443e0d11a02c29764); no step waits on the Mac
