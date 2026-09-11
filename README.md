# Golden Stake Casino — release preparation

Native Android game by **LSD Stone Ltd**. Support: `onlyjessehere@gmail.com`.

## Signed release 4.0.1

A signed Android App Bundle and a universal test APK were built and delivered separately to the owner on **11 September 2026**:

| Field | Value |
|---|---|
| Application ID | `com.goldenstake.casino` |
| Version | `4.0.1` / `40001` |
| Android | min API 26; target API 36 |
| Runtime | Java / Android Views / Canvas; no WebView |
| Audience | Adults 18+, simulated gambling only |
| Money functionality | Virtual credits only; no cash stakes or prizes |

Public package checksums and the certificate fingerprint: [release/4.0.1-verification.json](release/4.0.1-verification.json).

Actual checks: official Android release compilation, bundletool validation, AAB signature, APK v2/v3 signature and alignment passed. Android Lint: **0 errors, 5 documented warnings**. **76 JVM scenarios** passed and **1,000 original game-outcome vectors** were unchanged. All **83 image/audio assets** were preserved byte-for-byte from UI 4.

No physical Android device/emulator execution, Play Console upload, Play App Signing enrollment, or store approval is claimed.

## What is in this repository

This repository currently contains **build infrastructure and verification metadata**, not the complete app source and binary artwork. The full source was delivered as `Golden-Stake-Casino-4.0.1-source.zip`. The available connector did not provide a local binary-file upload operation for synchronizing the full resource pack. Import that complete source snapshot into the repository root before running the app release workflow.

The successful toolchain workflow downloaded official Android SDK 36, Build Tools 36.0.0, Gradle 8.13 and AGP 8.13.2 dependencies. The **actual full-app release build was performed locally** with that toolchain, not on GitHub Actions. The temporary export workflows built only a dependency-warmup app; their green status does not represent the game build.

- [Successful toolchain preparation](https://github.com/RedOctober222333/goldenstake/actions/runs/34627437672)
- [Toolchain export](https://github.com/RedOctober222333/goldenstake/actions/runs/34627856600)
- `android-release.yml`: prepared manual workflow for the complete source checkout. It fails explicitly if the project/resources are missing. Signed builds additionally require the owner's existing upload key in repository Secrets.

## Signing security

A new private upload key was generated locally. The encrypted JKS and its passwords were delivered separately to the owner, **not** committed here, placed in public Actions artifacts, or configured in GitHub Secrets.

Never commit private keys, keystores, passwords, service-account credentials, or the private signing-backup archive. Keep the upload key for future updates. An unsigned CI candidate is clearly labelled and is not a Play upload bundle.

Future signed Actions builds use `GOLDENSTAKE_KEYSTORE_BASE64`, `GOLDENSTAKE_STORE_PASSWORD`, and `GOLDENSTAKE_KEY_PASSWORD` Secrets, after source import. The fixed alias is `goldenstake-upload`.

## Privacy prerequisite

The app uses the owner-supplied URL:
https://doc-hosting.flycricket.io/golsden-stake-casino-privacy-policy/d2b429ad-44ee-4a0d-abba-54967f87bf05/privacy

That page returned HTTP 200, but currently says **Golsden** and claims IP/analytics/AI/SDK data processing that this release does not implement. Correct the page before submission for moderation. Accurate replacement drafts and a review are included in the delivered source ZIP under `docs/privacy/`. The external page itself has not been edited. The app now has a native privacy summary and user-initiated policy/support actions.

A valid AAB is a technical deliverable, not a guarantee of store approval, trademark clearance, or device-level quality.
