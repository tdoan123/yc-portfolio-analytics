# Source Register

One row per data source considered, whether used or rejected. Updated as sources are evaluated (YC-7, YC-8).

| ID | Source | Type | Coverage | Access | Terms / licence | Freshness | Fit | Verdict |
|----|--------|------|----------|--------|-----------------|-----------|-----|---------|
| SRC-01 | [yc-oss/api](https://github.com/yc-oss/api) | Unofficial mirror of YC directory (built from YC website's Algolia search index) | Publicly launched companies only; 6,248 companies, batches Summer 2005 – Summer 2027 (snapshot 2026-09-25). No founder data beyond diversity flags; no funding or performance data. Location = current HQ | Public JSON endpoints | No licence stated in repo; relationship to YC's terms unclear — treat as risk | Updated daily via GitHub Actions; YC adds companies gradually, so the in-progress batch is incomplete | Q1 | **Go, with caveats** (YC-7, 2026-09-25). See validation summary below |
| SRC-02 | [ycombinator.com/companies](https://www.ycombinator.com/companies) | Official YC directory | Company pages list founders with short bios; education mentioned inconsistently. Pages display `tags`, not the industry/subindustry hierarchy | Website only; no public API | [Terms of Use](https://www.ycombinator.com/legal) prohibit scraping, data mining, and proxy circumvention | Live | Q2 (manual viewing only); reference for manual spot checks of SRC-01 | No automated collection. Used for a 22-company manual spot check (YC-7). Founder spike manual only (YC-10); permission to be requested (YC-9) |
| SRC-03 | [Frontrun: YC F26 company list](https://www.frontrun.vc/blog/yc-f26-companies-full-list/) | Third-party blog | Fall 2026 batch listing counts (23 listed on 2026-08-27) | Public web page | Standard website terms; cited, not collected | Point in time | Evidence that directory listings grow during a batch | Secondary reference only. To be confirmed with own snapshots |

## SRC-01 validation summary (YC-7)

Full evidence: `notebooks/00_source_profile_v2.ipynb` (Findings 1–5, charts C1–C6) and `docs/spot_check.csv`.

**Verdict: go, with caveats.** Q1 (is a founder's solution space getting crowded in recent YC batches?) can be answered with SRC-01 under the rules below.

**Reliability**
- Faithful mirror: 22 of 22 spot-checked companies matched YC's own directory on name, batch, status and industry. This confirms copying accuracy, not that YC's labels are current.
- Identity clean: no missing or duplicate company IDs.
- Missing values: tags 13.9%, long_description 6.7%, one_liner 2.6%, all_locations 2.5%, team_size 1.8%; industry and batch complete (18 companies "Unspecified" industry, 1 "Unspecified" batch).

**Rules for use (caveats)**
1. Define a founder's space by `subindustry` (application) + keyword in `one_liner` (solution). Tags are unreliable for recent companies (about 74% of 2026-H1 untagged) and mix application and technology labels.
2. Show trends by half-year period (Winter + Spring = H1, Summer + Fall = H2), complete periods only. YC moved to four batches a year in 2024–25, so per-batch counts show a false decline. Exclude the in-progress batch (currently Fall 2026, so 2026-H2 onward), future-dated batches (Winter 2027, Summer 2027: 1 company each, confirmed on YC's site), and "Unspecified."
3. "Crowded" means crowded within YC's public directory, not the whole market: launched companies only, labels as of the snapshot date, no funding or performance data.

**Minor limitations**
- 1,166 companies (18.7%) have only a parent subindustry (e.g. just "B2B"); about 30% from 2024 onward.
- `industry` alone is too coarse: B2B is 51% of all companies.
- `stage` has only two values (Early, Growth): weak maturity signal.
- Periods before about 2011 have fewer than 50 companies; shares there are noisy.

## Notes

- **Investment proxy:** YC gives every company in a batch the same standard deal, so company counts are a reasonable proxy for number of investments. They do not measure dollar amounts or follow-on funding.
- **Location caveat:** location fields reflect where a company is based now, not where founders came from.
- **Snapshots:** each download is saved under `data/raw/<date>/` with a checksum manifest (not committed). Re-downloading periodically lets listing growth and label changes be measured over time.
