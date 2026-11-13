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

## Current packages — app version 1.80-beta

### Universal reader package

- File: sierra-reader-b9fa9ebe0cd6e37e3bd4765712be77d479edd86122951aea698be5ce389232b1.zip
- Bytes: 67271212
- Expanded bytes: 162370172
- SHA-256: b9fa9ebe0cd6e37e3bd4765712be77d479edd86122951aea698be5ce389232b1
- Download: https://github.com/expertmanofficial/sierra-reader-packages/releases/download/reader-pack-v1/sierra-reader-b9fa9ebe0cd6e37e3bd4765712be77d479edd86122951aea698be5ce389232b1.zip

### Channel packages

- Stable: sierra-stable-77558fe4ea8ad1098e0ee28e613ecc6b61374707361d215c08f609cf8c4621be.zip — 1953 bytes, expanded 6279 bytes, SHA-256 77558fe4ea8ad1098e0ee28e613ecc6b61374707361d215c08f609cf8c4621be — https://github.com/expertmanofficial/sierra-reader-packages/releases/download/reader-pack-v1/sierra-stable-77558fe4ea8ad1098e0ee28e613ecc6b61374707361d215c08f609cf8c4621be.zip
- Beta: sierra-beta-dde647b8648e1588404a44692a5a3a5d2d824312c6509b2151df1068d2e8fdf5.zip — 68829836 bytes, expanded 166984668 bytes, SHA-256 dde647b8648e1588404a44692a5a3a5d2d824312c6509b2151df1068d2e8fdf5 — https://github.com/expertmanofficial/sierra-reader-packages/releases/download/reader-pack-v1/sierra-beta-dde647b8648e1588404a44692a5a3a5d2d824312c6509b2151df1068d2e8fdf5.zip
- Alpha: sierra-alpha-31160c2b0a186ece7edaa3ebac3681d965a255fb2169b29dc2cbc58478e5c56c.zip — 1952 bytes, expanded 6278 bytes, SHA-256 31160c2b0a186ece7edaa3ebac3681d965a255fb2169b29dc2cbc58478e5c56c — https://github.com/expertmanofficial/sierra-reader-packages/releases/download/reader-pack-v1/sierra-alpha-31160c2b0a186ece7edaa3ebac3681d965a255fb2169b29dc2cbc58478e5c56c.zip

Stable and Alpha overlays now carry the shared dialect rules (same rules as the Beta package). There is no separate LTS package channel; LTS uses the Stable overlay.

Latest Beta reader package (build 180, app version 1.80-beta): the new
renderer engine and its Markdown support, now in the downloadable Beta
reader package. The shared universal package is unchanged. The catalog
needs activation before Beta receives the new package; that activation
is a separate step, not done in this release update. No APK is included
in this release.

### Signed reader catalog

- reader-updates.json — 2047 bytes, SHA-256 351ff5e14cb3cd3ac13f31979343f526de8376cffab13fd5bcdda6892ab6b1ec, Ed25519-signed, schema 1, engineApi 1, minAppBuild 110
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
