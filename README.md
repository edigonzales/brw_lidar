## LAS-Format ##
Es werden die RGB-losen LAS-Dateien transformiert, dh. LAS-Format 1.

## Tileindex erstellen ##
```
find /home/stefan/mr_candie_nas/Geodaten/ch/so/agi/hoehen/2014/lidar/ -maxdepth 1 -iname "*.laz" | pdal tindex tileindex.gpkg -f "GPKG" --a_srs EPSG:21781 --t_srs EPSG:21781 --fast_boundary --stdin --lyr_name tileindex
```



pdal tindex --merge /home/stefan/tmp/lidar/srs/tileindex.gpkg --lyr_name tileindex --polygon "POLYGON ((594998 225000,594998 226000,594998.097886967356317 226000.61803398875054,594998.38196601124946 226001.175570504594361,594998.824429495376535 226001.61803398875054,594999.38196601124946 226001.902113032585476,595000 226002,596000 226002,596000.61803398875054 226001.902113032585476,596001.175570504623465 226001.61803398875054,596001.61803398875054 226001.175570504594361,596001.902113032643683 226000.61803398875054,596002 226000,596002 225000,596001.902113032643683 224999.38196601124946,596001.61803398875054 224998.824429495405639,596001.175570504623465 224998.38196601124946,596000.61803398875054 224998.097886967414524,596000 224998,595000 224998,594999.38196601124946 224998.097886967414524,594998.824429495376535 224998.38196601124946,594998.38196601124946 224998.824429495405639,594998.097886967356317 224999.38196601124946,594998 225000))" tmp.las


pdal tindex --merge /home/stefan/tmp/lidar/srs/tileindex.gpkg --lyr_name tileindex tmp.las

wkt_geom	location	srs	modified	created
Polygon ((593000 227000, 594000 227000, 594000 228000, 593000 228000, 593000 227000))	/home/stefan/tmp/lidar/srs/./LAS_593227.laz	EPSG:21781	2015-08-13	2015-08-13



POLYGON ((593000 227000, 594000 227000, 594000 228000, 593000 228000, 593000 227000))

pdal tindex --merge /home/stefan/tmp/lidar/srs/tileindex.gpkg --lyr_name tileindex --polygon "POLYGON ((593000 227000, 594000 227000, 594000 228000, 593000 228000, 593000 227000))" tmp2.las




find . -maxdepth 1 -iname "*.laz" | pdal tindex tileindex.gpkg -f "GPKG" --fast_boundary --a_srs "+proj=somerc +lat_0=46.952405555555555N +lon_0=7.439583333333333E +ellps=bessel +x_0=600000 +y_0=200000 +towgs84=674.374,15.056,405.346 +units=m +units=m +k_0=1 +nadgrids=./chenyx06/chenyx06a.gsb" --t_srs "+proj=somerc +lat_0=46.952405555555555N +lon_0=7.439583333333333E +ellps=bessel +x_0=600000 +y_0=200000 +towgs84=674.374,15.056,405.346 +units=m +units=m +k_0=1 +nadgrids=./chenyx06/chenyx06a.gsb" --stdin --lyr_name tileindex

find . -maxdepth 1 -iname "*.laz" | pdal tindex tileindex.gpkg -f "GPKG" --fast_boundary --a_srs EPSG:21781 --t_srs EPSG:21781 --stdin --lyr_name tileindex


gdal_rasterize -a fs_mm -tr 100.0 100.0 -l centroids_diff_solothurn -a_nodata -9999 /home/stefan/tmp/ntv2/centroids_diff_solothurn.shp /home/stefan/Downloads/ntv2_genauigkeit.tif
