# Indian Banking Credit Dashboard

A complete data analysis project tracking the health and structure of India's scheduled commercial banking system — credit deployment, priority sector lending, deposit composition (CASA), asset quality (NPAs), digital payment adoption, financial inclusion, state-wise credit-deposit ratios, and macroeconomic context — built entirely from public RBI data.

---

## What this is

This project consolidates **18 separate RBI datasets** (RBI Bulletin "Current Statistics" + RBI DBIE + Handbook of Statistics) into a single, cleaned, analysis-ready data layer and an interactive Tableau dashboard across **5 dashboard tabs**, **18 worksheets**, and **20 verified charts**.

| Pillar | Source | Coverage |
|---|---|---|
| Sectoral & Industry Credit | RBI Bulletin Tables 15–16 | Apr 2025 – Apr 2026 |
| Priority Sector Lending | RBI Bulletin Table 15 (memo items) | Apr 2025 – Apr 2026 |
| CASA Ratio | DBIE Select Aggregates (fortnightly) | Jan 2024 – Apr 2026 |
| NPA — Bank Group | DBIE Gross & Net NPA Bank Group-wise | FY1996–97 to FY2023–24 |
| NPA — Individual Banks | DBIE Bank-wise Gross NPA Ratios | FY2025 snapshot |
| Agriculture Credit | DBIE Institutional Credit for Agriculture | FY1971–72 to FY2024–25 |
| SHG-Bank Linkage | DBIE Self-Help Group Programme | FY1992–93 to FY2024–25 |
| Deposit Ownership | DBIE Ownership of Deposits (SCBs) | FY2019 to FY2026 |
| Digital Payments | DBIE Payment System Indicators | FY2015–16 to FY2024–25 |
| Bank Group Business | DBIE Bank Group-wise Business | Mar 2005 – Mar 2025 |
| State-wise CD Ratio | DBIE Quarterly Spatial Distribution 3A | FY2022–23 to FY2025–26 (Q4) |
| GDP Growth | Handbook of Statistics — Macro Aggregates | FY1950–51 to FY2025–26 |
| CPI Inflation | Handbook of Statistics — Output & Prices | FY2012–13 to FY2025–26 |
| Repo Rate | Handbook of Statistics — Money & Banking | FY2001–02 to FY2025–26 |
| Unified Cross-Pillar | Derived — merged on FY key | FY2015–16 to FY2024–25 |
| NPA Forecast | Derived — linear trend + structural floor | FY2024–25 to FY2026–27 |
| CASA Forecast | Derived — linear trend projection | May 2026 – Apr 2027 |
| SCB Aggregates | RBI Bulletin Table 14 | Snapshot Apr 2026 |

---

## Why this project matters — the economic logic

Banking system health is one of the clearest leading indicators of real-economy direction in a credit-driven economy like India's. Each metric maps to a distinct transmission channel:

**Credit deployment** shows where the economy is actually expanding. A shift toward Services and Personal Loans over Industry signals a consumption-led growth phase rather than a private capex cycle — relevant for anyone reading where investment stands.

**Priority Sector Lending** exists because credit markets under-serve agriculture, small enterprises, and affordable housing on their own. RBI mandates a minimum 40% ANBC allocation specifically to correct this market failure. Tracking it shows whether policy intent is translating into actual disbursement.

**CASA ratio** directly determines a bank's cost of funds and lending margins. System-wide CASA trends also reflect household liquidity preference — parking money for transactions vs. locking into fixed deposits for yield.

**NPAs** are the most direct asset-quality signal. A rising NPA ratio means capital is being destroyed and banks will pull back on new lending (credit crunch risk). The post-2018 recovery from 11.2% to 2.75% GNPA marks the most significant balance sheet healing in Indian banking in two decades.

**Digital payments** (UPI in particular) is a structural shift with second-order credit effects: better transaction data trails enable underwriting of previously thin-file borrowers, making credit inclusion economically viable.

**State-wise CD ratio** reveals geographic capital flows invisible in national aggregates. States like Andhra Pradesh (155%) are net credit-deployers funded via inter-bank; states like Uttarakhand (43%) are net savers whose deposits fund credit elsewhere.

**Macro overlay** makes everything else interpretable. The NPA crisis is incomprehensible without seeing that it coincided with elevated real rates and decelerating GDP. The COVID-era NPA dip requires GDP collapse context to understand as a recognition artifact, not genuine improvement.

---

## Key findings

Six findings emerged from the cleaned data that were not visible in any single RBI publication:

**1. India's NPA crisis has fully reversed — near a two-decade low.**
System GNPA peaked at 11.2% in FY2017–18 (post-AQR) and fell to 2.75% by FY2023–24. Better than every year between 2011 and 2021. Public Sector Banks remain higher (3.5%) than Private (1.8%) and Foreign (1.2%), but the gap has narrowed sharply.

**2. Services and Personal Loans have displaced Industry as the engine of credit growth.**
Services: +18.6% YoY. Personal Loans: +16.0%. Industry: +15.1%. Agriculture: +13.7%. For the first time since bank nationalisation, retail/services credit is the primary system growth driver — with implications for NPA risk and the traditional corporate lending model.

**3. UPI grew ~10,000x in transaction volume since launch — and is still accelerating.**
From ~1.8 crore transactions (FY2016–17) to ~18,587 crore (FY2024–25). Value: Rs.6,961 crore to Rs.26 lakh crore. RTGS still dominates by value (Rs.2,013 lakh crore) for large corporate settlements, but UPI is now the dominant retail rail, displacing both NEFT and IMPS.

**4. Six states have CD ratios above 90% — a geographic credit concentration worth watching.**
Andhra Pradesh (155%), Tamil Nadu (120%), Telangana (112%), Maharashtra (100%), Rajasthan (93.5%), NCT of Delhi (88.6%). The top three states extend more credit than they collect in deposits locally. Meanwhile 12 states have CD ratios below 50%, acting as net savers for the banking system.

**5. Priority sector lending has a significant internal divergence hidden in headline numbers.**
Housing (+39.9% YoY) and Social Infrastructure (+35.3%) accelerating. Export Credit (−12.0%) and Others (−13.5%) contracting. The aggregate compliance figure masks this divergence entirely.

**6. UPI growth and NPA decline are coincident (r = −0.94), not causal.**
Both trends ran 2016–2024, driven by the same post-AQR banking clean-up and digital policy environment. Claiming UPI caused NPA improvement would be methodologically unsound — disentangling causal channels requires loan-level microdata.

---

## Repository structure

```
/data/
  clean_sector_credit.csv          # Sectoral credit outstanding + growth, incl. Priority Sector
  clean_industry_credit.csv        # 19 major industries, outstanding + growth
  clean_scb_aggregates.csv         # Deposits/credit/investment snapshot (Table 14)
  clean_casa_aggregates.csv        # Monthly CASA ratio + deposits, Jan 2024 – Apr 2026
  clean_npa_bankgroup.csv          # Gross/Net NPA % by bank group, FY1996–2024
  clean_npa_bankwise.csv           # Gross NPA by individual bank, FY2025
  clean_shg_linkage.csv            # SHG-Bank Linkage Programme, FY1992–2025
  clean_agri_credit.csv            # Institutional agriculture credit by channel, FY1971–2025
  clean_deposit_ownership.csv      # Deposit ownership by sector, FY2019–2026
  clean_digital_payments.csv       # UPI/IMPS/NEFT/RTGS/Cards volume & value, FY2015–2025
  clean_bankgroup_business.csv     # Deposits & credit by bank group (March snapshots)
  clean_state_cd_ratio.csv         # State-wise deposits, credit, CD ratio (Q4 FY2022–2026)
  clean_gdp.csv                    # Real GDP at constant 2011-12 prices + YoY growth %
  clean_cpi.csv                    # CPI Combined (base 2012=100) + inflation %
  clean_repo_rate.csv              # Policy repo rate by fiscal year (year-end)
  clean_unified_annual.csv         # Cross-pillar merged on FY key (overlap 2015–2025)
  clean_npa_forecast.csv           # NPA actuals + 3-year floor-adjusted projection
  clean_casa_forecast.csv          # CASA actuals + 12-month linear trend projection

/dashboard/
  indian_banking_dashboard_FINAL.twbx   # Tableau workbook — 18 datasets, 18 sheets, 5 dashboards
  indian_banking_dashboard_FINAL.pdf    # 5-page rendered dashboard preview, 20 charts

/docs/
  project_narrative.pdf                 # 12-page project narrative — economic logic, STAR
                                        # framework, challenges, limitations, conclusions
```

---

## Dashboard tabs (Tableau)

| Tab | Contents |
|---|---|
| Credit & Priority Sector | Sectoral credit, industry credit, priority sector growth, SCB aggregates |
| NPA & Asset Quality | NPA by bank group, system NPA trend, agri credit vs SHG, unified cross-pillar |
| Digital & Macro | UPI/IMPS/NEFT volume, payment value mix, GDP growth, repo rate vs CPI |
| State CD Ratio | 36 states/UTs bar chart, colour-coded by CD ratio level |
| Forecasts | NPA 3-year outlook, CASA 12-month projection, NPA by bank group trend |

---

## Data sources

| Source | Publisher | Access |
|---|---|---|
| RBI Bulletin — Current Statistics (Tables 12–16) | Reserve Bank of India | rbi.org.in → Publications → RBI Bulletin |
| DBIE — Multiple series | Reserve Bank of India | data.rbi.org.in |
| Handbook of Statistics on the Indian Economy | Reserve Bank of India | data.rbi.org.in → Publications → Time-Series |
| Quarterly Spatial Distribution of Deposits and Credit | Reserve Bank of India | data.rbi.org.in → Publications → Time-Series |

---

## Limitations

- **State-wise data covers only FY2022–23 to FY2025–26** — the Quarterly Spatial Distribution file only goes back to 2022 in the currently active series (Excluding RRBs). Earlier years require the older BSR series which has a different structure and stops at 2017.
- **CASA ratio is system-wide** — not comparable to any individual bank's published CASA ratio without explicit adjustment.
- **Forecasts are linear trend projections**, not econometric models. NPA floor set at ~1.8% based on long-run banking minima. Do not use for investment decisions.
- **Priority sector compliance cannot be verified** without the ANBC denominator (not included in this version).
- **Nationalised Banks and SBI/Associates stopped separate RBI reporting after March 2017** (post-merger consolidation) — bank-group trend analysis spanning before/after 2017 requires this caveat.
- **No bank-level CASA or credit drilldown** — individual bank-wise data limited to NPA ratios; CASA and credit growth are system/group-level only.

---

## Possible improvements / next steps

1. **Add ANBC denominator** — enables actual priority sector compliance ratio, not just outstanding amounts
2. **Bank-level CASA drilldown** — STRBI Table on Bank-wise Important Financial Indicators (one additional download)
3. **Extend state-wise CD ratio history** — join BSR-1/BSR-2 older series (2004–2017) to the current Quarterly Spatial Distribution series for a longer geographic trend
4. **Automate refresh pipeline** — scheduled script pulling from DBIE export URLs (template in project_narrative.pdf)
5. **Stress-testing module** — simple sensitivity analysis: "if GDP drops to 5%, what does NPA history suggest about credit quality?"
6. **Macro cross-reference deepening** — add investment (GFCF), unemployment, and bank credit-to-GDP ratio for a fuller macro-banking linkage

---

## License & attribution

All underlying data is public domain, published by the Reserve Bank of India. This repository contains only cleaned and restructured derivatives of that public data for analysis and educational purposes.
