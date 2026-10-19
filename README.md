# Luma Homebrew tap

Development builds of Luma for Apple Silicon Macs running macOS 26 or later.
The package token is `luma` and the installed application is `Luma.app`.

The cask pins the published 0.2.1 installer, including direct cleanup/Undo,
requested Storage discovery, Overview and the menu companion, M2 battery
reporting, and explicit Maintenance cache/local-Trash/memory actions.
It is ad-hoc signed and not notarized. Homebrew preserves quarantine; this tap
does not change macOS security settings or promise first-launch access.

Install the development build:

```sh
brew install --cask felixlheureux/luma/luma
```

Upgrade an existing Homebrew installation:

```sh
brew upgrade --cask felixlheureux/luma/luma
```

Verified from this public GitHub tap with Homebrew 7.0.9 on Apple Silicon/macOS
27.0.1. The fully qualified command trusts this cask only; no whole-tap trust is
needed. Installation succeeds, but successful first launch is not established
for this unnotarized release. See [Homebrew tap trust](https://docs.brew.sh/Tap-Trust).

The 0.2.0 → 0.2.1 upgrade and app-only removal were checked in a disposable
app directory. Activity/history, ignore choices and appearance/menu preferences
remain unchanged. The installed arm64 app keeps quarantine and passes strict
signature verification; Gatekeeper assessment rejects this unnotarized build on
macOS 27.0.1. No first-launch or security bypass is claimed.

Cask validation uses Homebrew style and online audit. The exact prerelease is
listed in `audit_exceptions/github_prerelease_allowlist.json`; this declares the
development channel and is not a signing or security exception. The cask uses a
plain app artifact, requests normal Quit during upgrade/removal, and contains no
zap, user-data deletion, helper installation or security-changing script.

Maintainers prepare updates using `Scripts/prepare_homebrew.py` in the Luma
source repository. It verifies an already-published release, checksum and app
payload before replacing the proposed cask. Review its output and the exact
prerelease declaration, then run style/audit and test installation, upgrade and
removal before pushing this tap. Updates are reviewed; no cross-repository write
token or automatic publication is configured.

Licensed GPL-3.0-or-later. See LICENSE.
