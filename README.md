# map675-module02
Minneapolis, apparently.

Since we decided to go with Minneapolis, I just did a Google search for _Minneapolis GIS Data_.  Not too surprisingly, because I remember from my days at Transportation that Minnesota actually has that a law requiring all *Spatial Data*, at least at the government level, will be free and open.  The first item that caught my eye was _Neighborhoods_ data. 

```bash
curl LOk https://www.arcgis.com/sharing/rest/content/items/9927974f5d7443549b34abaa11810ed5/data
```
It may be because I love _File Geodatabases_, or I'm the real [@FileGDB}](https://twitter.com/FileGDB "File Geodatabase"):
```bash
unzip Neighborhoods-d67f042acef4454c851d8c7448b216f9_0-fgdb.zip -d Neighborhoods
```

Then, I did the following and this was a first for me: 
```bash
git push --set-upstream origin ian_start
```


