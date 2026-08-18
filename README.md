# Rindler — published builds

Supervise a fleet of coding agents, and get one honest page of what they could
not do.

This repository publishes **builds only**. The source is private, in
`rindler-ai/rindler-dev-ide`. Nothing here is written by hand: every asset is
produced by that repository's tag-driven release workflow.

## Install

Take the newest build from [Releases](../../releases/latest).

| platform | artifact |
|---|---|
| macOS (Apple silicon) | `Rindler-darwin-arm64.dmg` |
| macOS (Intel) | `Rindler-darwin-x64.dmg` |
| Linux | `Rindler-linux-<arch>.tar.gz` or `rindler_<version>_<arch>.deb` |
| Windows | use the Linux build under WSL — see below |

### macOS

Open the `.dmg` and drag Rindler into Applications. Drag it in rather than
running it from the disk image: an app launched from where the browser left it
runs under App Translocation, from a randomized read-only path.

Builds are **ad-hoc signed and not notarized**, so the first launch says
"Apple could not verify…". Open it from **System Settings → Privacy &
Security → Open Anyway**.

Right-click → Open does *not* work. macOS 15 removed that bypass; Privacy &
Security is the only route.

### Linux

Requires `tmux`. The `.deb` declares it as a dependency; the tarball does not
check.

### Windows

There is no Windows build, on purpose. The IDE drives a real tmux server, and
native Windows has no equivalent — an `.exe` that cannot find tmux is worse than
no `.exe`. Run the Linux build under WSL.

## Verifying a download

Every release carries a `SHA256SUMS.txt` covering all of its artifacts:

```sh
shasum -a 256 -c SHA256SUMS.txt      # macOS
sha256sum -c SHA256SUMS.txt          # Linux
```

`rindler update` verifies against this same file, so an artifact missing from it
is one the updater refuses.
