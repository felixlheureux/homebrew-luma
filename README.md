# Luma Homebrew tap

Development builds of Luma for Apple Silicon Macs running macOS 26 or later.
The package token is `luma` and the installed application is `Luma.app`.

The prepared cask pins the published 0.2.0 installer. It predates current work
on the main branch. It is ad-hoc signed and not notarized. Homebrew preserves
quarantine; Gatekeeper rejected this build in the recorded macOS 27.0.1 test.
This tap does not change macOS security settings or promise first-launch access.

Public installation instructions will be added after the repository exists and
the public tap installation route has been verified.

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
