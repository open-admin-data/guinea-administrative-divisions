# Guinea Administrative Divisions / Guinée

Open dataset of Guinea's administrative hierarchy — 8 regions, 34 prefectures, and 340 sub-prefectures. French reference data with geographic coordinates at every level. Designed for developers, researchers, government agencies, and AI agents.

Licensed under CC-BY-4.0. Browse the hierarchy through GitHub's folder navigation, download aggregate files in JSON/CSV/NDJSON, or integrate directly via raw URLs.

## Overview

| Item | Details |
|------|---------|
| Region | 8 |
| Prefecture | 34 |
| Sub-prefecture | 340 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-05-24 |

## Browse by Region

| # | Region | Prefectures | Sub-prefectures | Link |
|---|----|----|----|------|
| 1 | Boke | 5 | 37 | [Browse](divisions/boke-gn001/) |
| 2 | Conakry | 1 | 5 | [Browse](divisions/conakry-gn002/) |
| 3 | Faranah | 4 | 41 | [Browse](divisions/faranah-gn003/) |
| 4 | Kankan | 5 | 57 | [Browse](divisions/kankan-gn004/) |
| 5 | Kindia | 5 | 45 | [Browse](divisions/kindia-gn005/) |
| 6 | Labe | 5 | 53 | [Browse](divisions/labe-gn006/) |
| 7 | Mamou | 3 | 36 | [Browse](divisions/mamou-gn007/) |
| 8 | Nzerekore | 6 | 66 | [Browse](divisions/nzerekore-gn008/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-region.json](data/all-region.json) | JSON | All 8 region records |
| [all-prefecture.json](data/all-prefecture.json) | JSON | All 34 prefecture records |
| [all-sub_prefecture.json](data/all-sub_prefecture.json) | JSON | All 340 sub-prefecture records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-region.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['prefecture']} prefectures")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-region.json", "utf-8"));
console.log(`Total: ${data.length} regions`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=region, 2=prefecture, 3=sub-prefecture |
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
divisions/{region-slug}/
divisions/{region-slug}/{prefecture-slug}/
```

Sub-prefectures are listed inline in each prefecture's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-region links
- [Per-region data](docs/llms-full/) — Full data by region

## Citation

```
Guinea Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/guinea-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [ListBase](https://www.listbase.org) — Structured reference data for every country
- [open-admin-data](https://github.com/open-admin-data) — Open administrative data for ASEAN countries
- [thailand-administrative-divisions](https://github.com/open-admin-data/thailand-administrative-divisions) — Thailand dataset
