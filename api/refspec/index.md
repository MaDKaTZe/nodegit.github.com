---
layout: default
menu_item: api
title: Refspec
description: Version 0.26.1
menu_item: api
return_to:
  "API Documentation Index": /api/
sections:
  "parse": "#parse"
  "#direction": "#direction"
  "#dst": "#dst"
  "#dstMatches": "#dstMatches"
  "#force": "#force"
  "#src": "#src"
  "#srcMatches": "#srcMatches"
  "#string": "#string"
---

## <a name="parse"></a><span>Refspec.</span>parse <span class="tags"><span class="async">Async</span><span class="experimental">Experimental</span></span>

```js
Refspec.parse(input, is_fetch).then(function(refspec) {
  // Use refspec
});
```

| Parameters | Type |   |
| --- | --- | --- |
| input | String | the refspec string |
| is_fetch | Number | is this a refspec for a fetch |

| Returns |  |
| --- | --- |
| [Refspec](/api/refspec/) | hold the refspec handle |

## <a name="direction"></a><span>Refspec#</span>direction <span class="tags"><span class="sync">Sync</span><span class="experimental">Experimental</span></span>

```js
var result = refspec.direction();
```

| Returns |  |
| --- | --- |
| Number |  GIT_DIRECTION_FETCH or GIT_DIRECTION_PUSH |

## <a name="dst"></a><span>Refspec#</span>dst <span class="tags"><span class="sync">Sync</span><span class="experimental">Experimental</span></span>

```js
var string = refspec.dst();
```

| Returns |  |
| --- | --- |
| String |  the refspec's destination specifier |

## <a name="dstMatches"></a><span>Refspec#</span>dstMatches <span class="tags"><span class="sync">Sync</span><span class="experimental">Experimental</span></span>

```js
var result = refspec.dstMatches(refname);
```

| Parameters | Type |
| --- | --- | --- |
| refname | String | the name of the reference to check |

| Returns |  |
| --- | --- |
| Number |  1 if the refspec matches, 0 otherwise |

## <a name="force"></a><span>Refspec#</span>force <span class="tags"><span class="sync">Sync</span><span class="experimental">Experimental</span></span>

```js
var result = refspec.force();
```

| Returns |  |
| --- | --- |
| Number |  1 if force update has been set, 0 otherwise |

## <a name="src"></a><span>Refspec#</span>src <span class="tags"><span class="sync">Sync</span><span class="experimental">Experimental</span></span>

```js
var string = refspec.src();
```

| Returns |  |
| --- | --- |
| String |  the refspec's source specifier |

## <a name="srcMatches"></a><span>Refspec#</span>srcMatches <span class="tags"><span class="sync">Sync</span><span class="experimental">Experimental</span></span>

```js
var result = refspec.srcMatches(refname);
```

| Parameters | Type |
| --- | --- | --- |
| refname | String | the name of the reference to check |

| Returns |  |
| --- | --- |
| Number |  1 if the refspec matches, 0 otherwise |

## <a name="string"></a><span>Refspec#</span>string <span class="tags"><span class="sync">Sync</span><span class="experimental">Experimental</span></span>

```js
var string = refspec.string();
```

| Returns |  |
| --- | --- |
| String |  |

