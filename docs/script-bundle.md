---
id: script-bundle
title: Adverse script bundle
sidebar_label: Adverse script tag
---

#### The `data-` params and their meaning

| Param               | Value type                     | Meaning                                                                                                  | Example                   |
|---------------------|--------------------------------|----------------------------------------------------------------------------------------------------------|---------------------------|
| data-zoneId         | A valid ID                     | The id of a zone, `zoneId` should be already available when you copy the script tag                      | data-zoneId="12ik3b"      |
| data-zone-id        | A valid ID                     | Alias of `data-zoneId`                                                                                   | data-zone-id="12ik3b"     |
| data-geo-state      | 2-char geo code (CA, AL...etc) | A geological state used in adgroup targeting.                                                            | data-geo-state="CA"       |
| data-ad-feed-count  | Integer Number                 | The number of ads rendered in a publisher's ad feed.                                                     | data-ad-feed-count="3"    |
| data-score-key      |          String                      |A special key used to optimize traffic, different keys will make the zone order differently depending on the source.|         data-score-key="A"                  |
| data-zone-load-cost | Real Number                 |                                                                                                          |                 data-zone-load-cost="0.123"          |
| data-manual-render  | true/false (default)           | Whethere you want the script tag to render automatically or you want to control where to render the ads. | data-manual-render="true" |

#### Manual render ads with `window.adverse`

Usually when using the bundle script with no `data-manual-render`, it will be in **automatic render mode**. That means the script tag will render the ads into its nearest parent HTML element. For example:

```
<div id="container">
  <script
    src="https://adverse.lincx.la/ad"
    data-zone-id="dg65mc"
    data-ad-feed-count="3"
  >
  </script>
</div>
```

When the ads data is loaded from server, it will become:
```
<div id="container">
  <div id="ad-1">ad 1</div>
  <div id="ad-2">ad 2</div>
  <div id="ad-3">ad 3</div>
  <script
    src="https://adverse.lincx.la/ad"
    data-zone-id="dg65mc"
    data-ad-feed-count="3"
  >
  </script>
</div>
```

When `data-manual-render="true"`, manual render is enabled. After the script tag has finished loading its content, a helper method is available: `window.adverse`

`window.adverse` method definition:
```
window.adverse(target, opts)
```

| Param  | Value                 | Meaning                                                                                                       |
|--------|-----------------------|---------------------------------------------------------------------------------------------------------------|
| target | A valid HTML DOM Node | The container target that you want your ads rendered into                                                     |
| opts   | Object                | Options for rendering, equivalent to the `data-` params. For example `data-geo-state` will be `opts.geoState` |

Example usage:

```
<div id="target">
  <script charset="utf-8" src="https://adverse.lincx.la/ad" id="target-script" data-zoneid="56hasmx"
    data-manual-render="true"></script>
  <script type="text/javascript">
    function init() {
      var opts = {};
      var target = document.getElementById('target');
      opts['apiUrl'] = '[](https://adverse.lincx.la/ad)'
      opts['zoneId'] = '56hasmx';
      window.adverse(target, opts)
    }
    init()
  </script>
  // Ads will be render here, appended to the "target" element
</div>

```
