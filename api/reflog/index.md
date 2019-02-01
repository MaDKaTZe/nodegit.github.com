---
layout: default
menu_item: api
title: Reflog
description: Version 0.24.0
menu_item: api
return_to:
  "API Documentation Index": /api/
sections:
  "delete": "#delete"
  "read": "#read"
  "rename": "#rename"
  "#append": "#append"
  "#drop": "#drop"
  "#entryByIndex": "#entryByIndex"
  "#entrycount": "#entrycount"
  "#write": "#write"
---

## <a name="delete"></a><span>Reflog.</span>delete <span class="tags"><span class="sync">Sync</span><span class="experimental">Experimental</span></span>

```js
var result = Reflog.delete(repo, name);
```

| Parameters | Type |   |
| --- | --- | --- |
| repo | [Repository](/api/repository/) | the repository |
| name | String | the reflog to delete |

| Returns |  |
| --- | --- |
| Number |  0 or an error code |

## <a name="read"></a><span>Reflog.</span>read <span class="tags"><span class="async">Async</span><span class="experimental">Experimental</span></span>

```js
Reflog.read(repo, name).then(function(reflog) {
  // Use reflog
});
```

| Parameters | Type |   |
| --- | --- | --- |
| repo | [Repository](/api/repository/) | the repostiory |
| name | String | reference to look up |

| Returns |  |
| --- | --- |
| [Reflog](/api/reflog/) |  |

## <a name="rename"></a><span>Reflog.</span>rename <span class="tags"><span class="sync">Sync</span><span class="experimental">Experimental</span></span>

```js
var result = Reflog.rename(repo, old_name, name);
```

| Parameters | Type |   |
| --- | --- | --- |
| repo | [Repository](/api/repository/) | the repository |
| old_name | String | the old name of the reference |
| name | String | the new name of the reference |

| Returns |  |
| --- | --- |
| Number |  0 on success, GIT_EINVALIDSPEC or an error code |

## <a name="append"></a><span>Reflog#</span>append <span class="tags"><span class="sync">Sync</span><span class="experimental">Experimental</span></span>

```js
var result = reflog.append(id, committer, msg);
```

| Parameters | Type |
| --- | --- | --- |
| id | [Oid](/api/oid/) | the OID the reference is now pointing to |
| committer | [Signature](/api/signature/) | the signature of the committer |
| msg | String | the reflog message |

| Returns |  |
| --- | --- |
| Number |  0 or an error code |

## <a name="drop"></a><span>Reflog#</span>drop <span class="tags"><span class="sync">Sync</span><span class="experimental">Experimental</span></span>

```js
var result = reflog.drop(idx, rewrite_previous_entry);
```

| Parameters | Type |
| --- | --- | --- |
| idx | Number | the position of the entry to remove. Should be greater than or equal to 0 (zero) and less than `git_reflog_entrycount()`. |
| rewrite_previous_entry | Number | 1 to rewrite the history; 0 otherwise. |

| Returns |  |
| --- | --- |
| Number |  0 on success, GIT_ENOTFOUND if the entry doesn't exist
 or an error code. |

## <a name="entryByIndex"></a><span>Reflog#</span>entryByIndex <span class="tags"><span class="sync">Sync</span><span class="experimental">Experimental</span></span>

```js
var reflogEntry = reflog.entryByIndex(idx);
```

| Parameters | Type |
| --- | --- | --- |
| idx | Number | the position of the entry to lookup. Should be greater than or equal to 0 (zero) and less than `git_reflog_entrycount()`. |

| Returns |  |
| --- | --- |
| [ReflogEntry](/api/reflog_entry/) |  the entry; NULL if not found |

## <a name="entrycount"></a><span>Reflog#</span>entrycount <span class="tags"><span class="sync">Sync</span><span class="experimental">Experimental</span></span>

```js
var result = reflog.entrycount();
```

| Returns |  |
| --- | --- |
| Number |  the number of log entries |

## <a name="write"></a><span>Reflog#</span>write <span class="tags"><span class="async">Async</span><span class="experimental">Experimental</span></span>

```js
reflog.write().then(function(result) {
  // Use result
});
```

| Returns |  |
| --- | --- |
| Number |  0 or an error code |

