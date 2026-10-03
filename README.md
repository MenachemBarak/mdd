# MDD

Official release distribution for **MDD**, the `.mdd` Markdown-and-diagram
document editor for Visual Studio Code.

An `.mdd` document is a self-contained HTML-backed file. It can be opened
standalone in a browser, edited through its embedded UI, or edited as source.
The editor and bundled renderers work offline: no runtime server, CDN, npm
installation, or build step is required to open a document.

## Download and install

- [Latest official release](https://github.com/MenachemBarak/mdd/releases/latest)
- [MDD 0.10.0 release notes](https://github.com/MenachemBarak/mdd/releases/tag/v0.10.0)
- [Download mdd-0.10.0.vsix](https://github.com/MenachemBarak/mdd/releases/download/v0.10.0/mdd-0.10.0.vsix)
- [SHA256SUMS](https://github.com/MenachemBarak/mdd/releases/download/v0.10.0/SHA256SUMS)

Requires Visual Studio Code **1.96.0 or newer**.

1. Download the VSIX and verify its SHA-256 against `SHA256SUMS`.
2. In VS Code, open Extensions, choose **Install from VSIX...** from the
   Extensions menu, and select `mdd-0.10.0.vsix`.
3. Reload the VS Code window when prompted, then open an `.mdd` file.

Alternatively, from the download directory:

```sh
code --install-extension mdd-0.10.0.vsix
```

Approved 0.10.0 archive SHA-256:

```text
da683a82fcb7791f7e7532c292d5c5f578ef4b533442cbf91913b063addbdcc0
```

## Version compatibility in 0.10.0

Current-version documents are editable. Supported older documents are opened
**read-only** using the trusted current runtime; opening or saving does not
silently migrate them. Use the offered **Copy upgrade prompt** for an explicit,
SHA-guarded migration with an exact-byte backup before editing an older file.

The compatibility registry covers 29 historical schema-1 releases:
0.2.0, 0.3.0, 0.3.1, 0.4.0, 0.4.1, 0.5.0, 0.5.1, 0.6.0, 0.6.1, 0.6.2,
0.6.3, 0.6.4, 0.7.0, 0.8.0, 0.8.1, 0.8.2, 0.8.3, 0.8.4, 0.9.0, 0.9.1,
0.9.2, 0.9.3, 0.9.4, 0.9.5, 0.9.6, 0.9.7, 0.9.8, 0.9.9, and 0.9.10.

Unregistered versions, unknown schemas, and unsupported features are not
promised to work. Newer files are not down-migrated. Direct editing of older
files and a light-red compatibility alert are **not included in 0.10.0**.

## Distribution scope

This repository contains official release documentation, not imported
development history. The 0.10.0 VSIX is the exact independently reviewed and
approved archive, unchanged from its verification. Some bundled documentation
still labels that frozen artifact a candidate; the official release notes
record its publication and limitations.

Third-party notices remain bundled in the VSIX. This distribution does not
declare a project-wide license.
