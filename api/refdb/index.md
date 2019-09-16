---
layout: default
menu_item: api
title: Refdb
description: Version 0.26.0
menu_item: api
return_to:
  "API Documentation Index": /api/
sections:
  "open": "#open"
  "#compress": "#compress"
---

## <a name="open"></a><span>Refdb.</span>open <span class="tags"><span class="async">Async</span><span class="experimental">Experimental</span></span>

```js
Refdb.open(repo).then(function(refdb) {
  // Use refdb
});
```

| Parameters | Type |   |
| --- | --- | --- |
| repo | [Repository](/api/repository/) | the repository |

| Returns |  |
| --- | --- |
| [Refdb](/api/refdb/) |  |

## <a name="compress"></a><span>Refdb#</span>compress <span class="tags"><span class="sync">Sync</span><span class="experimental">Experimental</span></span>

```js
var result = refdb.compress();
```

| Returns |  |
| --- | --- |
| Number |  |

