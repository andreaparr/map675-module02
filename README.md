# map675-module02
Minneapolis, apparently.
=======

Since we decided to go with Minneapolis, I just did a Google search for _Minneapolis GIS Data_.  Not too surprisingly, because I remember from my days at Transportation that Minnesota actually has that a law requiring all *Spatial Data*, at least at the government level, will be free and open.  The first item that caught my eye was _Neighborhoods_ data. 

I used `curl -LOk` to download the shapefiles and then ogr2ogr to convert to JSON files.  Here is a sample I used to make the Street_Centerline file more compact.
```
ogr2ogr -f "GeoJSON" center-lines.json Street_Centerline.shp -sql "select speed_lim, streetname from Street_Centerline"
```
I have created my _index.html_ by adding the basic Leaflet stylesheet and javascript used in Module01.  I used Google Maps to find Minneapolis and grabbed the lat/long from the URL```https://www.google.com/maps/place/Minneapolis,+MN/@44.970797,-93.331518,12z/data=!3m1!4b1!4m5!3m4!1s0x52b333909377bbbd:0x939fc9842f7aee07!8m2!3d44.977753!4d-93.2650108``` to populate the `options`. 

After adding the `L.GeoJSON` with the `drawMap` function, I realized I need to get some better layers.  Half of them are point layers with the `fires-reported-2012.json` overwhelming the map. 

Changed my layers to the following 
* County Boundaries of only surrounding counties
* fire-stations within ```limits  ogr2ogr -f "GeoJSON" -t_srs EPSG:4326 cb.json MNCounties_MNDOT.shp -sql "select * from MNCounties_MNDOT where COUNTY_NAM in ('Anoka', 'Dakota', 'Hennepin', 'Ramsey', 'Washington') "```
* add Water.json
* Neighborhoods goes unchanged
* transit-routes (bus routes) added by AP

Replaced Tile Layer.

AP Edits/Notes
* Removed the drawMap function because I thought it was redundant as the data is drawn on the GeoJSON Leaflet layers. It all still works. Kind of wish I hadn't done that though. 
* Added transit.json layer that includes bus routes. 
Need to deal with the transit layer that has info outside Minneapolis city limits - might restrict zoom bounds
* Simplified tile layer - still looking for a different labels only layer
* Tried to add tool tip to neighborhoods layer, but have not gotten that to work yet
* Added parks layer
* Set initial bounds
* Added info to legend





