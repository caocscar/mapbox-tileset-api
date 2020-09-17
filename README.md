# mapbox-tileset-api
One Time Steps

A. Create secret token with secret scopes privileges for the following:
  - Uploads (List, Read, Write)
  - Tilesets (List, Read, Write)
  - Datasets (List, Write)
B. Copy and save secret token into environmental variable MAPBOX_ACCESS_TOKEN
C. `pip install mapbox-tilesets` in terminal

## How to create a GeoJSON newline-delimited file
A. Geopandas: df.to_file('filename.geojson.ld', driver='GeoJSONSeq')
B. Fiona: `fio cat filename.geojson > filename.geojson.ld`


0. Create GeoJSON newlines (line-delimited) file

1. `tilesets list_sources <username>`
2. `tilesets validate_source filename.geojson.ld`
