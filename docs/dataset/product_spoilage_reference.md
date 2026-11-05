# Product Spoilage Reference Dataset

## Purpose
This dataset contains reference storage conditions for products monitored by AtmoSync. It will support spoilage-risk analysis using container temperature and humidity telemetry.

## File
`data/reference/product_spoilage_reference.csv`

## Fields
- product_name: Canonical product name.
- product_stage_or_variety: Product maturity stage or variety covered by the reference.
- recommended_temp_min_c: Lower recommended storage temperature in Celsius.
- recommended_temp_max_c: Upper recommended storage temperature in Celsius.
- best_temp_c: Midpoint of the recommended temperature range.
- humidity_min_pct: Lower recommended relative humidity percentage.
- humidity_max_pct: Upper recommended relative humidity percentage.
- shelf_life_min_hours: Lower approximate storage-life estimate in hours.
- shelf_life_max_hours: Upper approximate storage-life estimate in hours.
- data_source: Name of the reference publication.
- source_url: Reference URL.
- notes: Assumptions and limitations.

## Important limitations
- Values are reference estimates, not universal spoilage thresholds.
- Shelf life depends on variety, maturity, initial quality, packaging, handling and storage conditions.
- Green bananas and firm-ripe tomatoes have different storage requirements from other maturity stages.
- A midpoint temperature is a modelling convenience, not necessarily a biological optimum.
- Shelf-life estimates should not be treated as guaranteed remaining shelf life.
- Further product-specific validation is required before production use.

## Sources
1. FAO - Storage of Horticultural Crops:
   https://www.fao.org/4/x5403e/x5403e09.htm
2. UC Davis - Banana:
   https://postharvest.ucdavis.edu/produce-facts-sheets/banana
3. UC Davis - Tomato:
   https://postharvest.ucdavis.edu/produce-facts-sheets/tomato
4. UC Davis - Strawberry:
   https://postharvest.ucdavis.edu/produce-facts-sheets/strawberry
5. University of Maine - Storage Conditions: Fruits and Vegetables:
   https://extension.umaine.edu/publications/4135e/
