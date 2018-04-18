# map675-module02
Minneapolis, apparently.

Since we decided to go with Minneapolis, I just did a Google search for _Minneapolis GIS Data_.  Not too surprisingly, because I remember from my days at Transportation that Minnesota actually has that a law requiring all *Spatial Data*, at least at the government level, will be free and open.  The first item that caught my eye was _Neighborhoods_ data. 

```bash
curl LOk https://www.arcgis.com/sharing/rest/content/items/9927974f5d7443549b34abaa11810ed5/data
```
It may be because I love _File Geodatabases_:
```bash
unzip Neighborhoods-d67f042acef4454c851d8c7448b216f9_0-fgdb.zip -d Neighborhoods
```



