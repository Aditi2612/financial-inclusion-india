Day 21 — Project 2 data sourced + truncation caught
Source: RBI DBIE > BSR-1
Has: Year, State, District, Population Group (RURAL/URBAN), Bank Group, Occupation, amounts

⚠️ DATA QUALITY ISSUE FOUND:
Excel export hit the 1,048,576-row limit and silently truncated.
RBI source has data from 2010; exported file only had 2020 onwards.
~10 years dropped without warning.

Verified by cross-checking source year range vs exported year range.
Fix: download in year-chunks, or process full data in Python (no row limit).
