# homebrew-sigsieve

Homebrew tap for [SigSieve](https://github.com/semihbugrasezer/sigsieve), a
local SSH-agent filtering proxy that forwards only allowlisted identities.

> **Experimental pre-release. Not independently audited.** Read the
> [security model](https://github.com/semihbugrasezer/sigsieve/blob/main/docs/SECURITY_MODEL.md)
> and [limitations](https://github.com/semihbugrasezer/sigsieve/blob/main/docs/LIMITATIONS.md)
> before use, and keep ordinary SSH access available.

## Install

```sh
brew install semihbugrasezer/sigsieve/sigsieve
sigsieve --version
```

The formula builds the tagged release from source with `cargo install
--locked` and verifies the source archive's SHA-256. It installs only the
`sigsieve` binary: no service, no configuration file, no changes to `~/.ssh`
or your SSH agent.

Homebrew's checksum is not GitHub build provenance. If you need verified
build provenance, install the attested release binaries as described in the
[installation guide](https://github.com/semihbugrasezer/sigsieve/blob/main/docs/INSTALL.md).

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
[SECURITY.md](https://github.com/semihbugrasezer/sigsieve/blob/main/SECURITY.md).

License: MIT (formula and SigSieve).
