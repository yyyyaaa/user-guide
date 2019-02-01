---
id: creative-target-url
title: Creative target URL macros
sidebar_label: Creative target URL macros
---

An example of creative target URL macros:

```
http://tracking.com?aff_click_id={{adverseClickId}}
```

When that URL is clicked, the {{adverseClickId}} variable is replaced with an unique value, for example **cjrlxwohg0000q9pppznx9q1v**.

```
http://tracking.com?aff_click_id=cjrlxwohg0000q9pppznx9q1v
```

Available variables are:

- `geoState` - example "NY"
- `scoreKey` - zone score key from the client script data atttribute `data-score-key="rich"`
- `timestamp` - visitor local timestamp, example `2019-02-01T15:00:33+03:00`
- `utcHour` - for example `12`
-  `visitorHour` - for example `15`
- `zoneId` - unique zone identificator

by default `adverseClickId={{adverseClickId}}` added to the target URL


