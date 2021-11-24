# This repository provides materials used for data analysis for the paper: <add a link here>

Overview
========

The repository contains datasets and Jupyter Notebooks used for the validation of PyGEE-SWToolbox

Dirctories
==========

  bin/ .......................... programs used during conversion  
      gdalcopyprj.cmd ............. copies gographic projection from one raster file to another  
      gdalcopyprj.py  
      osmconvert.exe .............. converts OpenStreetMap pbf binary files to o5m and osm format  
      osmfilter.exe ............... filter OpenStreetMap files  

  config/ ....................... config files use by some of the scripts
    osmconf.ini ................. used by osmconvert and osmfilter
    water.osmfilter.params ...... combines tags used to extract hydrography from OpenStreetMap files (polylines and polygons)

  data/ ......................... input files
    OpenStreetMap/
    SurfaceHydrology/ ........... major rivers extracted from http://www.ga.gov.au
    grid.kml .................... regular grid used to aggregate results and to parallelize the analysis
    HydroSHEDS_Catchment_MD.* ... HydroSHEDS cachment boundaries for Murray-Darling River Basin
    HydroSHEDS_rivers_MD.* ...... HydroSHEDS drainage network

  graphics/ ..................... images comparing generated water mask and OSM with WOfS and Surface Hydrology
    <images>

  notebooks/ .................... Python Notebooks used to perform different steps of the analysis
    ConvertWaterHistogramsAndThresholds.ipynb
    ExplodeShpPolylines.ipynb
    ExplodeShpPolylinesSH.ipynb
    HAND.ipynb
    HydroBASINS (fix).ipynb
    NDWI_thresholds.ipynb
    OSM water validation using LANDSAT (Murray & Darling).ipynb
    SHP2KML with fix.ipynb
    TileCatchmentsToGrid.ipynb
    UploadToFusionTable.ipynb    

  results/ ...................... some of the results generated during analysis
    water_and_results_examples/
    water.zip
    authoritative/ .............. screenshots comparing L8 watermask to some of the authoritative datastes

  src/
    javascript/
       download_SRTM.js ........... GEE script used to download SRTM data clipped by catchment boundaries
       download_water.js .......... GEE
       training.js ................ training dataset, generated within GEE

    javascript-ee-playground/ ......... GEE Playground scripts
       OSM_automatic_NDWI.js ..........
       OSM_compute_buffers.js ......... computes distances between rivers using Goodchilds's method
       OSM_compute_buffers_export.js .. 
       OSM_stat_per_catchment.js ...... generates aggregated statistics

    python/
       generate-hydro-datasets.py .......... script used to deleniate drainage network and compute HAND
       generate-hydro-datasets-runner.py ... wraps the above script to avoid out-of-memory probles

    scripts/
       convert.cmd .................... script used to extract hydrography from the OSM files

  web/ .......................... source code of the Google App Engine website (http://osm-water.appspot.com)
    httplib2
    media
    oauth2client
    static
    app.yaml
    config_web.py
    index.html
    README.md
    server.py
    six.py

  AuthoritativeDatasets.docx ...... early comparisons to the authoritative datasets in Australia

