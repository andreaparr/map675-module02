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

My next step was to create and _*index.html*_ file.

```echo "<!doctype html>" > index.html
git add index.html
```

I have created my _index.html_ by adding the basic Leaflet stylesheet and javascript used in Module01.  I used Google Maps to find Minneapolis and grabbed the lat/long from the URL```https://www.google.com/maps/place/Minneapolis,+MN/@44.970797,-93.331518,12z/data=!3m1!4b1!4m5!3m4!1s0x52b333909377bbbd:0x939fc9842f7aee07!8m2!3d44.977753!4d-93.2650108``` to populate the `options`. 