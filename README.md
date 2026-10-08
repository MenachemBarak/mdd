# MDD

Official release distribution for **MDD**, the `.mdd` Markdown-and-diagram
document editor for Visual Studio Code.

An `.mdd` document is a self-contained HTML-backed file. It can be opened
standalone in a browser, edited through its embedded UI, or edited as source.
The editor and bundled renderers work offline: no runtime server, CDN, npm
installation, or build step is required to open a document.

## Download and install

- [Latest official release](https://github.com/MenachemBarak/mdd/releases/latest)
- [MDD 0.10.10 release notes](https://github.com/MenachemBarak/mdd/releases/tag/v0.10.10)
- [Download mdd-0.10.10.vsix](https://github.com/MenachemBarak/mdd/releases/download/v0.10.10/mdd-0.10.10.vsix)
- [SHA256SUMS](https://github.com/MenachemBarak/mdd/releases/download/v0.10.10/SHA256SUMS)

Requires Visual Studio Code **1.96.0 or newer**.

1. Download the VSIX and verify its SHA-256 against `SHA256SUMS`.
2. In VS Code, open Extensions, choose **Install from VSIX...** from the
   Extensions menu, and select `mdd-0.10.10.vsix`.
3. Reload the VS Code window when prompted, then open an `.mdd` file.

Alternatively, from the download directory:

```sh
code --install-extension mdd-0.10.10.vsix
```

Official 0.10.10 archive SHA-256:

```text
cab12bd7d67ecefa53a4f990c508f72c75c47db534d89d7d23d3bab97e75f9bf
```

## What's new in 0.10.10

- Open a local UTF-8 Markdown file renamed from `.md` to `.mdd` to convert it
  automatically. MDD verifies a create-only backup of the original bytes before
  its guarded save, disables scripts in the initial raw document, and waits for
  the exact raw tab to close before opening a fresh trusted HTML editor.
  This does not associate `.md` files with MDD or convert documents back to Markdown.
- Select words and paste a URL to retain their label and formatting. Supported
  HTTP(S)/mailto links offer hover **Edit** and Ctrl/Cmd-click navigation.
- Enter on a blank heading creates ordinary paragraph content; intentionally
  authored empty headings remain distinct. Valid same-version documents with
  stale compatible runtime metadata are classified separately from genuinely
  newer or malformed documents.
- Shared outer Tab and list Enter behavior covers eight atom providers within
  the supported editing contract, retaining live media frames and playback.
- Bundled diagram engine **1.67.0** restores saved zoom and world center, with
  its map collapsed by default. Native diagrams, Excalidraw and Three.js gain
  saved views while preserving keyboard authoring history.
- Native Save verifies disk content before reporting **Saved**. A correlated
  old-baseline result permits one guarded retry for the exact document URI,
  not recursive workspace edits.

### 0.10.10 verification scope

Validation is **composed**: 64 normal-hook source checks and 38 exact-VSIX
native cases, plus 40 archive/source mappings, CRC, privacy and bundled-license
checks. Actual default-open and guide screenshots are included in the retained
evidence. These are bounded source gates and native proofs, not a clean full
suite or a clean full-native aggregate; the failed oversized aggregate remains
retained. Publication uses the exact approved archive without rebuilding.

Save repair proof uses controlled old-disk injection in actual VS Code, alongside
ordinary native Save passes. The earlier diagnostic trace may itself have
triggered a save-participant budget abort; it is not proof of spontaneous data
loss or a vulnerability in 0.10.8.

Native proof is from the isolated guest, not new Windows-host UI testing.
Existing Windows windows can keep the older loaded extension until reloaded;
installation alone does not prove their loaded version. No under-120-second
test-suite result is claimed. Private historical 0.10.9 compatibility does not
represent an additional public release.

## What's new in 0.10.8

Atomic editing repairs (R27, R29-R31, R33, R34) cover Enter, Tab/Shift+Tab,
copy, cut, paste, Backspace, list numbering and heading-rank changes within
the supported ownership/content contract, with single-edit history behavior.

Declared list starts and relative content order are preserved. Surviving
sibling ordinals compact after structural edits; their old ordinal numbers
are not promised unchanged. Heading-rank handling respects owned and manually
indented content. The strict `v1-list-items` registry retains 0.10.4 through
0.10.8 with unchanged schema fields.

This is a limited shared editing contract, not complete parity across all
providers or platforms. **Saved views remain pending and excluded.** The
embedded diagram engine remains **1.66.0**; saved-viewport engine 1.67 and MDD9
are not included.

### 0.10.8 verification scope

Proof is **composed** from frozen core, actual OS clipboard/R31, cross-ancestry
and list/plain R33, heading, guide-pixel and model/history evidence. Five
remaining native cross cases passed their one-revision, Undo/Redo/caret,
URI/version Save and reopen checks. Heading columns matched in dark and light
themes with 0 px deviation; owned/manual/native-parent/gap cases passed.
The final differential guide check found no missing or uncovered active guide
pixels in either theme, distinguished persistent non-guide breadcrumb pixels,
and included removed-guide and one-pixel-hole controls.

The combined hook checks passed 100 cases; fresh model history covered 100
seeds at 30 steps each. These are composed scopes, not a new full suite.
No full Windows-native, all-provider, full-suite or all-task result is claimed.
Publication distributes the exact approved archive without rebuilding it.

## What's new in 0.10.7

R32 continuous indentation guides cover headings, breadcrumbs, blank lines,
lists, and component padding. Shared ancestor guides continue across equal-depth
headings and stop on actual outdents. Same-list root-owned sibling margins stay
continuous; non-list/fullscreen/outdent boundaries prevent erroneous bridges.

Failed marker measurements fall back to a parent checkbox/control or logical
indentation boundary. Precise native marker-ink alignment is claimed only for
measured styles, not for custom-style logical-boundary fallbacks.

0.10.6 Delete, persistent breadcrumbs, caret behavior, and diagram engine 1.66.0
are retained. Atomic Enter/Tab/Paste/numbering/Backspace and saved-view support
are not included; private engine 1.67 saved-viewport work remains separate.
The unchanged `v1-list-items` profile registers 0.10.4 through 0.10.7.

### 0.10.7 verification scope

Proof is composed and source-frozen: the broad Linux dark/light, scroll,
fallback, shared-ancestor, and save/reopen matrix belongs to the historical
`18649…` baseline, which later showed 15 missing rows in a 16 px same-list
root-sibling margin. That candidate is not shipped.

The corrected `f393…` package has narrow exact-installed native proof for the
fixed sibling case and two unpainted outdent/reused-list controls, with frame
identity, document version, and dirty state unchanged. Parent source review
covered the original painter/fallback plus the 18-line root-run correction.
No broad corrected-package matrix, narrow save/reopen rerun, full 105-case
suite, or real Windows-host proof is claimed. See release notes for details.

## What's new in 0.10.6

- Delete exits a collapsed, empty ordinary numbered item like Enter.
  Existing nested ordinary-item outdent behavior is retained. A complete,
  top-level owned empty prose item clears ownership; nested or continued
  owned cases refuse with zero edits.
- Persistent breadcrumbs default to all headings, including the current leaf.
  An existing per-document `false` setting remains OFF.
- Bold current-line highlighting follows the actual caret, not hover or a
  stale cached selection.

The `v1-list-items` profile retains 0.10.4, 0.10.5, and 0.10.6 compatibility.
The embedded diagram engine remains **1.66.0**; existing insertion/paste
refusal limits and backup protections remain.

### 0.10.6 verification scope

Pre-publication real-tests-only RED evidence used the normal guest hook;
the original RED replay also used the normal public hook. Unchanged
normal-hook checks passed **60/60**, and scoped checks passed **68/68**.
These are separate scopes, not a combined full-suite result.

Exact-package native Linux VS Code DARK and LIGHT evidence covers
Delete/Enter parity, one Undo/Redo, source Save after the expected URI/version
clean acknowledgement and disk reopen, active-caret vertical alignment within
0.25 px, all-heading breadcrumbs, OFF-toggle persistence through one edit
and Undo, non-overlap, and retained iframe Window identity.

No new full 105-file suite or Windows native proof is claimed. Independent
list keyboard/number-gap work, saved-viewport work, and engine 1.67 are not
included. This does not claim fixes for normal-text Enter producing item 3,
Tab at an atom, paste below item 3, or numbering 1, 2, 5, nor all reported
user bugs. Publication verifies the exact approved bytes, not a new test run.

## What's new in 0.10.5

- Nested-list guides align to the actual **parent marker's ink-start**, not
  its padding container. The owned-parent padding join removes the real
  20 px gap while preserving genuine reset boundaries and gap-free 1 px guides.
- Passive frame initialization/theme synchronization/forced flush preserve
  clean authored data instead of appending derived canvas/origin/theme/z-order.
- Actual toolbar-button Undo/Redo now signal authorship and persist frame
  changes, alongside keyboard/global history paths.

Supported markers are `decimal`, `decimal-leading-zero`, `disc`, `circle`,
and `square`. Unsupported custom `::marker` content, alpha/Roman/string
markers, image/inside/none styles, and affected task/checkbox styles draw
**no marker guide**. Embedded custom `@font-face` fonts were not separately
validated; failed marker-image decoding caches null and draws no marker line.
Structural/manual/heading guides remain unchanged.

The 0.10.4 ordered-item-2/list-format scope and refusal limits below remain,
as do subtitle/body alignment, closed-by-default outline, table/history,
backups, and embedded diagram engine **1.66.0**.

### 0.10.5 verification scope

Current original guest-hook checks passed **38/38**. Exact-package native
proof passed in **Linux VS Code 1.105.1**, DARK and LIGHT: six-scroll marker
alignment within 1 px, gap 0, no reset bridges, stable frames, passive reopen
version 1 clean with unchanged raw canonical data, one real palette edit,
actual toolbar Undo/Redo, and exact edited Save/Reopen. Disk/data/getText
assertions followed the expected URI's version-4 clean save acknowledgement.
An earlier edited-Save failure was a pre-ACK test race; initialization and
toolbar authorship bugs were real and fixed.

Initial 24 selected-font/scoped checks and 56 original-hook checks, plus
the older join-only/baseline-only 37-check runs, are separate historical
proof—not additional current runs. Final evidence-only hooks ran zero
original source tests and preserved source fingerprints. No new full
105-file suite, current all-browser run, Windows native proof, or actual
minimum-floor VS Code 1.96 native proof is claimed. See the release notes.

## What's new in 0.10.4

- Optional validated `listFormat: "items-v1"` and block ancestry support
  structured list-item content. Runtime 0.10.4 is registered under
  `v1-list-items`; historical version profiles are unchanged.
- A new diagram can be actual content of empty ordered-list item 2, with no
  outside placeholder. Enter after the last atom continues to item 3.
- Nested bullet continuation, clipboard item-graph remapping, sequence-aware
  Markdown item-1 markers, Save/Reopen, and Undo support the new item structure.

Insertion/paste is limited to supported **empty-item/single-atom** cases.
Mid-text, text-bearing, multi-atom paste, before-atom Enter, and unsafe gaps
are visibly refused with **zero edits**. Flat old Markdown list-fragment paste
is refused. Arbitrary inline insertion is not claimed.

Without the DOM `moveBefore` API, new plain-Markdown/new-iframe paths work,
including initial new-diagram insertion into empty ordered item 2. Unsafe
topology changes reparenting an existing live iframe are refused with zero
mutations, preserving draft/state. The VS Code engine floor remains
`^1.96.0`.

The 0.10.3 heading/body, guides, and default-outline fixes remain, as do
table/history behavior, embedded diagram engine **1.66.0**, backup protections,
and official-GitHub upgrade prompts.

### 0.10.4 verification scope

Reported owned isolated-guest checks passed **85/85**, and unchanged
normal-hook checks passed **36/36**. Exact-package Linux native VS Code
API-absence checks passed: this simulated missing `moveBefore`, not actual
VS Code 1.96 or Windows native execution. No new full 105-file Ring 2 suite
or current all-browser run is claimed. Final independent source review
approved the frozen artifact, closing the canonical-before-mutation blocker
and four earlier faults. See the release notes for limitations.

## What's new in 0.10.3

- **R19:** body text aligns with its own heading: H1/body at 0 px,
  H2/body at 32 px, and H3/body at 64 px. Structural indentation starts
  with subtitles; authored and list indentation remain additive.
- **R20:** continuous indentation guides start at the row indentation
  boundary, before markers, without margin gaps; coverage includes
  right-to-left, nested, wrapped, and empty rows.
- **R22:** the outline is closed by default and opens/closes with its
  user button. Toggling the outline changes only the view.

**In 0.10.3, R21**, inserting a diagram inside an empty LI2, was **not included**.
The supported scoped form is introduced in 0.10.4 above, not retroactively
added to 0.10.3. The embedded diagram engine stays at **1.66.0**;
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

## Version compatibility in 0.10.6

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
[Historical 0.10.3](https://github.com/MenachemBarak/mdd/releases/tag/v0.10.3)
retains its original release notes, assets, and validation limitations.
[Historical 0.10.4](https://github.com/MenachemBarak/mdd/releases/tag/v0.10.4)
retains its original release notes, assets, and validation limitations.
[Historical 0.10.5](https://github.com/MenachemBarak/mdd/releases/tag/v0.10.5)
retains its original release notes, assets, and validation limitations.
[Historical 0.10.6](https://github.com/MenachemBarak/mdd/releases/tag/v0.10.6)
retains its original release notes, assets, and validation limitations.

## Distribution scope

This repository contains official release documentation, not imported
development history. The 0.10.10 VSIX is the exact independently reviewed and
approved archive, unchanged from its verification. The official release notes
record its publication and limitations.

Third-party notices remain bundled in the VSIX. This distribution does not
declare a project-wide license.
