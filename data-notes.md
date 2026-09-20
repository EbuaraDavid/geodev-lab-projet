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
- All source layers arrived in EPSG:4326
- Study area: Abuja Municipal Area Council (AMAC), extracted from GRID3 boundary data
- Layers were clipped to the study area, then reprojected to EPSG:32632 (UTM Zone 32N)
- Area check: AMAC = 1,446.57 km², calculated from the projected geometry
- Working files are stored in data/processed/, while raw files remain untouched
