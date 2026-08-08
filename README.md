# Financial Inclusion in India: Accounts vs Credit Access

## Question
Is banking actually reaching rural India, or are the accounts just there to receive government benefits (DBT)?

## Data
- Source: RBI Basic Statistical Return (BSR-1), data.rbi.org.in
- ~2.24 million rows, district-level, 2010–2026
- One row = totals for a Year × District × Population Group × Bank Group × Occupation combination

## Data Challenges & Cleaning
- Excel silently truncated the data at its ~1 million row limit. I caught it by cross-checking the source year range, which revealed ~10 years were missing. Moved the whole pipeline to Python (Pandas).
- The top 5 rows of each file were title text and notes, not column headers — set the correct header row.
- Removed junk rows that had no district and all-zero values.
- Fixed an inconsistent category: "semi-urban" was spelled two ways ("SEMI-URBAN" and "SEMI URBAN"), which would have split its totals if left unstandardized.

## Key Findings
1. Rural India has the most bank accounts (1.16 billion) — more than metropolitan areas.
2. But metropolitan accounts hold roughly 7x more credit per account (0.144 vs 0.020 Rs crore). Rural has the accounts, not the credit.
3. From 2010 to 2026, the gap widened — metropolitan credit grew steeply while rural stayed comparatively flat.

**Conclusion:** Rural India is financially included on paper, but on the receiving end — accounts arrived through government schemes like Jan Dhan and DBT, but credit access did not follow.

## Dashboard
![Dashboard](dashboard.png)

## Tools
Python (Pandas) · Matplotlib · Power BI · SQL

## Limitation
This analysis shows association, not causation. The data reveals the correlation between population group and credit access, but cannot prove government schemes *caused* the pattern. Establishing causation would require household-level data.
