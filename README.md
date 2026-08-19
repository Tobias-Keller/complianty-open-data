# GDPR Pre-Consent Tracking on 1.2M German Websites

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.22009986.svg)](https://doi.org/10.5281/zenodo.22009986)

Aggregated results from the 2026 [Complianty](https://complianty.de/) study on whether German
websites load tracking services **before** the visitor gives cookie consent.

**Canonical source & full study (German):**
https://complianty.de/studie/dsgvo-verstoesse-deutsche-websites-2026/

Also available on [Zenodo](https://doi.org/10.5281/zenodo.22009986) (citable DOI) and
[Kaggle](https://www.kaggle.com/datasets/tobiaspaulik/gdpr-pre-consent-tracking-on-1-2m-german-websites).

Version 1.0 · data as of 2026-06-18 · released 2026-08-19

## Key findings

- **1,193,438** .de websites successfully scanned (as of June 2026, ~62.6 % technical success rate)
- **46.5 %** show a cookie consent banner (CMP)
- **17.9 %** of all sites load genuine tracking (analytics, advertising, retargeting,
  session recording, A/B testing) before any consent — the *strict* count
- **Core finding: 21.0 % of all sites WITH a consent banner still load genuine
  tracking before the visitor consents**

A "finding" here is a **measured technical fact** (a network request to a tracking
service before the consent click), **not a legal assessment** of the individual case.

## Files

| File | Content |
|---|---|
| [`complianty-studie-2026-aggregiert.csv`](complianty-studie-2026-aggregiert.csv) | All aggregates as a flat table |
| [`complianty-studie-2026-aggregiert.json`](complianty-studie-2026-aggregiert.json) | Same aggregates, structured, incl. metadata & license |
| [`README-daten.md`](README-daten.md) | Data dictionary and methodology (German) |

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

**Validation:** blind re-adjudication of a stratified sample (n = 250, scanner
verdict hidden) based on raw network evidence: 59.6 % clear hits, 27.2 % ambiguous,
13.2 % clear false positives (95 % Wilson CI 9.6–18.0 %). The re-adjudication was
performed by a separate language model, **not** by a human expert panel.

## Limitations

- Server-side tracking is invisible at network level → all rates are **conservative lower bounds**.
- Results are not extrapolated to "all German websites" — only successfully scanned sites are counted.
- Only aggregates are published, never individual websites.
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
> 1,193,438 successfully scanned .de websites, as of June 2026.
> https://complianty.de/studie/dsgvo-verstoesse-deutsche-websites-2026/
> DOI: [10.5281/zenodo.22009986](https://doi.org/10.5281/zenodo.22009986)

## Changelog

- **1.0 (2026-08-19):** First release as open data under CC BY 4.0 (study data as of 2026-06-18).
