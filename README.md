# Wochenplaner Updates

Public Sparkle update feed and release assets for the **Wochenplaner** macOS app of Köhn Gartenbau AG.

The application source code lives in a private repository. This repo exists only to host:

- `appcast.xml` — the Sparkle update feed
- GitHub Releases — the signed `.zip` bundles Sparkle downloads

## How it works

The Wochenplaner app embeds the URL `https://raw.githubusercontent.com/KoehnGartenbauAG/Wochenplaner-updates/main/appcast.xml` as its `SUFeedURL`. Sparkle checks the feed every hour, finds the latest `<item>`, verifies the EdDSA signature, and installs the update.

## Release process

Releases are produced by the private repository's `release.sh` script. The script:

1. Builds, signs, and zips the app.
2. Updates this repo's `appcast.xml` with a new `<item>` and a fresh EdDSA signature.
3. Creates a GitHub Release here with the `.zip` as an asset.

This repo should never be edited directly.
