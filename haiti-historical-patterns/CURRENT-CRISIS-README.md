# Haiti Current Crisis Extension — Field Documentation

**File:** `haiti-current-crisis-extension.json`  
**Version:** 2.0.0 (extends v1.0.0 core)  
**New Events:** 37 (IDs 47–83)  
**New Themes:** 3  
**Date Range:** January 2015 – April 2026  

---

## Purpose

The core dataset (`haiti-historical-patterns.json`) documents structural dependency cycles from 1804–2004. This extension adds the **current crisis window** needed for daily intelligence brief synthesis:

| Gap Filled | Why It Matters |
|-----------|----------------|
| Electoral collapse sequences (2015, 2016, 2021–26) | Every political development requires this as historical context |
| Gang consolidation arc (G9 2020 → Viv Ansanm 2024 → 90% control 2026) | Every security development requires gang territorial benchmark |
| MSS/GSF deployment patterns (Oct 2023 → Apr 2026) | Every intervention analysis requires mission status |
| Post-Moïse power vacuum (CPT, Conille, Fils-Aimé, Feb 7 2026 limbo) | Every CPT/government development requires vacuum context |

---

## New Themes

### `electoral_collapse` — Electoral Collapse Sequences (2015–2026)
**Color:** Amber (`#d4830a`) · **Events:** 12 (IDs 47–58)

Three consecutive electoral failures constituting a structural pattern:
1. **2015** — First-round annulled due to mass fraud
2. **2016** — Rerun with <10% eligible voter turnout (Moïse)
3. **2021–2026** — Complete suspension: no president, no parliament, CPT expires without elections; next attempt scheduled Aug 2026 but widely considered infeasible under current security conditions

**Key pattern for briefs:** Each electoral failure is instrumentalized to extend unaccountable executive power. The Feb 7 2026 CPT expiry is the latest iteration — 10 years since Haiti's last credible election.

---

### `gang_consolidation_2021` — Gang Consolidation & State Collapse (2021–present)
**Color:** Crimson (`#8b1a1a`) · **Events:** 12 (IDs 59–70)

| Date | Control Index | Key Event |
|------|--------------|-----------|
| Jun 2020 | — | G9 founded (state-sponsored) |
| Jul 2021 | ~30% | Moïse assassinated; patron removed |
| Jul 2022 | ~50% | Cité Soleil massacre; territorial consolidation |
| Sep 2023 | ~60% | Viv Ansanm truce announced |
| Feb 2024 | ~80% | Coordinated assault; airport/prisons seized |
| Jan 2025 | ~85% | 1M+ IDPs; criminal parallel governance |
| Mar 2026 | ~90% | 26 gangs; sea/road routes; southern expansion |

**Key pattern for briefs:** Viv Ansanm is not a traditional gang coalition — ACLED and GI-TOC identify it as a parallel sovereignty structure with bureaucratized extortion, territorial governance, and political ambitions. Chérizier's Aug 2025 US indictment attempts to disrupt diaspora funding channels.

---

### `mss_gsf` — MSS/GSF International Security Intervention (2023–present)
**Color:** Teal (`#1a7a7a`) · **Events:** 13 (IDs 71–83)

**Mission timeline:**
```
Oct 2022  Haiti requests force
Oct 2023  UNSC Res 2699 → MSS authorized (2,500 ceiling, voluntary funds)
Jun 2024  First 400 Kenyan officers land (8-month delay)
Sep 2024  ~600 deployed; funding crisis; Res 2751 renews mandate
Jan 2025  ~1,000 deployed; US freezes funding
Feb 2025  UN SG: peacekeeping mission infeasible
Sep 2025  UNSC Res 2793 → MSS → GSF (Gang Suppression Force)
Apr 2026  First GSF troops land (Chad); full capacity: Oct 2026
```

**Structural constraint for briefs:** The voluntary-contributions-only model (vs. UN-assessed budget) is the mission's fundamental weakness — it subjects security intervention to US political cycles. US funding freeze Jan 2025 and the forced MSS→GSF transition reflect this. Kenya withdrawal timeline ~Oct 2026.

---

## New Field: `notes`

Extension events include a `notes` field absent from v1.0.0 core events. Contains sourced analytical context, key figures, and cross-references.

```json
{
  "id": 64,
  "year_label": "Feb 29 2024",
  "theme": "gang_consolidation_2021",
  "event": "Viv Ansanm coordinated assault — airports, prisons, police HQ",
  "actor": "Viv Ansanm / Jimmy Chérizier",
  "type": "military",
  "impact": "critical",
  "impact_rank": 1,
  "location": "Port-au-Prince metropolitan area",
  "notes": "Synchronized assault across Port-au-Prince: Toussaint Louverture airport closed, 2 major prisons stormed (4,000 inmates escape), multiple police stations burned, key roads blocked. Coincides with PM Henry's Kenya trip. ~80% of capital under gang control."
}
```

---

## Combined Dataset Statistics

Merging core (v1.0.0) + extension (v2.0.0):

| Metric | Core (1804–2004) | Extension (2015–2026) | **Total** |
|--------|-----------------|----------------------|-----------|
| Events | 46 | 37 | **83** |
| Themes | 4 | 3 | **7** |
| Critical events | 24 | 20 | **44** |
| High-impact events | 16 | 13 | **29** |

---

## Key Sources

- **ACLED** — [Viv Ansanm: the alliance reshaping Haiti's gangland](https://acleddata.com/report/viv-ansanm-living-together-fighting-united-alliance-reshaping-haitis-gangland) (Oct 2024)
- **GI-TOC** — [Last Chance? Breaking Haiti's Political and Criminal Impasse](https://globalinitiative.net/wp-content/uploads/2025/01/Last-chance-Breaking-Haitis-political-and-criminal-impasse-GI-TOC-January-2025.pdf) (Jan 2025)
- **Security Council Report** — [Haiti monthly forecasts & What's in Blue](https://www.securitycouncilreport.org) (2023–2026)
- **UN News** — Gang control briefings, BINUH mandate renewals (2024–2026)
- **Reuters / Al Jazeera / BBC** — CPT transitions, Henry resignation, Fils-Aimé handover (2024–2026)
- **US DOJ / OFAC** — Chérizier sanctions indictment (Aug 2025)
- **Stimson Center** — [Sharing the Burden of Securing Haiti](https://www.stimson.org/2025/sharing-the-burden-of-securing-haiti/) (Nov 2025)
- **Wikipedia (Haitian conflict / G9 / GSF articles)** — Cross-referenced and verified against primary sources

---

*AYITI INTEL · KreyòlGenius · Port-au-Prince, Haiti · gestbiz@gmail.com*
