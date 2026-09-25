# Decision Log

Newest first. Each entry: date, decision, reason, alternatives considered, affected tickets.

---

## 2026-09-25 — No automated collection of founder data from ycombinator.com

**Decision:** Founder background data will not be scraped from YC's website. Q2 feasibility will be tested with a manual 30-founder spike, and permission will be requested from YC.

**Reason:** YC's Terms of Use prohibit "data mining, robots, scraping or similar data gathering or extraction methods" and circumventing blocks via proxies. Founder bios are also personal information, which raises privacy considerations.

**Alternatives considered:** Proxy-based crawl (rejected: breaches terms); LinkedIn (rejected: terms); Crunchbase/PitchBook (to evaluate in YC-8).

**Tickets:** YC-8, YC-9, YC-10

---

## 2026-09-25 — Progressive elaboration instead of an upfront blueprint

**Decision:** Documentation (schema, data dictionary, hypotheses, dashboard spec) is written sprint by sprint as evidence arrives, not fully specified before data is profiled.

**Reason:** An earlier draft blueprint specified schema, hypotheses, and visuals before the data had been downloaded. Several of those choices depend on what profiling reveals.

**Alternatives considered:** Full upfront specification (rejected for v1; its quality rules and metric-definition habits are kept as a reference to pull from when needed).

**Tickets:** YC-1 (epic)
