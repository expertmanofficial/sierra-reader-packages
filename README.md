# sierra-reader-packages

Verified offline reader packages for Sierra.

This repository hosts reader packages, not APKs.

Sierra is a Markdown viewer app. To keep the APK small, Sierra downloads
the needed reader package at first run instead of bundling it.

## Current verified package — Sierra build 110, app version 1.70

- Universal file: sierra-reader-925f528cc0ea89e3ff5020933f24b35343fb0191231942178f5027be2c335705.zip
- Bytes: 67059552
- Expanded bytes: 161613043
- SHA-256: 925f528cc0ea89e3ff5020933f24b35343fb0191231942178f5027be2c335705
- Download: https://github.com/expertmanofficial/sierra-reader-packages/releases/download/reader-pack-v1/sierra-reader-925f528cc0ea89e3ff5020933f24b35343fb0191231942178f5027be2c335705.zip

Channel packs in the same reader-pack-v1 release, each a small
engines/channel.json marker for its channel:

- Stable: sierra-stable-fdae75e02f986e2fca08caed952c3cc75c324ace8c957576aec33828190e26e9.zip — 183 bytes, SHA-256 fdae75e02f986e2fca08caed952c3cc75c324ace8c957576aec33828190e26e9
- Beta: sierra-beta-54f4e799e0d545b3addd04b1f82a80aabc3483476d180997b1602422aa88b261.zip — 181 bytes, SHA-256 54f4e799e0d545b3addd04b1f82a80aabc3483476d180997b1602422aa88b261
- Alpha: sierra-alpha-b448a3ee2e2ed773f1f9665bd0c920ea5add06e9cd33eaf581bdb7cbaa112df1.zip — 182 bytes, SHA-256 b448a3ee2e2ed773f1f9665bd0c920ea5add06e9cd33eaf581bdb7cbaa112df1

Signed update manifest: reader-updates.json in the same release.
It is Ed25519-signed, schema 1, engineApi 1, minAppBuild 110.

See `SHA256SUMS.txt` for the previous pack, and
`stable-reader-pack.json` for the current universal pack values.

## Verification rule

Uploaded archives must not be modified or silently replaced.

Before use, verify the downloaded archive's byte count and SHA-256
against reader-updates.json. If either does not match, do not use it.
