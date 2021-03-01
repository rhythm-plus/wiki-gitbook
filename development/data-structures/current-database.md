---
description: Firestore structure
---

# Current Database

## Current Tables

{% hint style="info" %}
The current database is stored inside firebase firestore, id cloud be document index.

Firestore is similar to mongoDB, but it has collections, which is essetially another document inside a document, that can be queried individually.
{% endhint %}

### Users

* **id** varchar \[pk\]
* **displayName** varchar
* **dateCreated** timestamp
* **dateUpdated** timestamp
* **photoUrl** varchar
* **isAnonymous** boolean
* **exp** integer
* **appearanceSt** // apperance settings
  * **blur** boolean
  * **syncYoutube** boolean
  * **theme** string
  * **visualizer** string
  * **options** json // theme options json
* **gameSt** // default game settings
  * **blur** boolean
  * **fps** boolean
  * **noteSpeed** float
  * **perspective** boolean
  * **vibrate** boolean
* **preference**
  * **keyMap**
    * \[key string\]:\[mapped key string\]
    * e.g: a:z

#### Collections

* **exp-changelog**
  * **dateCreated**
  * **expAdded** int
  * **expBefore** int
  * **type** varchar // game\_result
  * **detail** //flexible json
    * playId
    * resultId
    * sheetId
    * songId

### Songs

* **id**: varchar \[pk\]
* **artist**: varchar
* **createdBy**: varchar // ref user.id
* **dateCreated**: timestamp
* **dateUpdated**: timestamp
* **image**: varchar // image url, if not present, use youtube thumbnail 
* **srcMode**: varchar // youtube or url
* **title**: varchar
* **subtitle**: varchar
* **url**: varchar
* **visibility**: varchar // public, private, unlisted
* **youtubeId**: varchar
* **tags**: array, contain tag string

#### Collections

* history \[document in the same format as songs\]

### Sheets

* **id** varchar \[pk\]
* **createdBy** varchar // ref user.id
* **songId** varchar // ref song.id
* **dateCreated** timestamp
* **dateUpdated** timestamp
* **visibility** varchar // public, private, unlisted
* **startAt** float4
* **endAt** float4
* **keys** int
* **length** float4
* **noteCount** int
* **visualizerName** varchar
* **sheet** varchar // JSON OBJECT

{% hint style="info" %}
Below options defaults to null, but if present, it will override song's param
{% endhint %}

* **image** varchar
* **srcMode** varchar // "youtube" or "url"
* **title** varchar 
* **subtitle** varchar
* **url** varchar
* **youtubeId** varchar

#### Collections

* **history** \[document in the same format as sheets\]

### Tags

* **id** varchar // the tag itself
* **dateCreated** timestamp
* **dateUpdated** timestamp
* **createdBy** varchar // ref user.id
* **tag** varchar

### Results

* **id** varchar \[pk\]
* **uid** varchar // ref user.id ! should change to **createdBy**
* **dateCreated** timestamp
* **expAdded** int // experience added
* **expBefore** int // user's exp before the result
* **isFullCombo** boolean
* **playId** varchar
* **rank** varchar // S+, S, A, B, C, D, F
* **visibility** varchar // public, private, unlisted
* **sheetId** varchar
* **songId** varchar
* **result**
  * **combo** int
  * **maxCombo** int
  * **percentage** float
  * **score** float
  * **totalHitNotes** int
  * **totalPercentage** float
  * **marks**
    * **perfect** int
    * **good** int
    * **offbeat** int
    * **miss** int

### Plays

{% hint style="info" %}
Records when user click the start song button
{% endhint %}

* **id** varchar \[pk\]
* **createdBy** varchar // ref user.id
* **dateCreated** timestamp
* **dateUpdated** timestamp
* **isAuthed** boolean // is player logged in
* **status** varchar // started, finished, playing, exited, game-over, closed, tutorial-ends
* **sheetId** varchar
* **songId** varchar
* **resultId** varchar // if game finished, otherwise null
* **result** \[same as the one in results\] // if game exited, tutorial-ends or closed, otherwise null
* **visibility** varchar // public, private, unlisted

### Playlists

* **id** varchar \[pk\]
* **createdBy** varchar // ref user.id
* **items** array of songId
* **visibility** varchar // public, private, unlisted

## DBML File

With minor SQL revision

```text
Table users as U {
  id varchar [pk, increment] // auto-increment
  displayName varchar
  dateCreated timestamp
  dateUpdated timestamp
  photoUrl varchar
  isAnonymous boolean
  preferences varchar // TODO JSON OBJECT
}

Table songs {
  id varchar [pk]
  artist varchar
  createdBy varchar // ref user.id
  dateCreated timestamp
  dateUpdated timestamp
  image varchar
  srcMode varchar // youtube or url
  title varchar
  subtitle varchar
  url varchar
  visibility varchar // public, private, unlisted
  youtubeId varchar
 }
 
// > many-to-one; < one-to-many; - one-to-one
Ref: songs.createdBy > U.id
 
Table sheets {
  id varchar [pk]
  createdBy varchar // ref user.id
  songId varchar // ref song.id
  dateCreated timestamp
  dateUpdated timestamp
  visibility varchar // public, private, unlisted
  startAt float4
  endAt float4
  keys int
  length float4
  noteCount int
  visualizerName varchar
  sheet varchar // TODO JSON OBJECT
  // below options default to null,
  // but if present, can override songs param
  image varchar
  srcMode varchar // youtube or url
  title varchar 
  subtitle varchar
  url varchar
  youtubeId varchar
}

Ref: sheets.createdBy > U.id
Ref: sheets.songId > songs.id



Table tags {
  id int [pk, increment]
  dateCreated timestamp
  dateUpdated timestamp
  createdBy varchar // ref user.id
  tag varchar
}

Table songTags {
  id int [pk, increment]
  tagId int
  songId int
}

Ref: songTags.songId > songs.id
Ref: songTags.tagId > tags.id




Table results {
  id varchar [pk]
  createdBy varchar // ref user.id
  dateCreated timestamp
  expAdded int // experience added
  expBefore int // user's exp before the result
  isFullCombo boolean
  playId varchar
  rank varchar // S+, S, A, B, C, D, F
  visibility varchar // public, private, unlisted
  result varchar // TODO JSON OBJECT
  sheetId varchar
  songId varchar
 }
 
Ref: results.songId > songs.id
Ref: results.sheetId > sheets.id
Ref: results.createdBy > U.id


Table plays {
  id varchar [pk]
  createdBy varchar // ref user.id
  dateCreated timestamp
  dateUpdated timestamp
  isAuthed boolean // is player logged in
  status varchar // started, finished, playing, exited, game-over, closed, tutorial-ends
  sheetId varchar
  songId varchar
  resultId varchar // if game finished, otherwise null
  result varchar // if game exited, tutorial-ends or closed, TODO JSON OBJECT
  visibility varchar // public, private, unlisted
 }
 
Ref: plays.songId > songs.id
Ref: plays.sheetId > sheets.id
Ref: plays.createdBy > U.id
Ref: plays.resultId > results.id
Ref: results.playId > plays.id
 

Table playlists {
  id varchar [pk]
  createdBy varchar // ref user.id
  dateCreated timestamp
  dateUpdated timestamp
  title varchar
  descrption varchar
  visibility varchar // public, private, unlisted
}
 
 
Table playlistSongs {
  id int [pk, increment]
  dateCreated timestamp
  dateUpdated timestamp
  createdBy varchar
  playlistId int
  songId int
}
 
Ref: playlistSongs.songId > songs.id
Ref: playlistSongs.playlistId > playlists.id
Ref: playlistSongs.createdBy > U.id
 
 
 
```

