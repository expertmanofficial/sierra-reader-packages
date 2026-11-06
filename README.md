# sierra-reader-packages

Verified offline reader packages for Sierra.

This repository hosts reader packages, not APKs.

Sierra is a Markdown viewer app. To keep the APK small, Sierra downloads
the needed reader package at first run instead of bundling it.

## Issues: what is accepted here

This repository is NOT the Sierra app repository. It is only about
reader packages, that is, Markdown types and the reader engines and
packages that render them.

Accepted here:
- A reader pack, channel pack, or universal pack that fails to download
- A byte count or SHA-256 mismatch for a pack in a release
- A problem with reader-updates.json, a channel, or an engine in a pack
- A Markdown type that a pack should render but does not, with a
  minimal example and the pack filename and channel

Not accepted here, and automatically closed:
- Sierra app issues: the app interface, installation, APKs, accounts,
  features, or any bug in the Sierra app itself
- Feature requests for the Sierra app
- Anything unrelated to reader packages or this repository's role

Any issue that is not about reader packages will be automatically
closed by the repository's GitHub Action, with a comment explaining
this scope. See the pinned issue on the Issues page for the full
rules. If an issue was closed in error, reopen it with the pack
filename, channel, download URL, expected and actual byte count and
SHA-256 if relevant, and steps to reproduce it.

## Current verified package — Sierra build 113, app version 1.70

- Universal file: sierra-reader-b9fa9ebe0cd6e37e3bd4765712be77d479edd86122951aea698be5ce389232b1.zip
- Bytes: 67271212
- Expanded bytes: 162370172
- SHA-256: b9fa9ebe0cd6e37e3bd4765712be77d479edd86122951aea698be5ce389232b1
- Download: https://github.com/expertmanofficial/sierra-reader-packages/releases/download/reader-pack-v1/sierra-reader-b9fa9ebe0cd6e37e3bd4765712be77d479edd86122951aea698be5ce389232b1.zip

Build 113 changes, as reported by Codex: redesigned package setup with
clear stages, then Open Sierra when ready, with no automatic redirect;
added Cyberpunk Neon, with black surfaces and green glows behind
controls and cards; continued MyST, image-safety and notice fixes;
removed Request from inline R. All four main channels passed source
compilation. No APKs were built and no device visuals were verified
for this build.

## Beta build 121 — optional translator runtime, app version 1.70

- Optional translator runtime file: libtranslate-jni-arm64-v1.so
- Bytes: 16361048
- SHA-256: 35b3d0366291347e3f25e80e809ee398d716aea49cd03278007fedd526a1496f
- Download: https://github.com/expertmanofficial/sierra-reader-packages/releases/download/reader-pack-v1/libtranslate-jni-arm64-v1.so

Beta build 121, as reported by Codex: Markdown reading no longer waits for a package download. Reader tools are optional, and Home now has a direct "Having trouble? Get help" link. The APK is about 45.4 MB, down from build 120's 61.7 MB; the translator library is no longer bundled. Stable was not changed. The matching Beta APK verifies this exact size and SHA-256 before loading the library. Do not rename or modify the file. Offline translation will not work until this asset is publicly available. Ordinary Markdown reading and all other app functions do not depend on this asset. No APK is included in this release.

## Beta build 125 — translator runtimes for all ABIs, app version 1.70

- Optional translator runtimes, one per device ABI. Sierra downloads only the runtime matching the device architecture and verifies its exact size and SHA-256 before loading it.
- armeabi-v7a: libtranslate-jni-armeabi-v7a-v1.so — 11608808 bytes, SHA-256 cdf803c7a17cadf5f53314365dd3c999746d98c510863c636de62c7acd8cb016 — https://github.com/expertmanofficial/sierra-reader-packages/releases/download/reader-pack-v1/libtranslate-jni-armeabi-v7a-v1.so
- x86: libtranslate-jni-x86-v1.so — 17258012 bytes, SHA-256 8501cf6c07570a276539399d2e63b7f3f9f46714b33607599a28ab6b3f33878e — https://github.com/expertmanofficial/sierra-reader-packages/releases/download/reader-pack-v1/libtranslate-jni-x86-v1.so
- x86_64: libtranslate-jni-x86_64-v1.so — 17371632 bytes, SHA-256 d7e1b7be14a5cd2c20331c9a511efb3e98b777347abf7eb9bce9166fcb246975 — https://github.com/expertmanofficial/sierra-reader-packages/releases/download/reader-pack-v1/libtranslate-jni-x86_64-v1.so
- Reused, unchanged: libtranslate-jni-arm64-v1.so — 16361048 bytes, SHA-256 35b3d0366291347e3f25e80e809ee398d716aea49cd03278007fedd526a1496f — https://github.com/expertmanofficial/sierra-reader-packages/releases/download/reader-pack-v1/libtranslate-jni-arm64-v1.so

Beta build 125, as reported by Codex: build 121 translation could not start on an x86_64 device because Beta only knew how to download the ARM64 library. Build 125 chooses the translation engine for the device's ABI. Build 125 compiled and installed in Ramus. No APK is included in this release.

Channel packs in the same reader-pack-v1 release, each a small
engines/channel.json marker for its channel, unchanged from build 110:

- Stable: sierra-stable-fdae75e02f986e2fca08caed952c3cc75c324ace8c957576aec33828190e26e9.zip — 183 bytes, SHA-256 fdae75e02f986e2fca08caed952c3cc75c324ace8c957576aec33828190e26e9
- Beta: sierra-beta-54f4e799e0d545b3addd04b1f82a80aabc3483476d180997b1602422aa88b261.zip — 181 bytes, SHA-256 54f4e799e0d545b3addd04b1f82a80aabc3483476d180997b1602422aa88b261
- Alpha: sierra-alpha-b448a3ee2e2ed773f1f9665bd0c920ea5add06e9cd33eaf581bdb7cbaa112df1.zip — 182 bytes, SHA-256 b448a3ee2e2ed773f1f9665bd0c920ea5add06e9cd33eaf581bdb7cbaa112df1

Signed update manifest: reader-updates.json in the same release.
It is Ed25519-signed, schema 1, engineApi 1, minAppBuild 110 as in the
manifest file for build 113.

Previous universal packs remain in this release as assets, including
build 112 and build 110.

See `stable-reader-pack.json` for the current universal pack values.

## Verification rule

Uploaded archives must not be modified or silently replaced.

Before use, verify the downloaded archive's byte count and SHA-256
against reader-updates.json. If either does not match, do not use it.
