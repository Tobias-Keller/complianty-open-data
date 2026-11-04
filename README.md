# GDPR Pre-Consent Tracking on 3.2M German Websites

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23939754.svg)](https://doi.org/10.5281/zenodo.23939754)

Aggregated results from the 2026 [Complianty](https://complianty.de/) study on whether German
websites load tracking services **before** the visitor gives cookie consent.

**Canonical source & full study (German):**
https://complianty.de/studie/dsgvo-verstoesse-deutsche-websites-2026/

Also available on [Zenodo](https://doi.org/10.5281/zenodo.23939754) (citable DOI, version 2; version 1: [10.5281/zenodo.22009986](https://doi.org/10.5281/zenodo.22009986)) and
[Kaggle](https://www.kaggle.com/datasets/tobiaspaulik/gdpr-pre-consent-tracking-on-1-2m-german-websites).

**Version 2.0** · data as of 2026-09-14 to 2026-11-02 · prepared 2026-11-03
Version 1.0 (data as of 2026-06-18, released 2026-08-19) stays available unchanged.

## Key findings (Version 2)

- **3,158,515** .de websites successfully scanned (latest successful scan per domain)
- **44.8 %** show a cookie consent banner (CMP)
- **18.0 %** of all sites load genuine tracking (analytics, advertising, retargeting,
  session recording, A/B testing) before any consent, the *strict* count
- **Core finding: 19.8 % of all sites WITH a consent banner still load genuine
  tracking before the visitor consents**

Version 1 reported 17.9 % and 21.0 % on 1,193,438 sites. Re-classifying that June corpus
with today's catalog gives 18.3 % and 21.3 %, so the catalog explains about 2 % relative.
The corpus is larger and differently composed in Version 2, so the difference is not a trend.

A "finding" here is a **measured technical fact** (a network request to a tracking
service before the consent click), **not a legal assessment** of the individual case.

## Files

| File | Content |
|---|---|
| [`complianty-studie-2026-aggregiert-v2.csv`](complianty-studie-2026-aggregiert-v2.csv) | Version 2: all aggregates as a flat table |
| [`complianty-studie-2026-aggregiert-v2.json`](complianty-studie-2026-aggregiert-v2.json) | Version 2: same aggregates, structured, incl. metadata, license and comparison to v1 |
| [`README-daten-v2.md`](README-daten-v2.md) | Version 2 data dictionary and methodology (German) |
| [`complianty-studie-2026-aggregiert.csv`](complianty-studie-2026-aggregiert.csv) / [`.json`](complianty-studie-2026-aggregiert.json) | Version 1 (June 2026), unchanged |
| [`README-daten.md`](README-daten.md) | Version 1 data dictionary (German) |

CSV columns: `bereich` (topic block) · `kennzahl` (metric / service / CMP name) ·
`seiten` (absolute number of distinct websites) · `anteil_prozent` (percentage;
reference base is the full corpus unless the metric states otherwise).

## Methodology (short)

Automated browser measurement with a fresh browser context (no cookies, no storage):
network capture **before** consent → click "accept all" → delta capture **after**
consent. Only the most recent successful scan per domain is counted. The **strict**
headline count includes only genuine tracking categories; map/video embeds,
monitoring and consent-mode-denied pings are deliberately **excluded** (their legal
status is disputed in individual cases). The *wide* count including those categories
is provided for transparency only.

**Validation (v2):** blind re-adjudication of a sample (n = 250: 200 sites with a confirmed
finding plus 50 consent-mode/transfer cases, scanner verdict hidden) based on raw network
evidence: 63.2 % clear hits, 33.2 % ambiguous, 3.6 % clear false positives (95 % Wilson CI
1.9 to 6.7 %). The sample is not built identically to v1 (59.6 / 27.2 / 13.2 %), so the rates
are only partly comparable. The re-adjudication was performed by a separate language model,
**not** by a human expert panel.

## Limitations

- Server-side tracking is invisible at network level → all rates are **conservative lower bounds**.
- Results are not extrapolated to "all German websites" — only successfully scanned sites are counted.
- Only aggregates are published, never individual websites.
- Cookies/storage before consent rose from 9.1 % to 14.0 %. This is already present in the raw
  data of the newer scans; whether it is a trend or a changed scanner measurement is not
  established. Please do not cite it as a trend.
- CMP market shares are a **market overview only, not a compliance rate per product**:
  whether tracking fires before consent depends on how tags are integrated on the
  individual site, not on the banner product.
- Whether a service loads before or after consent depends solely on its integration —
  several listed services (e.g. Google Analytics, Matomo) can demonstrably be
  operated consent-gated.

## Disclosure

Collected by Complianty, a provider of GDPR scanning software for websites — the
commercial interest in the topic is hereby disclosed.

## License & citation

**[CC BY 4.0](LICENSE)** — free to use, share and adapt (including commercially) with attribution:

> Complianty (2026): Tracking before consent on German websites. Data analysis of
> 3,158,515 successfully scanned .de websites, version 2, as of November 2026.
> https://complianty.de/studie/dsgvo-verstoesse-deutsche-websites-2026/
> DOI: [10.5281/zenodo.23939754](https://doi.org/10.5281/zenodo.23939754)

## Changelog

- **2.0 (2026-11-03):** Re-analysis on 3,158,515 sites (data as of 2026-09-14 to 2026-11-02),
  current fingerprint catalog, new validation sample, counter-check against v1.
- **1.0 (2026-08-19):** First release as open data under CC BY 4.0 (study data as of 2026-06-18).
