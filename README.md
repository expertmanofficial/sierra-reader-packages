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

## Current packages — app version 1.80

### Universal reader package

- File: sierra-reader-b9fa9ebe0cd6e37e3bd4765712be77d479edd86122951aea698be5ce389232b1.zip
- Bytes: 67271212
- Expanded bytes: 162370172
- SHA-256: b9fa9ebe0cd6e37e3bd4765712be77d479edd86122951aea698be5ce389232b1
- Download: https://github.com/expertmanofficial/sierra-reader-packages/releases/download/reader-pack-v1/sierra-reader-b9fa9ebe0cd6e37e3bd4765712be77d479edd86122951aea698be5ce389232b1.zip

### Channel packages

- Stable: sierra-stable-77558fe4ea8ad1098e0ee28e613ecc6b61374707361d215c08f609cf8c4621be.zip — 1953 bytes, expanded 6279 bytes, SHA-256 77558fe4ea8ad1098e0ee28e613ecc6b61374707361d215c08f609cf8c4621be — https://github.com/expertmanofficial/sierra-reader-packages/releases/download/reader-pack-v1/sierra-stable-77558fe4ea8ad1098e0ee28e613ecc6b61374707361d215c08f609cf8c4621be.zip
- Beta: sierra-beta-811ae9e184467278f9dadfe42226caa35bc139f8a240ccb5f4fa5c2ac9d88270.zip — 4717236 bytes, expanded 22390885 bytes, SHA-256 811ae9e184467278f9dadfe42226caa35bc139f8a240ccb5f4fa5c2ac9d88270 — https://github.com/expertmanofficial/sierra-reader-packages/releases/download/reader-pack-v1/sierra-beta-811ae9e184467278f9dadfe42226caa35bc139f8a240ccb5f4fa5c2ac9d88270.zip
- Alpha: sierra-alpha-31160c2b0a186ece7edaa3ebac3681d965a255fb2169b29dc2cbc58478e5c56c.zip — 1952 bytes, expanded 6278 bytes, SHA-256 31160c2b0a186ece7edaa3ebac3681d965a255fb2169b29dc2cbc58478e5c56c — https://github.com/expertmanofficial/sierra-reader-packages/releases/download/reader-pack-v1/sierra-alpha-31160c2b0a186ece7edaa3ebac3681d965a255fb2169b29dc2cbc58478e5c56c.zip

Stable and Alpha overlays now carry the shared dialect rules (same rules as the Beta package). There is no separate LTS package channel; LTS uses the Stable overlay.

Latest Beta reader package (build 156, app version 1.80): offline UMLet
UXF rendering; DBML files that repeat a relationship inline and as a
top-level Ref; Hugo, Docusaurus and Doxygen instructions classified as
tool-dependent formats rather than malformed text; retryable issue cards
now have a Try again button, including online image errors. The catalog
needs activation before Beta receives the new renderer package; that
activation is a separate step, not done in this release update. Beta
build 156 APK is 35694356 bytes, 16 KB larger than build 155. No APK is
included in this release. The APK compiled and passed release-signing
and reader-package checks, as reported by Codex; it was not verified
visually in Ramus, whose emulator minutes are exhausted. The !Heading
family was already handled inside fenced TiddlyWiki content; outside
that context it remains literal, and !include stays limited to local
Markdown files.

### Signed reader catalog

- reader-updates.json — 1963 bytes, SHA-256 3e82a98ab4a9c81b294e11ef4df3450df9e07748179d9ba9c69680339816f26c, Ed25519-signed, schema 1, engineApi 1, minAppBuild 110
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
