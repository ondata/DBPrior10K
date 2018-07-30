# Su questo dataset

Il dataset originale è `DBPriorItalia.zip`. 

- scaricato: 30 luglio 2018.
- URL sorgente: [http://www.centrointerregionale-gis.it/DBPrior/Dati/DBPriorItalia.zip](http://www.centrointerregionale-gis.it/DBPrior/Dati/DBPriorItalia.zip);
- formato file: ArcView Shapefile;
- sistema di coordinate: EPSG:4326


## Elaborazioni integrative

- decompresso il file zip;
- convertito in geopackage con ogr2ogr

```
ogr2ogr -f GPKG dbprior.gpkg Idrografia/SA.shp
ogr2ogr -update -f GPKG dbprior.gpkg Idrografia/EI.shp
ogr2ogr -update -f GPKG dbprior.gpkg Idrografia/CS.shp
ogr2ogr -update -f GPKG dbprior.gpkg Idrografia/NI.shp
ogr2ogr -update -f GPKG dbprior.gpkg Strade/ITS.shp
ogr2ogr -update -f GPKG dbprior.gpkg "Limiti Amministrativi/CENTRI.shp"
ogr2ogr -update -f GPKG dbprior.gpkg Strade/TS.shp
ogr2ogr -update -f GPKG dbprior.gpkg "Limiti Amministrativi/PRO.shp"
ogr2ogr -update -f GPKG dbprior.gpkg "Limiti Amministrativi/REG.shp"
ogr2ogr -update -f GPKG dbprior.gpkg "Limiti Amministrativi/COM.shp"
ogr2ogr -update -f GPKG dbprior.gpkg Ferrovie/TF.shp
ogr2ogr -update -f GPKG dbprior.gpkg Ferrovie/ITF.shp
```