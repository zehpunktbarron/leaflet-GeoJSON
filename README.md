# leaflet-GeoJSON
A simple leaflet map which loads an external GeoJSON file.
The GeoJSON file can be queried. The results (properties from GeoJSON file) are displayed in a pop-up.

Vorarbeiten:
1) Shapefiles in WGS84 (epsg: 4326) projizieren.

2) Umlaute in ArcMap korrigieren

3) Mit ogr2ogr das Shapefile in GeoJSON konvertieren:
"C:\Program Files\GDAL\ogr2ogr.exe" -f GeoJSON -t_srs crs:84 W:\02_Anwendungen\Klima_2010\leaflet\klimagutachten_2001_rheinau.geojson W:\02_Anwendungen\Klima_2010\leaflet\klimagutachten_wgs84.shp

3) Überlagerte Polygone: Je weiter unten im GeoJSON das Feature, desto weiter oben als Layer in leafleat

4) Ggf. Unformatiertes GeoJSON sauber formatieren mit https://jsonformatter.curiousconcept.com/


Sollte, warum auch immer, X und Y Koordinaten vertauscht werden müssen:
"C:\Program Files\GDAL\ogr2ogr.exe" -f GeoJSON -s_srs "+proj=latlong +datum=WGS84 +axis=neu +wktext" -t_srs "+proj=latlong +datum=WGS84 +axis=enu +wktext" W:\02_Anwendungen\Klima_2010\leaflet\klimagutachten_2001_rheinau.geojson W:\02_Anwendungen\Klima_2010\leaflet\klimagutachten_wgs84.shp 
