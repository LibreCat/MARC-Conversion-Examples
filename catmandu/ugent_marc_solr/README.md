# UGent MARC to Solr

Catmandu Fix scripts to convert MARC documents to Solr documents. This Catmandu Fix isn't executable without copying the Ghent University data processing environment. For instance, some Fixes like the `weave_by_id` are local implementations of Fixes

Converts a record like:

```(yaml)
---
_id: ser01:000000276
is_download: 'false'
is_zoomable: 'false'
items: '[{"department":"CA20","holding":"#33(1972)","barcode":"","button":{"loan":"N","color":"GREEN","show":"1","service":"REQUEST","msg_i18n":"depot","msg":"Request
  from depot","code":"CLOSED_STACK"},"is_closed_stack":"true","note":"","offline":"0","faculty":"UB","is_order_digital":"false","location":"BIB.P.000359/16BIS","type":"","DOCTYPE":"HOLDING","library":"BIB"}]'
merge:
  id: ser01:000000276
  rand16: 13
  rand2: 1
  rand32: 20
  rand4: 1
  rand8: 4
  source: ser01
  type: periodical
p_holding: '1972'
p_holding_txt: Print available for 1972
record:
- - FMT
  - ' '
  - ' '
  - _
  - SE
- - LDR
  - ' '
  - ' '
  - _
  - 00000nas a22      a 4500
- - '001'
  - ' '
  - ' '
  - _
  - '000000276'
- - '005'
  - ' '
  - ' '
  - _
  - '20150403133141.0'
- - '008'
  - ' '
  - ' '
  - _
  - 970601nuuuuuuuuxx^^^^^^^^^^^^^^^^^^|||^^
- - '035'
  - ' '
  - ' '
  - a
  - c:lvd:13111628
- - '035'
  - ' '
  - ' '
  - a
  - (ser01)BIB.P.000359
- - '040'
  - ' '
  - ' '
  - a
  - BE-GnUNI
- - '050'
  - ' '
  - ' '
  - a
  - AS2 .M57
- - '245'
  - ' '
  - ' '
  - a
  - 'Minerva :'
  - b
  - internationales Verzeichnis wissenschaftlicher Institutionen. Wissenschaftliche
    Gesellschaften.
- - '260'
  - ' '
  - ' '
  - a
  - 'Berlin :'
  - b
  - de Gruyter,
  - c
  - n.d.
- - '580'
  - ' '
  - ' '
  - a
  - 'Ten dele voortzetting van: Minerva: Jahrbuch der gelehrten Welt. Erste Abteilung:
    Forschungsinstitute, Observatorien, Bibliotheken, Archive, Museen, Kommissionen,
    Gesellschaften'
- - '852'
  - ' '
  - ' '
  - x
  - UB
  - b
  - CA20
  - c
  - BIB
  - j
  - BIB.P.000359/16BIS
  - a
  - '#33(1972)'
- - '920'
  - ' '
  - ' '
  - a
  - periodical
version: 2017-06-30T21:19:58Z
...
```

to

```(yaml)
---
_bag: data
_boost: 1
_id: ser01:000000276
access:
- print
all:
- c:lvd:13111628
- (ser01)BIB.P.000359
- '1972'
- 'Minerva : internationales Verzeichnis wissenschaftlicher Institutionen. Wissenschaftliche
  Gesellschaften.'
- 'Berlin : de Gruyter, n.d.'
- 'Ten dele voortzetting van: Minerva: Jahrbuch der gelehrten Welt. Erste Abteilung:
  Forschungsinstitute, Observatorien, Bibliotheken, Archive, Museen, Kommissionen,
  Gesellschaften'
- 'UB CA20 BIB BIB.P.000359/16BIS #33(1972)'
- periodical
- '000000276'
- BIB.P.000359/16BIS
fSYS: '000000276'
fXML: '<marc:record xmlns:marc="http://www.loc.gov/MARC21/slim"><marc:leader>00000nas
  a22      a 4500</marc:leader><marc:controlfield tag="001">000000276</marc:controlfield><marc:controlfield
  tag="005">20150403133141.0</marc:controlfield><marc:controlfield tag="008">970601nuuuuuuuuxx^^^^^^^^^^^^^^^^^^|||^^</marc:controlfield><marc:datafield
  tag="035" ind1=" " ind2=" "><marc:subfield code="a">c:lvd:13111628</marc:subfield></marc:datafield><marc:datafield
  tag="035" ind1=" " ind2=" "><marc:subfield code="a">(ser01)BIB.P.000359</marc:subfield></marc:datafield><marc:datafield
  tag="040" ind1=" " ind2=" "><marc:subfield code="a">BE-GnUNI</marc:subfield></marc:datafield><marc:datafield
  tag="050" ind1=" " ind2=" "><marc:subfield code="a">AS2 .M57</marc:subfield></marc:datafield><marc:datafield
  tag="245" ind1=" " ind2=" "><marc:subfield code="a">Minerva :</marc:subfield><marc:subfield
  code="b">internationales Verzeichnis wissenschaftlicher Institutionen. Wissenschaftliche
  Gesellschaften.</marc:subfield></marc:datafield><marc:datafield tag="260" ind1="
  " ind2=" "><marc:subfield code="a">Berlin :</marc:subfield><marc:subfield code="b">de
  Gruyter,</marc:subfield><marc:subfield code="c">n.d.</marc:subfield></marc:datafield><marc:datafield
  tag="580" ind1=" " ind2=" "><marc:subfield code="a">Ten dele voortzetting van: Minerva:
  Jahrbuch der gelehrten Welt. Erste Abteilung: Forschungsinstitute, Observatorien,
  Bibliotheken, Archive, Museen, Kommissionen, Gesellschaften</marc:subfield></marc:datafield><marc:datafield
  tag="852" ind1=" " ind2=" "><marc:subfield code="x">UB</marc:subfield><marc:subfield
  code="b">CA20</marc:subfield><marc:subfield code="c">BIB</marc:subfield><marc:subfield
  code="j">BIB.P.000359/16BIS</marc:subfield><marc:subfield code="a">#33(1972)</marc:subfield></marc:datafield><marc:datafield
  tag="920" ind1=" " ind2=" "><marc:subfield code="a">periodical</marc:subfield></marc:datafield></marc:record>'
faculty:
- UB
has_metadata_license: ODBL
id: ser01:000000276
is_deleted: 'false'
is_download: 'false'
is_hidden: 'false'
is_oai: 'true'
is_zoomable: 'false'
items: '[{"department":"CA20","holding":"#33(1972)","barcode":"","button":{"loan":"N","color":"GREEN","show":"1","service":"REQUEST","msg_i18n":"depot","msg":"Request
  from depot","code":"CLOSED_STACK"},"is_closed_stack":"true","note":"","offline":"0","faculty":"UB","is_order_digital":"false","location":"BIB.P.000359/16BIS","type":"","DOCTYPE":"HOLDING","library":"BIB"}]'
json: '{"version":"2017-06-30T21:19:58Z","p_holding_txt":"Print available for 1972","p_holding":"1972","host_publication":"Published
  in Berlin by de Gruyter<br>Print available for 1972","title":"Minerva : internationales
  Verzeichnis wissenschaftlicher Institutionen. Wissenschaftliche Gesellschaften"}'
lang: und
library:
- BIB
location:
- BIB.P.000359/16BIS
marc_display: '[{"title":"Minerva : internationales Verzeichnis wissenschaftlicher
  Institutionen. Wissenschaftliche Gesellschaften."},{"publisher":"Berlin : de Gruyter,
  n.d."},{"note":"Ten dele voortzetting van: Minerva: Jahrbuch der gelehrten Welt.
  Erste Abteilung: Forschungsinstitute, Observatorien, Bibliotheken, Archive, Museen,
  Kommissionen, Gesellschaften"}]'
rug01: '000000276'
ser01: '000000276'
set:
- all
source: ser01
sysctlnr:
- c:lvd:13111628
- (ser01)BIB.P.000359
title: 'Minerva : internationales Verzeichnis wissenschaftlicher Institutionen. Wissenschaftliche
  Gesellschaften'
title_short: Minerva
title_sort: minervainternationalesverzeichniswissenschaftliche
type: periodical
updated_at: 2015-04-03T11:31:41Z
year: '1972'
year_all:
- '1972'
...
```
