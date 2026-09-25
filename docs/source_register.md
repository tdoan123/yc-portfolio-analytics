# Source Register

One row per data source considered, whether used or rejected. Updated as sources are evaluated (YC-7, YC-8).

| ID | Source | Type | Coverage | Access | Terms / licence | Freshness | Fit | Verdict |
|----|--------|------|----------|--------|-----------------|-----------|-----|---------|
| SRC-01 | [yc-oss/api](https://github.com/yc-oss/api) | Unofficial mirror of YC directory (built from YC website's Algolia search index) | Publicly launched companies only; ~6,200 companies, 50 batches (S05–W27) as of Sep 2026. No founder data beyond diversity flags. Location = current HQ | Public JSON endpoints | No licence stated in repo; relationship to YC's terms unclear — treat as risk | Updated daily via GitHub Actions | Q1 | Pending YC-7 validation |
| SRC-02 | [ycombinator.com/companies](https://www.ycombinator.com/companies) | Official YC directory | Company pages list founders with short bios; education mentioned inconsistently | Website only; no public API | [Terms of Use](https://www.ycombinator.com/legal) prohibit scraping, data mining, and proxy circumvention | Live | Q2 (manual viewing only) | No automated collection. Manual spike only (YC-10); permission requested (YC-9) |

## Notes

- **Investment proxy:** YC gives every company in a batch the same standard deal, so company counts are a reasonable proxy for number of investments. They do not measure dollar amounts or follow-on funding.
- **Location caveat:** location fields reflect where a company is based now, not where founders came from.
