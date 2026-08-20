# Poland Administrative Divisions / Polska



## Overview

| Item | Details |
|------|---------|
| Voivodeship | 16 |
| County | 380 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-20 |
| Website | [openadmindata.org/pl](https://openadmindata.org/pl/) |
| API | [openadmindata.org/api/pl](https://openadmindata.org/api/pl/) |
| Flag | [PNG](https://onlygames.me/flags-png/pl/) · [SVG](https://onlygames.me/flags-svg/pl/) · [PDF](https://onlygames.me/flags-pdf/pl/) |
| National Anthem | [🎵 Listen & Download Poland National Anthem MP3](https://onlygames.me/national-anthems/pl/) |

## Browse by Voivodeship

| # | Voivodeship | Countys | Link |
|---|----|----|------|
| 1 | Dolnośląskie (Dolnoslaskie) | 30 | [Browse](divisions/dolnoslaskie-pl002/) |
| 2 | Kujawsko-Pomorskie | 23 | [Browse](divisions/kujawsko-pomorskie-pl004/) |
| 3 | Lubelskie | 24 | [Browse](divisions/lubelskie-pl006/) |
| 4 | Lubuskie | 14 | [Browse](divisions/lubuskie-pl008/) |
| 5 | Łódzkie (Lodzkie) | 24 | [Browse](divisions/lodzkie-pl010/) |
| 6 | Małopolskie (Malopolskie) | 22 | [Browse](divisions/malopolskie-pl012/) |
| 7 | Mazowieckie | 42 | [Browse](divisions/mazowieckie-pl014/) |
| 8 | Opolskie | 12 | [Browse](divisions/opolskie-pl016/) |
| 9 | Podkarpackie | 25 | [Browse](divisions/podkarpackie-pl018/) |
| 10 | Podlaskie | 17 | [Browse](divisions/podlaskie-pl020/) |
| 11 | Pomorskie | 20 | [Browse](divisions/pomorskie-pl022/) |
| 12 | Śląskie (Slaskie) | 36 | [Browse](divisions/slaskie-pl024/) |
| 13 | Świętokrzyskie (Swietokrzyskie) | 14 | [Browse](divisions/swietokrzyskie-pl026/) |
| 14 | Warmińsko-Mazurskie (Warminsko-Mazurskie) | 21 | [Browse](divisions/warminsko-mazurskie-pl028/) |
| 15 | Wielkopolskie | 35 | [Browse](divisions/wielkopolskie-pl030/) |
| 16 | Zachodniopomorskie | 21 | [Browse](divisions/zachodniopomorskie-pl032/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-voivodeship.json](data/all-voivodeship.json) | JSON | All 16 voivodeship records |
| [all-county.json](data/all-county.json) | JSON | All 380 county records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-voivodeship.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['county']} countys")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-voivodeship.json", "utf-8"));
console.log(`Total: ${data.length} voivodeships`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=voivodeship, 2=county |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{voivodeship-slug}/
```

Countys are listed inline in each voivodeship's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-voivodeship links
- [Per-voivodeship data](docs/llms-full/) — Full data by voivodeship

## Citation

```
Poland Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/poland-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
