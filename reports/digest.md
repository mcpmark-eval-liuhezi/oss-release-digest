# OSS Release Digest

Quarterly upstream report on the three OSS projects our team builds on. All figures below were pulled fresh from the GitHub API on 2026-10-22.

**Report header (requester account, verified against the live account rather than taken on faith):** GitHub login `HeziLiu`, numeric user id `28861483`, display name "Hezi Liu", profile https://github.com/HeziLiu

## microsoft/vscode

### 1. Current latest release
- Tag: `1.142.0` (release name "1.142.0")
- Published: 2026-10-14T19:46:12Z (Oct 14, 2026)
- Link: https://github.com/microsoft/vscode/releases/tag/1.142.0

### 2. Our tracked upgrade baseline
- Baseline: `1.85.0` (release name "November 2023")
- Baseline published: 2023-12-07T19:05:49Z (Dec 7, 2023)
- How far behind: ~2 years 10 months (1,042 days) and 57 minor versions (1.85.0 -> 1.142.0)

### 3. CI cost - primary build/test workflow
- Workflow picked: **"Code OSS"** (`.github/workflows/pr.yml`, workflow id 4196599) - the repo's main PR build/test workflow (Compile & Hygiene plus Linux/macOS/Windows unit-test shards), by far the most active (2,500+ completed runs, the API's count cap). Other CI workflows were rejected: `pr-linux-test.yml` / `pr-darwin-test.yml` / `pr-win32-test.yml` (created Jul 2025, zero recorded runs), `pr-node-modules.yml` (dependency caching only), CodeQL (security scanning), Monaco Editor checks (Monaco package only).
- Run used: **run id 39760649823** - run #74214, event `pull_request`, conclusion `cancelled`, finished 2026-10-22T10:13:35Z. This is the most recent completed run of this workflow for which GitHub reports usage figures.
- Usage reported by GitHub for that run: `run_duration_ms` = 396,000 (**6 min 36 s**); billable time = **0 ms on every platform** - macOS 0 ms (1 job), Ubuntu 0 ms (21 jobs), Windows 0 ms (2 jobs), 24 job runs in the usage record (the run lists 45 jobs overall, including skipped ones). Billable time is zero because the jobs ran on Microsoft's self-hosted 1ES runner pool (e.g. label `1ES.Pool=1es-vscode-oss-ubuntu-22.04-x64`), which GitHub does not bill.
- Stated explicitly: the two most recent completed runs of this workflow (run ids 39766025488 / #74230 and 39761086886 / #74217, both 2026-10-22) concluded `action_required`, dispatched no jobs, and recorded no usage data at all - no CI-cost figures exist for them.

### 4. Release health - publisher of the latest release
- Publisher (login on the release record): **kycutler** (user id 67761731; the release record also flags the account as `site_admin`)
- Public profile: https://github.com/kycutler - display name "Kyle Cutler" (per commit-author records in microsoft/vscode), **12 followers**, 2 public repos (`kycutler/aznb-samples`, `kycutler/multiple-monaco-bug`)
- Recent activity: authored microsoft/vscode commit `f8fac976` on 2026-10-21 ("Browser: Support workspace storage scope plus affinity key (#343317)")

## facebook/react

Note: `facebook/react` now canonicalizes to `react/react` (the repository moved to the `react` organization); the release records below are served from `react/react`.

### 1. Current latest release
- Tag: `v19.3.1` (release name "19.3.1 (October 14th, 2026)")
- Published: 2026-10-14T17:06:15Z (Oct 14, 2026)
- Link: https://github.com/facebook/react/releases/tag/v19.3.1

### 2. Our tracked upgrade baseline
- Baseline: `v18.2.0` (release name "18.2.0 (June 14, 2022)")
- Baseline published: 2022-06-14T19:54:21Z (Jun 14, 2022)
- How far behind: ~4 years 4 months (1,583 days) and one full major version (18.2.0 -> 19.3.1)

### 3. CI cost - primary build/test workflow
- Workflow picked: **"(Runtime) Build and Test"** (`.github/workflows/runtime_build_and_test.yml`, workflow id 106946368) - the main runtime build/test workflow (node_modules caching, shard-weight resolution, 200+ test-shard jobs; 2,500+ completed runs, the API's count cap). Other CI workflows were rejected: (Compiler) TypeScript / React Compiler (Rust) / (Compiler) Playground (React Compiler, not the runtime), (DevTools) Regression Tests, (Runtime) Fuzz tests, and lint/stale automation.
- Run used: **run id 39760603178** - run #14410, event `pull_request`, conclusion `success`, finished 2026-10-22T10:10:53Z. This is the most recent completed run of this workflow.
- Usage reported by GitHub for that run: billable **Ubuntu** time = **0 ms across 229 jobs**. The usage payload's `run_duration_ms` field was truncated out of the API response, so as the duration number: the run record's own window is 2026-10-22T10:06:37Z -> 10:10:53Z (**~4 min 16 s** wall clock).

### 4. Release health - publisher of the latest release
- Publisher (login on the release record): **eps1lon** (user id 12292047)
- Public profile: https://github.com/eps1lon - display name "Sebastian 'Sebbie' Silbermann" (per commit-author records; commit email is @vercel.com), profile README reads "I maintain stuff", personal site solverfox.dev, **1,846 followers**, 154 public repos (incl. `eps1lon/types-react-codemod`, `eps1lon/dom-accessibility-api`)
- Recent activity: authored react/react commit `ab0d927f` on 2026-10-20 ("Ensure unique `useId` values in large trees (#37916)")

## electron/electron

### 1. Current latest release
- Tag: `v45.0.0` (release name "electron v45.0.0", target branch `45-x-y`)
- Published: **2026-10-21 (UTC)**. Stated explicitly: this release's API payload is truncated by its very large release-notes body, so the exact `published_at` timestamp and the `author` object could not be read from the release record itself. The date is pinned by two authoritative signals: (a) the `release: published` event that fired the "Update Website Docs" workflow **run id 39549204111** at 2026-10-21T05:22:42Z - that workflow triggers only on release publication and its display title is "electron v45.0.0" on tag `v45.0.0`; and (b) the git tag `v45.0.0`, created 2026-10-21T03:25:49Z.
- Link: https://github.com/electron/electron/releases/tag/v45.0.0

### 2. Our tracked upgrade baseline
- Baseline: `v28.0.0` (release name "electron v28.0.0", target branch `28-x-y`)
- Baseline published: the exact `published_at` could not be read from the release record (same payload truncation). The closest authoritative timestamp is the git tag `v28.0.0`, created **2023-12-04T18:26:53Z** by "Sudowoodo Release Bot" - i.e. December 2023.
- How far behind: ~2 years 10.5 months (~1,052 days from the 2023-12-04 baseline tag to the 2026-10-21 latest release) and **17 major versions** (28 -> 45)

### 3. CI cost - primary build/test workflow
- Workflow picked: **"Build"** (`.github/workflows/build.yml`, workflow id 102567601) - the repo's main build/test workflow with 16,688 recorded runs. Other CI workflows were rejected: "C/C++ CI" (`c-cpp.yml`) has only 2 runs ever, both from one throwaway fork PR ("Create c-cpp.yml" by `zskbot` against a Velclaw/electron fork; last run 2026-10-05, failed) - a stray workflow, not the project's CI; the "Electron Build & Test Pipeline" variants have 2-4 runs and have been stale since 2026-08-26; "Publish MacOS/Linux/Windows" are release-publishing workflows, not CI.
- Run used: **run id 39726072825** - run #30907, event `pull_request` ("build: update build-images to 22fded7"), conclusion `success`, finished 2026-10-22T05:54:17Z. This is the most recent completed run of this workflow.
- Usage reported by GitHub for that run: `run_duration_ms` = 2,901,000 (**48 min 21 s**); billable time = **0 ms on every platform** - macOS 0 ms (13 jobs), Ubuntu 0 ms (9 jobs), Windows 0 ms (6 jobs), 28 jobs in total (builds run in the project's own container/build images, which GitHub reports as 0 billable ms).

### 4. Release health - publisher of the latest release
- Publisher: could not be read from the release record (payload truncated - see item 1). The associated git tag `v45.0.0` was created by **`sudowoodo-release-bot[bot]`** (GitHub App bot account, id 88427002), the same bot identity that tagged our `v28.0.0` baseline ("Sudowoodo Release Bot").
- Profile lookup: **no public user profile exists for this publisher and none could be found** - a GitHub user search for `sudowoodo-release-bot` returns no user account, because it is a bot (GitHub App) account rather than a human user. Stated explicitly: no publisher profile could be found or verified for this release, and no human maintainer has been substituted in its place.

Report credited to HeziLiu (GitHub login: HeziLiu, numeric user id: 28861483).
