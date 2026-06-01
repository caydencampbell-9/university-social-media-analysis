# University Social Media & Admissions Analysis

**Research project · Pepperdine Graziadio MSBA · 2026**

Engineered a 3-API data pipeline to scrape social media metrics for 51 universities, merged with federal IPEDS 2024 admissions data, and ran Pearson correlation analysis to quantify the relationship between social media performance and admissions outcomes. Findings were presented directly to Pepperdine Graziadio administration.

---

## Key Findings

| Metric | Correlation | Significance |
|--------|------------|--------------|
| IG Followers → Yield Rate | r = +0.530 | p < 0.01 |
| TikTok Avg Likes → Applications | r = +0.500 | p < 0.01 |
| Pepperdine IG Engagement Percentile | 87th | — |
| Pepperdine Yield Rate Percentile | 13th | Actionable gap |
| Pepperdine YouTube Posting Frequency | 91st worst | Every 268 days avg |

**Bottom line:** Social media engagement is measurably connected to admissions outcomes. These are business metrics, not vanity metrics.

---

## Data Pipeline

```
RapidAPI (Instagram120 + TikTok-scraper7)
         +
Google YouTube Data API v3
         +
IPEDS 2024 Federal Admissions Data
         ↓
UNITID federal school ID used as join key
         ↓
Merged dataset: 51 universities, 4 sources
         ↓
Pearson correlation analysis across 38 universities
```

---

## Methodology

- **Data collection:** RapidAPI scrapers for Instagram and TikTok metrics; YouTube Data API v3 for posting frequency and engagement; IPEDS 2024 for applications, acceptance rate, yield rate, and enrollment
- **Join key:** UNITID federal school ID — clean merge across all 4 sources with no manual matching
- **Analysis:** Pearson correlation coefficients computed across all social media metrics vs. admissions outcomes; statistical significance tested at p < 0.01
- **Sample:** 38 universities after cleaning (51 scraped, some excluded for missing data)

---

## Outputs

- Full correlation heatmap — all social media metrics vs. all admissions outcomes
- School positioning map — yield rate vs. total applications, sized by IG followers
- Pepperdine percentile rankings across all social media metrics
- 6 data-driven strategic recommendations delivered to university board

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| Python | Data pipeline, analysis, visualization |
| Pandas | Data cleaning, merging, transformation |
| RapidAPI | Instagram and TikTok scraping |
| YouTube Data API v3 | YouTube channel metrics |
| IPEDS 2024 | Federal admissions data |
| Matplotlib / Seaborn | Correlation heatmap, positioning map |
| Pearson r | Statistical correlation analysis |

---

## Repository Structure

```
├── analysis.py          # Full pipeline: scrape → merge → analyze → visualize
├── data/
│   ├── raw/             # Raw API outputs
│   └── processed/       # Cleaned merged dataset
├── outputs/
│   ├── correlation_heatmap.png
│   ├── school_positioning_map.png
│   └── pepperdine_percentile_rankings.png
└── README.md
```

---

*Pepperdine Graziadio MSBA · Data-Driven Decision Analysis · 2026*
