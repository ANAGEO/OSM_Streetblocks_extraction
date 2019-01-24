# OSM Streetblocks extraction
This repository contains a Python script (Jupyter notebook) implementing extraction of street blocks from OpenStreetMap (or other sources of vectorial data) using PostGis. 

This code was published belong to the following paper:

Grippa & al. 	Mapping Urban Land Use at Street Block Level Using OpenStreetMap, Remote Sensing Data, and Spatial Metrics. ISPRS Int. J. Geo-Inf. 2018, 7, 246. [doi:10.3390/ijgi7070246](https://doi.org/10.3390/ijgi7070246)

## Cite this code
Please use the following DOI for citing this code: [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1290638.svg)](https://doi.org/10.5281/zenodo.1290638)

## Related code
The code provided in this repository could be combined with the one provided in [https://github.com/ANAGEO/OSM_Streetblocks_extraction](https://github.com/ANAGEO/OSM_Streetblocks_extraction), to reproduce the aforementioned research.

## Workflow and outputs
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


## Known issues
- Some issues could appear on Windows when using 'osm2pgsql' command, regarding to the password for the Postgis databse.
- The resulting layer could contain self-intersecting polygons. Add extra step should be added after the extraction of the block in order to check is there are self-interecting polygons, and fix them in this case.
