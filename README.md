# map675-module02
Minneapolis, apparently.

Since we decided to go with Minneapolis, I just did a Google search for _Minneapolis GIS Data_.  Not too surprisingly, because I remember from my days at Transportation that Minnesota actually has that a law requiring all *Spatial Data*, at least at the government level, will be free and open.  The first item that caught my eye was _Neighborhoods_ data. 

I used `curl -LOk` to download the shapefiles and then ogr2ogr to convert to JSON files.  
```
ogr2ogr -f "GeoJSON" center-lines.json Street_Centerline.shp -sql "select speed_lim, streetname from Street_Centerline"
```

The four shape files I have downloaded and converted are:
* center-lines.json
* fires-report-2012.json
* neighborhoods.json
* growth-centers.json