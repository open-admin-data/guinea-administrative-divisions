# Methodology

## Data Sources

- **OCHA COD-AB Guinea** (CC BY-IGO) — 8 regions, 34 prefectures, 340 sub-prefectures with P-codes and centroid coordinates

## Processing

1. Administrative records from OCHA COD-AB XLSX gazetteer
2. Coordinates from OCHA centroid data (100% coverage)
3. Multi-format export: JSON, NDJSON, CSV

## Accuracy

- Coordinates: 100% at all levels
- Names: 100% at all levels (French)
- Build script is idempotent: same input always produces same output