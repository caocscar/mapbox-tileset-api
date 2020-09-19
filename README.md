# mapbox-tileset-api
One Time Steps

A. Create secret token with secret scopes privileges for the following:
  - Tilesets (List, Read, Write) 
  ~~- Uploads (List, Read, Write)~~ 
  ~~- Datasets (List, Write)~~ 
  
B. Copy and save secret token into environmental variable MAPBOX_ACCESS_TOKEN.  
C. `pip install mapbox-tilesets`

Assuming you have a GeoJSON newline-delimited) file
1. Create recipe.json

Command|Description
---|---
`tilesets list-sources <username>` | list tileset sources
`tilesets validate-source <filename>` | validate GeoJSON newline-delimited file
`tilesets upload-source <username> <id> <file>` | add tileset source
`tilesets create <username>.<tilesetid> --recipe <recipe-json> --name <tileset-name>` | create new empty tileset with recipe
`tilesets publish <username>.<tilesetid>` | publish tileset
`tilesets status <username>.<tilesetid>` | check status of tileset
`tilesets validate-recipe <recipe-json>` | validate recipe
`tilesets update-recipe <username>.<tilesetid> <recipe-json>` | update recipe

For the complete list, visit their github page:
https://github.com/mapbox/tilesets-cli/blob/master/README.md#upload-source

## Documentation
https://github.com/mapbox/tilesets-cli/blob/master/README.md#upload-source

https://docs.mapbox.com/help/tutorials/get-started-mts-and-tilesets-cli/

## How to create a GeoJSON newline-delimited file
A file formatted as line-delimited GeoJSON contains one or more GeoJSON Feature objects separated by newlines.

Method|Command
---|---
geopandas | `df.to_file('filename.geojson.ld', driver='GeoJSONSeq')`  
fiona from CLI | `fio cat filename.geojson > filename.geojson.ld`
