# Fixes to transform MARC into a format accepted in Project Blacklight installations

```(bash)
$ zcat data.mrc.gz | catmandu convert -v MARC to JSON --array 1 --fix bl_rug01.fix --var source=Ghent > solr.json
```
