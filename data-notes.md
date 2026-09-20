# Data notes

## AMAC Boundary

- Source: https://data.grid3.org
- Downloaded: 15 September 2026
- Geometry: Polygon
- Feature count: 1

## OSM Rivers

- Source: https://data.humdata.org
- Downloaded: 15 September 2026
- Query: waterway=river within AMAC extent via QuickOSM
- 59 features, lines
- Geometry: Line (LineString)
- Columns:
  - full_id (text)
  - osm_id (text)
  - osm_type (text)
  - waterway (text)
  - alt_name (text)
  - tunnel (text)
  - layer (text)
  - name (text)
- NULLs: Yes; NULL values are present in fields including alt_name, tunnel, layer and name
- Coverage: Covers the study area; no obvious spatial gaps were identified on the map

## OSM Streams

- Source: https://data.humdata.org
- Downloaded: 15 September 2026
- Query: waterway=stream within AMAC extent via QuickOSM
- 46 features, lines
- Geometry: Line (LineString)
- Columns:
  - full_id (text)
  - osm_id (text)
  - osm_type (text)
  - waterway (text)
  - name:es (text)
  - intermittent (text)
  - name (text)
  - tunnel (text)
  - layer (text)
- NULLs: Yes; NULL values are present in fields including name:es, intermittent, name, tunnel and layer
- Coverage: Covers the study area; no obvious spatial gaps were identified on the map

## OSM Roads

- Source: https://data.humdata.org
- Downloaded: 15 September 2026
- Query: highway=* within AMAC extent via QuickOSM
- 55,998 features, lines
- Geometry: Line (LineString)
- Columns:
  - full_id (text)
  - osm_id (text)
  - osm_type (text)
  - highway (text)
  - driveway (text)
  - crossing:markings (text)
  - proposed (text)
  - aeroway (text)
  - level (text)
  - bridge:movable (text)
  - bridge:structure (text)
  - motorcar (text)
  - informal (text)
  - maxspeed:backward (text)
  - indoor (text)
  - sport (text)
  - surface:note (text)
  - subject:wikidata (text)
  - subject (text)
  - cutting (text)
  - maxspeed:advisory (text)
  - covered (text)
  - barrier (text)
  - sidewalk:right (text)
  - embankment (text)
  - ramp (text)
  - handrail (text)
  - ford (text)
  - footway (text)
  - crossing (text)
  - smoothness (text)
  - turn (text)
  - noname (text)
  - roof:shape (text)
  - check_date (text)
  - sidewalk (text)
  - cycleway (text)
  - tracktype (text)
  - destination (text)
  - construction (text)
  - tunnel (text)
  - name:ar (text)
  - description (text)
  - old_name (text)
  - lit (text)
  - horse (text)
  - motor_vehicle (text)
  - foot (text)
  - bicycle (text)
  - name:etymology:wikidata (text)
  - name:etymology (text)
  - lane_markings (text)
  - loc_name (text)
  - disused:highway (text)
  - maxheight (text)
  - access (text)
  - service (text)
  - junction (text)
  - short_name (text)
  - incline (text)
  - ref (text)
  - turn:lanes (text)
  - alt_name (text)
  - surface (text)
  - layer (text)
  - bridge (text)
  - oneway (text)
  - maxspeed (text)
  - lanes (text)
  - name (text)
- NULLs: Yes; many optional OSM attributes contain NULL values
- Coverage: Covers the study area; no obvious spatial gaps were identified on the map

## CRS and preparation

- Source CRS: All source layers were initially in EPSG:4326 (WGS 84).
- Working CRS: EPSG:32632 (WGS 84 / UTM Zone 32N), chosen because AMAC is within UTM Zone 32N and the projected CRS uses metres, which is suitable for distance and area calculations.
- Study area: Abuja Municipal Area Council (AMAC), obtained from GRID3.
- Clipping: OSM rivers, streams and roads were clipped to the AMAC study-area boundary.
- Reprojection: All clipped layers were reprojected to EPSG:32632 (PCS) for analysis.
- Area check: The projected AMAC geometry gives an area of approximately 1,446.57 km². The area calculated from the original geographic coordinates was 0.119 and was therefore flagged as an incorrect area calculation caused by using a geographic CRS.
- Quality checks: Feature counts, attribute fields, NULL values, geometry types and spatial coverage were checked for the source and clipped layers.
- Problems found: NULL values were present in several optional OSM attributes. These were retained because they represent missing/unused OSM attributes rather than invalid geometry. The area calculation issue was resolved by calculating area using the projected layer.
- Data preparation: Raw source data were kept unchanged, while clipped and reprojected layers were prepared for analysis.
- Analysis-ready data: The clipped and reprojected layers will be stored together in an analysis-ready GeoPackage in data/processed/.
