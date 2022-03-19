# Changelogs

## 1.2.0 - 2022-03-16

### Features&#x20;

* A brand new database structure that allows pagination, which will drastically improve the performance for the menu or lobby page&#x20;
* Creator name of a song will now be visible by default, but you have the option to stay anonymous and hide the name for any specific song you created&#x20;
* Ability to favourite a song is added&#x20;
* Ability to create and share playlists for a collection of songs&#x20;
* Ability to delete any song, sheet or playlist you made&#x20;
* Improved settings experience, you can now save settings without reloading&#x20;
* A new setting is added to mute background music by default Improvements&#x20;
* Key indicator is added for each track when the song is about to start&#x20;
* Added mouse support to game control&#x20;
* A more friendly notice for the Youtube ID field&#x20;
* Redesigned modal UI&#x20;
* Difficulty names will be correctly displayed&#x20;
* Improved editor onboarding&#x20;

### Bug fixes&#x20;

* Bug fix for the pausing exploit&#x20;
* Bug fix for the key remap modal&#x20;
* A few other bug fixes&#x20;

With the newly designed backend and database as the infrastructure, you can expect updates to come more often, our next big goal is to refactor the game engine, to eliminate lagging, improve the editing experience, and provide customisable skins, scroll directions etc, stay tuned!

## 1.1.0 - 2021-03-02 - [PR75](https://github.com/henryz00/Rhythm-Plus-Music-Game/pull/75)

### Added

* Refactor song list, improve sheet filter
* Redesign song select mobile list animations
* Add latest song list in recommend page
* Add smooth list height animation and transitions
* Set menu and studio page router keep-alive
* Add game over screen and effects
* Add UI, modal and fever sound effects
* New BGM added
* Dependency upgrades, update husky and webpack to v5

### Fixed

* Fix scrollbar
* Improve youtube loading experience
* Bug fixes

## 1.0.9 - 2021-01-06 - [PR63](https://github.com/henryz00/Rhythm-Plus-Music-Game/pull/38)

### Fixed

* Dependency upgrades
* Editor function updates
* cross-env problem on windows
* Refactor sort function
* Bug fixes

### Added

* Key remap feature
* Added playlists function
* Categorize songs to recommended, new and all

## 1.0.8 - 2020-10-02 - [PR38](https://github.com/henryz00/Rhythm-Plus-Music-Game/pull/38)

* Song preview
* Scrollbar
* Add service worker, PWA manifests, offline ability
* Update combo style and separate canvases
* Move big mp3 assets to google cloud storage
* Add firebase play doc
* Google analytics
* [Separate combo and judge](https://github.com/henryz00/Rhythm-Plus-Music-Game/pull/38/commits/237044cc6a8117117f28a346da7ac33e8f863e80)
* [Update mark judge style](https://github.com/henryz00/Rhythm-Plus-Music-Game/pull/38/commits/58dc8e3bd44f93fff001136a7506a35227d01d53)
* [Fix editor note visibility and hold note bug](https://github.com/henryz00/Rhythm-Plus-Music-Game/pull/38/commits/35c921c3d2e19ccb950dcfd7e254a9ddf6116e44)
* [Implemented tutorial](https://github.com/henryz00/Rhythm-Plus-Music-Game/pull/38/commits/332c35e97913303af587fd364a7bf4e396b21ba8)
* [Add song suggestion link, add repo link](https://github.com/henryz00/Rhythm-Plus-Music-Game/pull/38/commits/9032cc8be64defb0784461b1cf563f4a1d60e476)
* Bug fixes



## 1.0.6 - 2020-08-23 - [PR30](https://github.com/henryz00/Rhythm-Plus-Music-Game/pull/30)

* Add sentry for error logging and update GA
* Configure global Logger to replace console.log
* Redesign game note speed logic, add editor functions
* Add game progress bar and game resume countdown
* Add editor route before leave warning
* Refactor themes and visualizers, add star visualizer (new default theme)
* Update studio loading to chunk loading
* Redesign song tag logic
* Add tag filtering, song search and sort function
* Result page and profile card style update
* Fix pause menu bug, add icons, add sheet detail modal
* Implement youtube nocookies option
* Bug fixes

## 1.0.5 - 2020-06-11 - [PR14](https://github.com/henryz00/Rhythm-Plus-Music-Game/pull/14)

* User authentication logic update, default anonymous login
* Implement result uploading and display
* Game start logic update
* Refactor visualizer, making it pluggable and modular
* Implement sheet editor

