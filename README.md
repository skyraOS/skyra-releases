# Skyra desktop downloads

Skyra runs agents under explicit OS-enforced boundaries and records their
execution for replay. This repository is the official binary distribution
endpoint. The development repository remains private.

**Skyra 0.1.1 is available** for Apple Silicon Macs running macOS 14 or later.

```sh
brew update
brew install --cask skyraOS/tap/skyra
```

This release uses ad-hoc signatures, without Apple Developer ID or notarization.
Homebrew keeps quarantine enabled. If macOS blocks first launch, review the app
in **System Settings > Privacy & Security** and choose **Open Anyway** if you
trust the download. A paid Apple Developer membership is not required to install.

The Homebrew package lives at https://github.com/skyraOS/homebrew-tap.
Releases contain `Skyra-VERSION-macos-arm64.zip`, its SHA-256 checksum,
and release notes. Initial support is Apple Silicon and macOS 14 or later.

Normal app startup uses a bundled runtime and does not compile source.
Codex support is verified for 0.160.0. Install and authenticate that provider
separately (`npm install -g @openai/codex@0.160.0`, then `codex login`).
The app asks you to grant a workspace before starting an agent.

Updates use `brew update` and `brew upgrade --cask skyra`.
`brew uninstall --cask skyra` removes the application but preserves conversations,
workspaces and provider logins. The archive includes Skyra's FSL-1.1-ALv2 license.

Homebrew installs Python 3.13. Optional desktop observation requires CuaDriver
0.34.0 and macOS Accessibility and Screen Recording permissions. Skyra starts
without desktop observation when the driver is absent.

Skyra 0.1.1 has passed relocated real Cua/backend startup and fake-provider
read/write/replay checks, with application bundle integrity preserved. Independent clean-Mac GUI, real-provider and TCC
acceptance have not been completed. See release notes for validation details.
