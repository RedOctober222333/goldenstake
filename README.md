# Golden Stake Casino — release preparation

Native Android game by **LSD Stone Ltd**. Support: `onlyjessehere@gmail.com`.

## Latest signed release: 4.0.2

The current Android App Bundle was rebuilt as **4.0.2 / 40002** and signed with the same upload key as 4.0.1, so it can be uploaded as the next Google Play build.

| Field | Value |
|---|---|
| Application ID | `com.goldenstake.casino` |
| Version | `4.0.2` / `40002` |
| Android | min API 26; target API 36 |
| Runtime | Java / Android Views / Canvas; no WebView |
| Audience | Adults 18+, simulated gambling only |
| Money functionality | Virtual credits only; no cash stakes or prizes |
| AAB SHA-256 | `87f1a7a7e8883e1782e7e74a5419d9e818174d9cca7bda341277276de60910c3` |
| Upload certificate SHA-256 | `81fb0cea8368ea2951ca4c67f5456871a6c93cbc6b3426bde298047a17e75750` |

Public verification metadata is in [release/4.0.2-verification.json](release/4.0.2-verification.json).

### Verification

- Official Android release compilation: PASS
- `bundletool validate`: PASS
- AAB signature: PASS
- Android Lint: **0 errors, 5 documented warnings**
- **76 JVM scenarios** passed
- **1,000 / 1,000** deterministic game-outcome vectors matched the previous verified engine
- No physical Android device/emulator execution or Play Console submission is claimed

## Previous release

Release **4.0.1 / 40001** remains documented under `release/4.0.1-*` for history.

## Repository contents

This repository contains build infrastructure and public verification metadata. Complete source snapshots and signed binaries are delivered separately; private signing material is never committed.

`android-release.yml` is the release workflow for a complete source checkout. Signed builds require the owner's existing upload key through repository Secrets. Never commit the JKS, passwords, Google credentials, service-account keys, or private signing backups.

A valid AAB is a technical deliverable, not a guarantee of store approval, trademark clearance, or device-level quality.
