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

## Current packages — app version 1.70

### Universal reader package

- File: sierra-reader-b9fa9ebe0cd6e37e3bd4765712be77d479edd86122951aea698be5ce389232b1.zip
- Bytes: 67271212
- Expanded bytes: 162370172
- SHA-256: b9fa9ebe0cd6e37e3bd4765712be77d479edd86122951aea698be5ce389232b1
- Download: https://github.com/expertmanofficial/sierra-reader-packages/releases/download/reader-pack-v1/sierra-reader-b9fa9ebe0cd6e37e3bd4765712be77d479edd86122951aea698be5ce389232b1.zip

### Channel packages

- Stable: sierra-stable-fdae75e02f986e2fca08caed952c3cc75c324ace8c957576aec33828190e26e9.zip — 183 bytes, SHA-256 fdae75e02f986e2fca08caed952c3cc75c324ace8c957576aec33828190e26e9 — https://github.com/expertmanofficial/sierra-reader-packages/releases/download/reader-pack-v1/sierra-stable-fdae75e02f986e2fca08caed952c3cc75c324ace8c957576aec33828190e26e9.zip
- Beta: sierra-beta-3c5e89f9933b08108cf96f1558a2aa844ac859890ef9af834dff8dc73b31c288.zip — 1951 bytes, expanded 6277 bytes, SHA-256 3c5e89f9933b08108cf96f1558a2aa844ac859890ef9af834dff8dc73b31c288 — https://github.com/expertmanofficial/sierra-reader-packages/releases/download/reader-pack-v1/sierra-beta-3c5e89f9933b08108cf96f1558a2aa844ac859890ef9af834dff8dc73b31c288.zip
- Alpha: sierra-alpha-b448a3ee2e2ed773f1f9665bd0c920ea5add06e9cd33eaf581bdb7cbaa112df1.zip — 182 bytes, SHA-256 b448a3ee2e2ed773f1f9665bd0c920ea5add06e9cd33eaf581bdb7cbaa112df1 — https://github.com/expertmanofficial/sierra-reader-packages/releases/download/reader-pack-v1/sierra-alpha-b448a3ee2e2ed773f1f9665bd0c920ea5add06e9cd33eaf581bdb7cbaa112df1.zip

Latest Beta dialect package (build 147): Slack formatting and mentions,
Discord spoilers, mentions, channel IDs and -# subtext, and escaped
punctuation in the chat dialect examples. Quote handling preserves the
quote markers while applying those rules to the quoted text. Build 147
also has an APK-side fix, not in this release: it recognizes
:/resource-id as a Joplin attachment reference, so it will not send it
to the local image picker.

### Signed reader catalog

- reader-updates.json — 1947 bytes, SHA-256 f23f9e4bbc90575a7cc5cce6782c97166b07b2cc5685042584a6074ea97d8644, Ed25519-signed, schema 1, engineApi 1, minAppBuild 110
- Download: https://github.com/expertmanofficial/sierra-reader-packages/releases/download/reader-pack-v1/reader-updates.json
- The catalog points each channel at its current package above.

### Optional translator runtimes (Beta)

One per device ABI. Sierra downloads only the runtime matching the device
architecture and verifies its exact size and SHA-256 before loading it.

- armeabi-v7a: libtranslate-jni-armeabi-v7a-v1.so — 11608808 bytes, SHA-256 cdf803c7a17cadf5f53314365dd3c999746d98c510863c636de62c7acd8cb016 — https://github.com/expertmanofficial/sierra-reader-packages/releases/download/reader-pack-v1/libtranslate-jni-armeabi-v7a-v1.so
- x86: libtranslate-jni-x86-v1.so — 17258012 bytes, SHA-256 8501cf6c07570a276539399d2e63b7f3f9f46714b33607599a28ab6b3f33878e — https://github.com/expertmanofficial/sierra-reader-packages/releases/download/reader-pack-v1/libtranslate-jni-x86-v1.so
- x86_64: libtranslate-jni-x86_64-v1.so — 17371632 bytes, SHA-256 d7e1b7be14a5cd2c20331c9a511efb3e98b777347abf7eb9bce9166fcb246975 — https://github.com/expertmanofficial/sierra-reader-packages/releases/download/reader-pack-v1/libtranslate-jni-x86_64-v1.so
- arm64: libtranslate-jni-arm64-v1.so — 16361048 bytes, SHA-256 35b3d0366291347e3f25e80e809ee398d716aea49cd03278007fedd526a1496f — https://github.com/expertmanofficial/sierra-reader-packages/releases/download/reader-pack-v1/libtranslate-jni-arm64-v1.so

See `stable-reader-pack.json` for the current universal pack values.

## Verification rule

Uploaded archives must not be modified or silently replaced.

Before use, verify the downloaded archive's byte count and SHA-256
against reader-updates.json. If either does not match, do not use it.
