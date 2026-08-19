# Bolivia Administrative Divisions / Bolivia



## Overview

| Item | Details |
|------|---------|
| Department | 9 |
| Province | 112 |
| Municipality | 339 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-19 |
| Website | [openadmindata.org/bo](https://openadmindata.org/bo/) |
| API | [openadmindata.org/api/bo](https://openadmindata.org/api/bo/) |
| National Anthem | [🎵 Listen & Download Bolivia National Anthem MP3](https://onlygames.me/national-anthems/bo/) |

## Browse by Department

| # | Department | Provinces | Municipalitys | Link |
|---|----|----|----|------|
| 1 | Beni | 8 | 19 | [Browse](divisions/beni-bo08/) |
| 2 | Chuquisaca | 10 | 29 | [Browse](divisions/chuquisaca-bo01/) |
| 3 | Cochabamba | 16 | 47 | [Browse](divisions/cochabamba-bo03/) |
| 4 | La Paz | 20 | 87 | [Browse](divisions/la-paz-bo02/) |
| 5 | Oruro | 16 | 35 | [Browse](divisions/oruro-bo04/) |
| 6 | Pando | 5 | 15 | [Browse](divisions/pando-bo09/) |
| 7 | Potosí (Potosi) | 16 | 40 | [Browse](divisions/potosi-bo05/) |
| 8 | Santa Cruz | 15 | 56 | [Browse](divisions/santa-cruz-bo07/) |
| 9 | Tarija | 6 | 11 | [Browse](divisions/tarija-bo06/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-department.json](data/all-department.json) | JSON | All 9 department records |
| [all-province.json](data/all-province.json) | JSON | All 112 province records |
| [all-municipality.json](data/all-municipality.json) | JSON | All 339 municipality records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-department.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['province']} provinces")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-department.json", "utf-8"));
console.log(`Total: ${data.length} departments`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=department, 2=province, 3=municipality |
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
divisions/{department-slug}/
divisions/{department-slug}/{province-slug}/
```

Municipalitys are listed inline in each province's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-department links
- [Per-department data](docs/llms-full/) — Full data by department

## Citation

```
Bolivia Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/bolivia-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
