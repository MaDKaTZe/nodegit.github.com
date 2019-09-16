---
layout: default
menu_item: api
title: Note
description: Version 0.26.0
menu_item: api
return_to:
  "API Documentation Index": /api/
sections:
  "commitCreate": "#commitCreate"
  "commitIteratorNew": "#commitIteratorNew"
  "commitRead": "#commitRead"
  "commitRemove": "#commitRemove"
  "create": "#create"
  "defaultRef": "#defaultRef"
  "foreach": "#foreach"
  "read": "#read"
  "remove": "#remove"
  "#author": "#author"
  "#committer": "#committer"
  "#id": "#id"
  "#message": "#message"
---

## <a name="commitCreate"></a><span>Note.</span>commitCreate <span class="tags"><span class="sync">Sync</span></span>

```js
var oid = Note.commitCreate(repo, parent, author, committer, oid, note, allow_note_overwrite);
```

| Parameters | Type |   |
| --- | --- | --- |
| repo | [Repository](/api/repository/) | repository where the note will live |
| parent | [Commit](/api/commit/) | Pointer to parent note or NULL if this shall start a new notes tree |
| author | [Signature](/api/signature/) | signature of the notes commit author |
| committer | [Signature](/api/signature/) | signature of the notes commit committer |
| oid | [Oid](/api/oid/) | OID of the git object to decorate |
| note | String | Content of the note to add for object oid |
| allow_note_overwrite | Number | Overwrite existing note |

| Returns |  |
| --- | --- |
| [Oid](/api/oid/) | a point to the id of a note blob (optional) |

## <a name="commitIteratorNew"></a><span>Note.</span>commitIteratorNew <span class="tags"><span class="async">Async</span></span>

```js
Note.commitIteratorNew(notes_commit).then(function(noteIterator) {
  // Use noteIterator
});
```

| Parameters | Type |   |
| --- | --- | --- |
| notes_commit | [Commit](/api/commit/) | a pointer to the notes commit object |

| Returns |  |
| --- | --- |
| [NoteIterator](/api/note_iterator/) |  |

## <a name="commitRead"></a><span>Note.</span>commitRead <span class="tags"><span class="async">Async</span></span>

```js
Note.commitRead(repo, notes_commit, oid).then(function(note) {
  // Use note
});
```

| Parameters | Type |   |
| --- | --- | --- |
| repo | [Repository](/api/repository/) | repository where to look up the note |
| notes_commit | [Commit](/api/commit/) | a pointer to the notes commit object |
| oid | [Oid](/api/oid/) | OID of the git object to read the note from |

| Returns |  |
| --- | --- |
| [Note](/api/note/) |  |

## <a name="commitRemove"></a><span>Note.</span>commitRemove <span class="tags"><span class="async">Async</span></span>

```js
Note.commitRemove(repo, notes_commit, author, committer, oid).then(function(oid) {
  // Use oid
});
```

| Parameters | Type |   |
| --- | --- | --- |
| repo | [Repository](/api/repository/) | repository where the note lives |
| notes_commit | [Commit](/api/commit/) | a pointer to the notes commit object |
| author | [Signature](/api/signature/) | signature of the notes commit author |
| committer | [Signature](/api/signature/) | signature of the notes commit committer |
| oid | [Oid](/api/oid/) | OID of the git object to remove the note from |

| Returns |  |
| --- | --- |
| [Oid](/api/oid/) |  |

## <a name="create"></a><span>Note.</span>create <span class="tags"><span class="async">Async</span></span>

```js
Note.create(repo, notes_ref, author, committer, oid, note, force).then(function(oid) {
  // Use oid
});
```

| Parameters | Type |   |
| --- | --- | --- |
| repo | [Repository](/api/repository/) | repository where to store the note |
| notes_ref | String | canonical name of the reference to use (optional); defaults to "refs/notes/commits" |
| author | [Signature](/api/signature/) | signature of the notes commit author |
| committer | [Signature](/api/signature/) | signature of the notes commit committer |
| oid | [Oid](/api/oid/) | OID of the git object to decorate |
| note | String | Content of the note to add for object oid |
| force | Number | Overwrite existing note |

| Returns |  |
| --- | --- |
| [Oid](/api/oid/) |  |

## <a name="defaultRef"></a><span>Note.</span>defaultRef <span class="tags"><span class="async">Async</span></span>

```js
Note.defaultRef(repo).then(function(buf) {
  // Use buf
});
```

| Parameters | Type |   |
| --- | --- | --- |
| repo | [Repository](/api/repository/) | The Git repository |

| Returns |  |
| --- | --- |
| [Buf](/api/buf/) | buffer in which to store the name of the default notes reference |

## <a name="foreach"></a><span>Note.</span>foreach <span class="tags"><span class="async">Async</span></span>

```js
Note.foreach(repo, notes_ref, note_cb, payload).then(function(result) {
  // Use result
});
```

| Parameters | Type |   |
| --- | --- | --- |
| repo | [Repository](/api/repository/) | Repository where to find the notes. |
| notes_ref | String | Reference to read from (optional); defaults to "refs/notes/commits". |
| note_cb | NoteForeachCb | Callback to invoke per found annotation. Return non-zero to stop looping. |
| payload | Void | Extra parameter to callback function. |

| Returns |  |
| --- | --- |
| Number |  0 on success, non-zero callback return value, or error code |

## <a name="read"></a><span>Note.</span>read <span class="tags"><span class="async">Async</span></span>

```js
Note.read(repo, notes_ref, oid).then(function(note) {
  // Use note
});
```

| Parameters | Type |   |
| --- | --- | --- |
| repo | [Repository](/api/repository/) | repository where to look up the note |
| notes_ref | String | canonical name of the reference to use (optional); defaults to "refs/notes/commits" |
| oid | [Oid](/api/oid/) | OID of the git object to read the note from |

| Returns |  |
| --- | --- |
| [Note](/api/note/) |  |

## <a name="remove"></a><span>Note.</span>remove <span class="tags"><span class="async">Async</span></span>

```js
Note.remove(repo, notes_ref, author, committer, oid).then(function(result) {
  // Use result
});
```

| Parameters | Type |   |
| --- | --- | --- |
| repo | [Repository](/api/repository/) | repository where the note lives |
| notes_ref | String | canonical name of the reference to use (optional); defaults to "refs/notes/commits" |
| author | [Signature](/api/signature/) | signature of the notes commit author |
| committer | [Signature](/api/signature/) | signature of the notes commit committer |
| oid | [Oid](/api/oid/) | OID of the git object to remove the note from |

| Returns |  |
| --- | --- |
| Number |  0 or an error code |

## <a name="author"></a><span>Note#</span>author <span class="tags"><span class="sync">Sync</span></span>

```js
var signature = note.author();
```

| Returns |  |
| --- | --- |
| [Signature](/api/signature/) |  the author |

## <a name="committer"></a><span>Note#</span>committer <span class="tags"><span class="sync">Sync</span></span>

```js
var signature = note.committer();
```

| Returns |  |
| --- | --- |
| [Signature](/api/signature/) |  the committer |

## <a name="id"></a><span>Note#</span>id <span class="tags"><span class="sync">Sync</span></span>

```js
var oid = note.id();
```

| Returns |  |
| --- | --- |
| [Oid](/api/oid/) |  the note object's id |

## <a name="message"></a><span>Note#</span>message <span class="tags"><span class="sync">Sync</span></span>

```js
var string = note.message();
```

| Returns |  |
| --- | --- |
| String |  the note message |

