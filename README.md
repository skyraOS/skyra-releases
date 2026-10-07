# Skyra desktop downloads

Skyra runs agents under explicit OS-enforced boundaries and records their
execution for replay. This repository is the official binary distribution
endpoint. The development repository remains private.

**First release pending:** portable packaging is being verified; public
application downloads require Developer ID signing and Apple notarization.
There are no supported installable release assets yet.

After the first release is published:

```sh
brew tap skyraOS/tap
brew install --cask skyra
```

The Homebrew package lives at https://github.com/skyraOS/homebrew-tap.
Releases will contain `Skyra-VERSION-macos-arm64.zip`, its SHA-256 checksum,
and release notes. Initial support is Apple Silicon and macOS 14 or later.

Normal app startup uses a bundled runtime and does not compile source.
Codex support is verified for 0.160.0. Install and authenticate that provider
separately (`npm install -g @openai/codex@0.160.0`, then `codex login`).
The app asks you to grant a workspace before starting an agent.

Updates use `brew update` and `brew upgrade --cask skyra`.
`brew uninstall --cask skyra` removes the application but preserves conversations,
workspaces and provider logins. The archive includes Skyra's FSL-1.1-ALv2 license.
