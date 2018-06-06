# OSM Streetblocks extraction
This repository contains a Python script (Jupyter notebook) implementing extraction of street blocks from OpenStreetMap (or other sources of vectorial data) using PostGis. 

The general workflow is as follow: 
![](illustrations/Flowchart.png)

- Input of the AOI as a polygon
![](illustrations/Full_AOI.png)

- Creation of tiles for download of OSM data
![](illustrations/Full_AOI_tiled.png)

- Linestrings extracted from OSM
![](illustrations/Full_linestrings_tiled.png)

- Extraction of street blocks polygons from linestrings
![](illustrations/Full_streetblocks.png)

- Optical image
![](illustrations/Zoom_optical.png)

- Linestrings before snapping using PostGis topology
![](illustrations/Zoom_linestrings_unsnapped.png)

- Linestrings snapped (using PostGis topology)
![](illustrations/Zoom_linestrings_snapped.png)

- Initial extraction of street blocks - Presence of artifacts polygons
![](illustrations/Zoom_streetblocks_withartifacts.png)

- Final street blocks layer - Artifacts were removed
![](illustrations/Zoom_streetblocks_cleaned.png)


# Known issues
- Some issues could appear on Windows when using 'osm2pgsql' command, regarding to the password for the Postgis databse.
