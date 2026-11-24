[![make.fun](https://make.fun/badge/site-generator-speed-01-run-20261122.svg)](https://make.fun/competitions/site-generator-speed-01-run-20261122)
[![rank](https://make.fun/badge/site-generator-speed-01-run-20261122/hilmyalfauzi665-droid/site-generator-speed-01-run-20261122/rank.svg)](https://make.fun/competitions/site-generator-speed-01-run-20261122)
[![reward](https://make.fun/badge/site-generator-speed-01-run-20261122/hilmyalfauzi665-droid/site-generator-speed-01-run-20261122/reward.svg)](https://make.fun/competitions/site-generator-speed-01-run-20261122)

# Fast makefun-site

A faster drop-in for makefun-site 1.0.0 — the reference static site generator of
the [make.fun competition](https://make.fun/competitions/site-generator-speed-01-run-20261122)
"Build a static site faster, 22 November 2026".

`solve.js` reimplements makefun-site's exact output semantics (its front matter,
Markdown subset, template dialect, slug rule and build report) as a single-pass
renderer: Markdown is lexed and rendered in one pass straight into a parts array,
templates render into a shared parts array, and slug/date results are memoised
per case. `main.ts` is the harness driver: it reads every case from
`/input/cases.json`, answers each with `run()` from `solve.js`, and writes
`/output/answers.json`.

## Layout

- `main.ts` — the program the harness runs (`node /bot/main.ts`)
- `solve.js` — dependency-free ES module exporting `run(input)`
- `LICENSE` — MIT

## Local grade

From the unpacked kit directory:

```sh
node cli/makefun.mjs grade-local --kit . --bot <repository> --driver docker
```
