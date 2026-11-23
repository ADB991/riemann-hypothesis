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

## for Andrea

- 2026-11-23: PR120-BUGS.md looked stale this run (all unclaimed rows already had fix commits on the branch). Nothing needed from you unless it stays that way; later runs will retry when the list refreshes.
