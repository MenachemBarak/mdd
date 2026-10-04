# MDD

Official release distribution for **MDD**, the `.mdd` Markdown-and-diagram
document editor for Visual Studio Code.

An `.mdd` document is a self-contained HTML-backed file. It can be opened
standalone in a browser, edited through its embedded UI, or edited as source.
The editor and bundled renderers work offline: no runtime server, CDN, npm
installation, or build step is required to open a document.

## Download and install

- [Latest official release](https://github.com/MenachemBarak/mdd/releases/latest)
- [MDD 0.10.3 release notes](https://github.com/MenachemBarak/mdd/releases/tag/v0.10.3)
- [Download mdd-0.10.3.vsix](https://github.com/MenachemBarak/mdd/releases/download/v0.10.3/mdd-0.10.3.vsix)
- [SHA256SUMS](https://github.com/MenachemBarak/mdd/releases/download/v0.10.3/SHA256SUMS)

Requires Visual Studio Code **1.96.0 or newer**.

1. Download the VSIX and verify its SHA-256 against `SHA256SUMS`.
2. In VS Code, open Extensions, choose **Install from VSIX...** from the
   Extensions menu, and select `mdd-0.10.3.vsix`.
3. Reload the VS Code window when prompted, then open an `.mdd` file.

Alternatively, from the download directory:

```sh
code --install-extension mdd-0.10.3.vsix
```

Approved 0.10.3 archive SHA-256:

```text
571578b4059de43c23e7afe6c5c56bec616695f52111307703722de7067d40ef
```

## What's new in 0.10.3

- **R19:** body text aligns with its own heading: H1/body at 0 px,
  H2/body at 32 px, and H3/body at 64 px. Structural indentation starts
  with subtitles; authored and list indentation remain additive.
- **R20:** continuous indentation guides start at the row indentation
  boundary, before markers, without margin gaps; coverage includes
  right-to-left, nested, wrapped, and empty rows.
- **R22:** the outline is closed by default and opens/closes with its
  user button. Toggling the outline changes only the view.

**R21**, inserting a diagram inside an empty LI2, is **not included** and
remains under development. The embedded diagram engine stays at **1.66.0**;
existing table-cut, parser, Undo/caret, older-file editing/light-red alert,
backup, and portable-prompt behavior are retained.

### 0.10.3 verification scope

Guest normal-hook validation reported **95/95**. The initial composed run
reported **181/182** with an AddBox timeout; the unchanged isolated assertion
passed **1/1**. The original composed failure is retained: no full green
182-case rerun is claimed. Final independent integration review passed
**6/6** unchanged normal-hook checks and **14/14** focused-selector checks.

Exact-package Linux native VS Code dark/light Save/Reopen checks passed,
including H1/body 0 px, H2/body 32 px, 1 px list stripes with no gaps, and
closed-by-default outline, while preserving canonical payload and game bytes.
No new full Ring 2 or Windows native validation is claimed. The optional
additional active-highlight assertion was not run.

The original R19 RED commit bypassed hooks using NUL. That deviation remains
disclosed; the subsequent proper normal-hook guest RED replay was verified.
See the release notes for the full scope and limitations.

## What's new in 0.10.2

- Bundled **html-diagrams v1.66.0**: offline Mermaid palettes/custom colours,
  sparse connector controls at true bends, and view-only fit-on-open.
- Left-aligned page, structural heading guides, and current-heading breadcrumb.
- Per-row/per-column table hover insertion, deletion, and selection controls;
  table selection supports copy/cut/delete.
- Native cut reentrancy, one-column Save/Reopen, and history caret fixes.

### Release validation and known QA issue

The controlled Ring 2 gate passed **105/105 files**, concurrency **8**, in
**194.824 seconds**, with no final failures/nonzero exits, but **one recorded
timeout retry/flaky result** for
`diagram-engine-162.browser-1-ui-text.test.mjs`.

An earlier negative-origin fit failure under heavy **31-way** concurrency
remains **OPEN and UNDIAGNOSED**. Three current targeted exact passes and the
final eight-way fit pass do not prove that earlier root cause fixed. The
timeout retry is not claimed diagnosed. This is a non-destructive view-fit
finding, not an authored-data rewrite; not every run was a perfect strict pass.

OS clipboard workflow proof is from isolated guest **Linux native** tests on
the exact package. Previous **Windows native R13-R17/UI** proof covers the
same UI core; no new Windows native clipboard proof is claimed.
See the release notes for the full validation scope.

## Version compatibility in 0.10.3

Current-version and supported older local documents are **editable normally**
through the owned MDD editor using the trusted current runtime. A small,
theme-aware **light-red alert** explains that saving upgrades an older file
and that the original is backed up.

Opening a clean file does not rewrite it or create a backup. Before the first
native buffer mutation, MDD creates and verifies a uniquely named, create-only
backup of the exact original on-disk bytes. The first edit includes the guarded
one-time runtime upgrade, protecting subsequent File Save/autosave and the MDD
Save command after edits through the owned MDD path. Changed disk bytes or
backup failures abort the mutation and retain the draft.

Dirty local documents are backed up and upgraded in the trusted buffer before
an editable MDD view is exposed, preserving unsaved canonical content. Existing
backups, including earlier explicitly chosen fixed paths, are never overwritten.

The compatibility registry includes 0.10.0, 0.10.1, and these 29 historical schema-1 releases:
0.2.0, 0.3.0, 0.3.1, 0.4.0, 0.4.1, 0.5.0, 0.5.1, 0.6.0, 0.6.1, 0.6.2,
0.6.3, 0.6.4, 0.7.0, 0.8.0, 0.8.1, 0.8.2, 0.8.3, 0.8.4, 0.9.0, 0.9.1,
0.9.2, 0.9.3, 0.9.4, 0.9.5, 0.9.6, 0.9.7, 0.9.8, 0.9.9, and 0.9.10.

### Portable upgrade prompts

Upgrade prompts identify the official GitHub release, versioned VSIX, and
checksum, and locate the installed provider dynamically:

```sh
code --locate-extension menachembarak.mdd
```

No machine-specific extension installation path is assumed. Explicit
agent-driven migration retains its SHA, backup, and concurrency guards.

### Limits

- Remote/virtual automatic upgrades are blocked read-only.
- Raw Text Editor changes/saves outside the owned MDD path are not covered by
  the automatic migration/backup guarantee.
- Newer versions and unknown or unsupported profiles remain read-only.
  Unknown schemas/features are not promised supported; files are not
  down-migrated.

[Historical 0.10.0](https://github.com/MenachemBarak/mdd/releases/tag/v0.10.0)
retains its original read-only-until-explicit-migration behavior and release notes.
[Historical 0.10.1](https://github.com/MenachemBarak/mdd/releases/tag/v0.10.1)
retains its original release notes and assets.
[Historical 0.10.2](https://github.com/MenachemBarak/mdd/releases/tag/v0.10.2)
retains its original release notes, assets, and recorded QA limitations.

## Distribution scope

This repository contains official release documentation, not imported
development history. The 0.10.3 VSIX is the exact independently reviewed and
approved archive, unchanged from its verification. The official release notes
record its publication and limitations.

Third-party notices remain bundled in the VSIX. This distribution does not
declare a project-wide license.
