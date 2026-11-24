# PR #120 fix runs (ADB991)

Cloud runs fix root build failures of rohanarun/riemann-hypothesis branch
`opt/collapse-and-consolidate-4.36` (PR #120 to leanprover-community/riemann-hypothesis),
following rohanarun/alpoge-rh-replay `auto-research.md`, `PR120-BUGS.md`, `PR120-PLAYBOOK.md`.

## setup notes

(2026-11-23) Environment v3r1t4s: 4 vCPU, 15 GB RAM, ~60 GB disk. elan's own toolchain download
fails: install Lean from the GitHub release zip (`unzip`) and `elan toolchain link`; `zstd` is not
installed. GitHub GraphQL is refused in the sandbox: use `gh api` REST.

## open

## runs

- 2026-11-23 23:10 UTC (session_01JXYTkXmKT8E5bU3q9fmR3Q): no PR opened. PR120-BUGS.md (head `943a6629e0`, not a commit on the branch; updated 22:37 UTC) listed 25 unclaimed rows whose files no open PR touches, but every one already has a fix commit on `opt/collapse-and-consolidate-4.36` (branch head `cb8f7260b0`, 22:19 UTC), e.g. Bundle0086 rdU (982eef449b), Bundle0276 klat_finite (0cb3ebdb3d), RawChartTangent… mm_zero (ff85c1bee3), LetterSquared… relab (47202afbe0), Bundle0023 (d4a0144fe9). The list lags those fixes; without a build no residual error could be identified, so no speculative PR. Not built: no project olean cache matches the consolidated tree (baseline in scripts/cache-baselines.json is pre-bundling), dependency build far over 90 min on 4 cores.
- 2026-11-24 02:20 UTC (session_01JXYTkYcH1o2M6fph2zxToz): no PR opened. PR120-BUGS.md (updated 01:58 UTC, head `8bc1b10452`, no longer in branch history after server-side merges; branch head now `a8da07f28`) lists 47 open rows. Every row's file already has a fix commit on the branch after bundling (most 13:00–20:00 EST Nov 23, i.e. before the list refresh), except `FlagMeasures/Bundle0343`, which is claimed by draft #664 (@FarzanAhmedHossain); `InertiaEigenvalues/Bundle0561` has #669. Whether those fixes work can only be seen by a rebuild; the smallest row closure (HostLocVan) is ~1,300 project modules, far over 90 min on 4 cores, so not built. No speculative PR.

## for Andrea

- 2026-11-23: PR120-BUGS.md looked stale this run (all unclaimed rows already had fix commits on the branch). Nothing needed from you unless it stays that way; later runs will retry when the list refreshes.
- 2026-11-24: second run in a row with nothing to take: the bug list's rows all already have fix commits on the branch, and this box cannot build a module's dependencies in time (no project olean cache for the consolidated tree). Unless the coordinator's build catches up, or a cache for the branch appears, these runs will keep coming up empty; consider pausing the schedule or lowering its frequency.
