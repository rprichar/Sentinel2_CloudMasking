# Sentinel2_CloudMasking

this notebook can be used to create synthetic cloud free imagery
with mosaic datasets created from https://github.com/rprichar/Sentinel-2-L2A-AWS-MDCS

place the Sentinel2_Median_BugFix.py and Sentinel2_Median_BugFix.rft.xml 
in C:\Program Files\ArcGIS\Pro\Resources\Raster\Functions\Custom

update paths in notebook and run

after the notebook is complete:
1) use copy raster on the base mosaic to create a median raster
2) use copy raster on the cloud masked raster to create a cloud masked median raster
3) use raster calculator to combine rasters using the cloud masked median raster and median raster
  where the cloud masked median raster is null
4) create random raster as a single band with the raster info coming from step3
5) composite bands from step 3 and 4 with 3 as the first 14 bands and 4 as the 15th band
6) use copy raster to persist synthetic cloud free raster
