---
description: Proposed to migrate database to SQL
---

# Proposed Database

## Proposed Changes

We propose to migrate the current firestore database into SQL format.

To implement the change, we need to consider:

* Normalize JSON objects in the current database \(e.g. put _results_ into separate table _score_\)
* **How to index items** 
  * firebase id is 20 base-64 characters
  * SQL id is incrementable int
  * prefer firebase id format or MongoDB object id format, can be used in URL like now
* Add linking tables for playlists, tags etc
* How to store user settings \(tables or JSON string, currently prefer the latter\)
* How to calculate user exp and track user exp changelog \(separate _exp-changelog_ table\)
* How to store sheet \(currently consider store zipped binary\)
* How to keep track of changes in sheet and song info \(separate _history_ table\)

We also plan to add the following new changes:

* Separate _songs_ and _sheets_ further, by implementing a new table called _packs_
  * Currently, when a user creates a song, anyone can create any number of sheets inside that song, which is not good if people want a separate song space for their own sheets. They have to create another exact same song again, causing duplicates.
  * With the introduction of packs, any user can create any number of packs for the same song, but they can customize the title and thumbnail for that pack. They have full control over the sheets inside the pack, they can create different level of sheets in the pack, and even invite others to edit in the future if possible.
  * Now, when user wants to create a song, they can first search for the song library, if found, they can create a pack, having the option to customize the title or just use the song's default ones. If the song does not exist, they can create a song. A song only contains basic info like youtube id, title, artist, thumbnail and subtitle. Once created, this info should not be changeable, we should warn the user about this when saving.
* Add _ratings_ for the _packs_
  * 1-5 scale, so that we can rank packs by ratings



