# homebrew-sigsieve

Homebrew tap for [SigSieve](https://github.com/semihbugrasezer/sigsieve), a
local SSH-agent filtering proxy that forwards only allowlisted identities.

> **Stable release (v1.0.0). Not independently audited.** Read the
> [security model](https://github.com/semihbugrasezer/sigsieve/blob/v1.0.0/docs/SECURITY_MODEL.md)
> and [limitations](https://github.com/semihbugrasezer/sigsieve/blob/v1.0.0/docs/LIMITATIONS.md)
> before use, and keep ordinary SSH access available.

## Install

```sh
brew install semihbugrasezer/sigsieve/sigsieve
sigsieve --version
```

Expected: `sigsieve 1.0.0`.

Use the full name `semihbugrasezer/sigsieve/sigsieve`. Homebrew 7 then trusts
this one formula, not the whole tap, and prints
`Trusted formula semihbugrasezer/sigsieve/sigsieve`. This is the tested
install path. Other paths, such as `brew tap` followed by a short-name
install, are not tested.

The formula builds the tagged release from source with `cargo install
--locked` and verifies the source archive's SHA-256. It installs only the
`sigsieve` binary: no service, no configuration file, no changes to `~/.ssh`
or your SSH agent.

Homebrew's checksum is not GitHub build provenance. If you need verified
build provenance, install the attested release binaries as described in the
[installation guide](https://github.com/semihbugrasezer/sigsieve/blob/main/docs/INSTALL.md).

## Upgrade

How this was verified: an upgrade from `v0.1.0-alpha.4` to `1.0.0` passed
(maintainer-reported; the exact command was not recorded). That a full-name
`brew upgrade` also trusts the formula is based on Homebrew's source
(`cmd/upgrade.rb`), not on a recorded run. With that caveat, upgrade with the
full name:

```sh
brew update && brew upgrade semihbugrasezer/sigsieve/sigsieve
sigsieve --version
```

Expected: `sigsieve 1.0.0` for the current formula.

## Uninstall

```sh
brew uninstall sigsieve
brew untap semihbugrasezer/sigsieve
```

## Updating this tap

The formula is maintained in the main repository at
[`packaging/homebrew/sigsieve.rb`](https://github.com/semihbugrasezer/sigsieve/blob/main/packaging/homebrew/sigsieve.rb);
`Formula/sigsieve.rb` here is a reviewed copy of it. Report problems in the
[main repository](https://github.com/semihbugrasezer/sigsieve/issues), and
security issues as described in its
[SECURITY.md](https://github.com/semihbugrasezer/sigsieve/blob/v1.0.0/SECURITY.md).

License: MIT (formula and SigSieve).
