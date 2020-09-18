# mapbox-tileset-api
One Time Steps

A. Create secret token with secret scopes privileges for the following:
  - Uploads (List, Read, Write)
  - Tilesets (List, Read, Write)
  - Datasets (List, Write)
B. Copy and save secret token into environmental variable MAPBOX_ACCESS_TOKEN
C. `pip install mapbox-tilesets` in terminal

## How to create a GeoJSON newline-delimited file
Method|Command
---|---
geopandas | `df.to_file('filename.geojson.ld', driver='GeoJSONSeq')`  
fiona from CLI | `fio cat filename.geojson > filename.geojson.ld`

Assuming you have a GeoJSON newline-delimited) file
1. Create recipe.json

Command|Description
---|---
`tilesets list_sources <username>` | list tileset sources
`tilesets validate_source <filename>` | validate GeoJSON newline-delimited file
`tilesets add-source <source> <file>` | add tileset source
`tilesets create <username> <tilesetid> --recipe <recipe-json> --name <tileset-name>` | create tileset with recipe
`tilesets publish <username>.<tilesetid>` | publish tileset
`tilesets status <username>.<tilesetid>` | check status of tileset
`tilesets update-recipe <username>.<tilesetid> <recipe-json>` | update recipe

A typical sequence would be:
- tilesets list-sources
- tilesets validate-source
- tilesets add-source
- create recipe.json
- tilesets create
- tilesets publish
- tilesets status
- tilesets update-recipe
