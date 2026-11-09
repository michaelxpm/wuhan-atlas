# whv4 Wuhan Urban Atlas with Residential

VS Code: open this folder, right click `index.html` → **Open with Live Server**. No API key.

## Added data
- Residential: 2938 OSM residential landuse polygons, joined one-to-one by OSM source ID to the supplied CSV coordinates and metadata. No invented population or building counts.
- Administrative districts: 13 admin_level=6 district polygons. 14 unlabeled Point features from the raw boundary export were excluded.
- All earlier metro, water and landmark data remain.

## Reliability and caveats
- All coordinates treated as WGS84 longitude/latitude; map uses a consistent local equirectangular metric approximation.
- Residential categories **小面积 / 中面积 / 大面积** are terciles of estimated polygon land area (thresholds approximately 14,348 and 41,548 m²). These are NOT building size, number of households, population, property prices or official residential complex classes.
- The residential CSV flags every entry as unverified; these flags are preserved.
- OSM `landuse=residential` polygons can be neighbourhoods, housing compounds, or broad residential land areas. They do not always correspond to a single 楼盘/小区.
- Polygons were topologically simplified with ~2.5e-5 degree tolerance for browser rendering. Source files are unmodified and should be retained separately.
- District labels are approximate bounding-box centres and may be outside oddly shaped polygons.
- District overlay defaults OFF to keep the map legible. Residential points default ON; names only appear when zoomed in.
- Metro connection lines are schematic straight lines, NOT surveyed railway alignments.
- OSM completeness and district accuracy not independently verified.
