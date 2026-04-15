# AYITI INTEL — Haiti Historical Patterns Dataset

**Version:** 1.0.0  
**Events:** 46  
**Themes:** 4  
**License:** [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)  
**Live Dashboard:** [AYITI INTEL](https://ayitiintel.com)

---

## Overview

Structured dataset of 46 historical events across four structural dependency cycles in Haitian history, compiled for the AYITI INTEL intelligence platform. Each event documents actors, mechanisms, and impact ratings to support cross-theme pattern analysis.

The dataset is embedded in [`haiti-historical-patterns.json`](./haiti-historical-patterns.json) and served live in the interactive dashboard.

---

## Themes

| ID | Name | Period | Events | Color |
|----|------|--------|--------|-------|
| `debt` | 1825 French Independence Debt | 1804–1947 | 9 | Gold |
| `occupation` | 1915–34 US Military Occupation | 1915–1941 | 13 | Red |
| `junta` | 1991–94 Cédras Military Junta | 1991–1994 | 13 | Purple |
| `coup` | 2004 Gang Consolidation & Coup | 2003–2017 | 11 | Blue |

---

## File: `haiti-historical-patterns.json`

### Top-level structure

```json
{
  "$schema": "...",
  "dataset": "Haiti Historical Patterns — Intelligence Database",
  "version": "1.0.0",
  "generated_at": "ISO-8601 UTC timestamp",
  "generated_by": "AYITI INTEL Dashboard",
  "license": "CC BY 4.0",
  "description": "...",
  "source": "...",
  "themes": { ... },
  "field_definitions": { ... },
  "stats": { ... },
  "events": [ ... ]
}
```

### Event record fields

| Field | Type | Description |
|-------|------|-------------|
| `id` | `integer` | Sequential identifier (1–46), ordered by theme then chronology |
| `year_label` | `string` | Human-readable date string. May be a year (`"1825"`), year range (`"1991-1993"`), month-year (`"Jul 1915"`), or full date (`"Sep 30 1991"`). Parse with care for numeric sorting. |
| `theme` | `string` | Theme identifier. One of: `debt` \| `occupation` \| `junta` \| `coup` |
| `theme_name` | `string` | Full human-readable theme name |
| `event` | `string` | Short descriptive event label (≤80 chars), suitable for table display |
| `actor` | `string` | Primary actor(s). Person, institution, or coalition. Multiple actors separated by ` / ` |
| `type` | `string` | Event category: `military` \| `economic` \| `political` \| `resistance` |
| `impact` | `string` | Qualitative impact rating: `critical` \| `high` \| `medium` \| `low` |
| `impact_rank` | `integer` | Numeric sort key: 1=critical, 2=high, 3=medium, 4=low |
| `location` | `string` | Primary geographic location |

### Controlled vocabularies

**`theme`**
- `debt` — 1825 French indemnity and related financing mechanisms
- `occupation` — 1915–34 US military presence and institutional control
- `junta` — 1991–94 military coup, embargo, and Operation Uphold Democracy
- `coup` — 2004 Aristide removal, paramilitaries, and MINUSTAH

**`type`**
- `military` — Armed action, troop movements, assassinations, repression
- `economic` — Debt instruments, sanctions, trade embargoes, fiscal control
- `political` — Treaties, elections, accords, governmental transitions
- `resistance` — Counter-actions by Haitian actors against external control

**`impact`**
- `critical` — Structural, irreversible, or mass-casualty event (24 of 46)
- `high` — Significant policy or institutional consequence (16 of 46)
- `medium` — Notable but bounded consequence (6 of 46)
- `low` — Background or contextual event

---

## Dataset Statistics

| Dimension | Breakdown |
|-----------|-----------|
| **By theme** | debt: 9 · occupation: 13 · junta: 13 · coup: 11 |
| **By type** | military: 16 · economic: 13 · political: 12 · resistance: 1 |
| **By impact** | critical: 24 · high: 16 · medium: 6 · low: 0 |

---

## Usage Examples

### Filter by theme (Python)
```python
import json

with open("haiti-historical-patterns.json") as f:
    db = json.load(f)

junta_events = [e for e in db["events"] if e["theme"] == "junta"]
critical_military = [e for e in db["events"] if e["impact"] == "critical" and e["type"] == "military"]
```

### Filter by theme (JavaScript)
```js
const { events } = await fetch("haiti-historical-patterns.json").then(r => r.json());

const economicEvents = events.filter(e => e.type === "economic");
const sortedByImpact = events.slice().sort((a, b) => a.impact_rank - b.impact_rank);
```

### Cross-theme pattern query (Python)
```python
# Events where foreign actors imposed economic control
econ_control = [
    e for e in db["events"]
    if e["type"] == "economic" and e["impact"] in ("critical", "high")
]
for e in econ_control:
    print(f"[{e['theme']:12}] {e['year_label']:<18} {e['event']}")
```

---

## Sources

Primary and secondary historical sources consulted:

- **Debt theme:** Montinat & Gauthier, *La Dette de l'Indépendance* (2022); Thomas Piketty et al., NYT report on the "Double Debt" (2022)
- **Occupation theme:** Mary Renda, *Taking Haiti* (2001); Brenda Plummer, *Haiti and the United States* (1992)
- **Junta theme:** Paul Farmer, *The Uses of Haiti* (1994); Robert Fatton Jr., *Haiti's Predatory Republic* (2002)
- **2004 coup theme:** Peter Hallward, *Damming the Flood* (2007); Jeb Sprague, *Paramilitarism and the Assault on Democracy in Haiti* (2012)

---

## Contributing

This dataset is maintained as part of the AYITI INTEL platform. To suggest corrections or additions, open an issue in this repository or contact the maintainer via [gestbiz@gmail.com](mailto:gestbiz@gmail.com).

---

*AYITI INTEL — Intelligence platform for NGOs, embassies, and research institutions.*  
*Built by KreyòlGenius · Port-au-Prince, Haiti*
