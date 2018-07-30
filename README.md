# Su questo dataset

> Il  progetto  “Strati  Prioritari  di  Interesse  Nazionale”  (DBPrior10k),  è  stato  realizzato  nell’ambito dell’Intesa Stato-Regioni-Enti Locali sui Sistemi Informativi Geografici (IntesaGIS) a partire dal settembre  2003,  ed  è  stato  consegnato  dal  Centro  Interregionale,  che  ne  ha  svolto  la  direzione lavori, agli Enti Committenti (Regione Basilicata, Ministero dell’Ambiente) nel giugno 2005. Esso  rappresenta  la  copertura  della  viabilità  stradale  e  ferroviaria,  dell’idrografia  e  dei  limiti amministrativi, in scala 1:10.000, del territorio Nazionale.

Il sito ufficiale non è pienamente accessibile (al 30 luglio 2018), ma ci sono ancora dei file raggiungibili, come quello di insieme nazionale.

È un dataset non più aggiornato, ma che può essere utile per analisi storiche; questo repo è stato proprio creato per preservarne una copia.

La copia del dataset nazionale è il file [`DBPriorItalia.zip`](./dati/DBPriorItalia.zip) 

- scaricato: 30 luglio 2018;
- URL sorgente: [http://www.centrointerregionale-gis.it/DBPrior/Dati/DBPriorItalia.zip](http://www.centrointerregionale-gis.it/DBPrior/Dati/DBPriorItalia.zip);
- formato file: ArcView Shapefile;
- sistema di coordinate: EPSG:4326.

# Licenza originale

Licenza Creative Commons - Attribuzione 2.5 Italia (testo integrale: http://creativecommons.org/licenses/by/2.5/it/legalcode). 
L'attribuzione dovrà fornire una menzione adeguata di:

- Autore originale e/o titolare dei diritti: CISIS;
- terze parti designate, se esistenti;
- Nome della Banca Dati: DBPrior10K.

# Elaborazioni integrative di onData

- decompresso il file zip;
- convertiti gli shapefile in un unico geopackage con [ogr2ogr](https://www.gdal.org/ogr2ogr.html). Il file è [`dbprior.7z`](./dati/dbprior.7z) 

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