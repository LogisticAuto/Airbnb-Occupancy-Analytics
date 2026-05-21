# Airbnb — Occupancy Analytics & Host Success Analysis

A 24-hour take-home analytics assignment completed for an **Advanced Analytics** role at **Airbnb**. The objective was to investigate an unexpected increase in occupancy trends, identify the root cause, and deliver executive-ready findings and recommendations in 5 slides.

---

## The Business Problem

The Advanced Analytics team — focused on host success — observed an increase in occupancy trends with no clear explanation. No major product changes had been made. The assignment was to independently diagnose the cause and provide data-driven recommendations.

**Occupancy is defined as:** `# of Booked Nights / (# of Available Nights + # of Booked Nights)`

Each row in the dataset represents monthly metrics for a host, with hosts potentially having multiple listings.

---

## Key Findings

### Finding 1 — The Overall Dataset Is Misleading
At the macro level, the dataset shows an upward trend in both bookings and availabilities. However, **occupancy rate tells a different story** — a fairly steady decline from January 2017 through July 2018, followed by a sharp and significant surge from July to August 2018. The overall upward trend masks the underlying occupancy deterioration.

### Finding 2 — The Southland Region Is the Primary Driver
The July–August 2018 occupancy surge is almost entirely explained by activity in the **Southland region**, which experienced a **28.8% surge** in that window. The root cause is a disproportionate relationship between a sharp **49.6% drop in Availabilities** against only a **9.8% drop in Booked Nights** — when supply contracts faster than demand, occupancy rate spikes mathematically even without demand growth.

**Entire Home/Apt listings within Southland account for ~66% of the declining availability impact.**

### Finding 3 — Six Hypothesized Impact Factors
Six external factors were identified as likely contributors to hosts relinquishing availabilities in the Southland region:

| Factor | Hypothesis |
|---|---|
| Seasonal Events / Festivals | Festival cancellation or relocation removes the demand signal that justified short-term listings |
| Economic Factors | Employment growth drives hosts toward long-term leases for perceived income stability |
| Natural Disaster or Climate Event | Adverse conditions prompt hosts to proactively delist to limit liability |
| Political Instability | Policy uncertainty causes traveler redirection away from the region |
| Competitor Sniping | Rivals capitalize on peak season gaps with targeted promotions |
| Regulatory Changes | Zoning, tax, or licensing changes reduce short-term rental viability |

---

## Recommendations — Game Plan

**Investigation & Identification**
Conduct further exploratory analysis against the six impact factors to properly diagnose the Southland spike. Cross-reference external event data (festival calendars, weather records, regulatory changes) against the July–August 2018 window to isolate the most likely cause.

**Host Dialogue**
Open structured communication with Southland hosts to understand what drove listing removals. Extend dialogue to the **Essos region** (which displayed a more consistent occupancy rate) as a comparative control group to identify what those hosts did differently.

**Listing Mix Suggestion**
Within the Southland region, **Private Room listings outperformed Entire Home/Apt listings** on occupancy rate. Recommending or incentivizing a shift toward Private Room listings could stabilize occupancy and reduce the platform's exposure to bulk availability drops from Entire Home hosts.

---

## Repository Structure

```
Airbnb-Occupancy-Analytics/
├── README.md
├── data/
│   └── eda_dataset_aa.csv              # Monthly host-level dataset (see data note)
├── database/
│   ├── AirBnb.db                       # SQLite database
│   ├── AirBnb_rec.sqbpro               # SQL query file — exploratory queries
│   └── AirBnb_v2.sqbpro                # SQL query file — refined analysis
├── dashboard/
│   └── Tableau_Display.twb             # Tableau workbook — occupancy and regional analysis
├── presentation/
│   └── Slides.pdf                      # 5-slide executive presentation
└── docs/
    └── airbnb_case_prompt.md           # Original assignment prompt (reference only)
```

---

## Tools Used

| Tool | Purpose |
|---|---|
| SQL / SQLite | Data querying and exploratory analysis via DB Browser (`.sqbpro`) |
| Tableau | Occupancy trend visualization, regional breakdowns, room type analysis |
| PowerPoint / PDF | Executive presentation — 5 slides for leadership with limited context |

---

## Analytical Approach

1. **Macro trend analysis** — charted bookings and availabilities over the full Jan 2017–Aug 2018 window to establish baseline context
2. **Occupancy rate isolation** — separated occupancy rate as a derived metric to surface the divergence from raw booking volume
3. **Regional drill-down** — decomposed occupancy by region to identify Southland as the primary driver of the Aug 2018 surge
4. **Room type segmentation** — broke out Entire Home/Apt vs. Private Room within Southland to quantify the listing mix impact
5. **Hypothesis framework** — developed six structured external factor hypotheses to guide further investigation

---

## Future Enhancements

- Layer in external data (local event calendars, weather records, regulatory change logs) to validate or eliminate each of the six impact factor hypotheses
- Build a host churn model to predict which hosts are at risk of relinquishing availabilities before it impacts occupancy
- Develop a regional early-warning dashboard that flags occupancy divergence from availability trends in real time

---

## Data Note

The dataset used in this analysis was provided as part of the Airbnb take-home assignment. Per the original assignment instructions, this data is **not intended for public distribution**. If this repository is public, the `data/` and `database/` folders should be reviewed accordingly. No personally identifiable host information is included.

---

## Author

**Christopher Brown**
Sr. BI Analyst | Data & Analytics Leader
[LinkedIn](https://www.linkedin.com/in/chris-brown-0331/)
