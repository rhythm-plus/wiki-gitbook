# Changelogs

## 1.2.4 - 2022-05-11

* Add low graphics mode that disables fever and hit effects
* Add customizable note and track color options
* Add song info in sheet detail popup
* Add like buttons in the song preview panel and result page
* Fix slow list loading and request failures under high load
* Fix indefinite loading when creating a song in the editor
* Fix background music mute toggle
* Other bug fixes

![](<../.gitbook/assets/image (2) (1).png>)

## 1.2.3 - 2022-04-27

* Redesigned filter bar, added key and difficulty filter, added option to sort by the average length of all the sheets in a song&#x20;
* Added average length, difficulty and key information to song list item&#x20;
* Added playlist sorting, searching and favorite functions - Added background dim slider - Added game volume slider&#x20;
* Fix menu page losing its state when navigating between pages&#x20;
* Bug fixes&#x20;

\---

* We have launched our official ko-fi page, become a supporter here [https://ko-fi.com/rhythmplus](https://ko-fi.com/rhythmplus) ❤
* We have launched our second domain [http://rhythmplus.io/](http://rhythmplus.io/) ! Vote in the polls channel to decide which should be our primary domain.&#x20;
* and... WE HAVE REACHED 1000 MEMBERS IN THE DISCORD SEVER 🎉 thank you and have fun!

## 1.2.2 - 2022-03-27

* the lobby list can now stay smooth when scrolling, no matter how many songs are loaded into the list
* a back to top button is added
* selected song will be highlight in the list
* new map list design to accommodate titles
* note judging now switched to time based instead of pixel based, this means no matter what speed you set, the accuracy would not be affected!

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

