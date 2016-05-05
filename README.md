# Preload Manager for RPG Maker MV
Version 2.0.0 of the Preload Manager plugin marks a complete rewrite with vastly better performance and handling of files. But not only that, it adds a lot of new features too!

## What does it do?
The Preload Manager preloads the assets used in scenes (startup, maps and battles) before the scenes are started. By default many images added in events, as well as sound effects and animations, have a delay the first time they are played. This is because they're loaded on-demand that first time, which does not look nor feel good for the player.

Preloading assets up front is what game engines usually do; we're all used to seeing some loading screens. When playing a game locally, the loading times are barely increased with this plugin. When played from a server, the loading times will be far longer, but the experience once the maps start will be much much better too.

# How to install
1. Click this link: https://raw.githubusercontent.com/TorD/rmmv-preload-manager/2.0.0-rc1/TDDP_PreloadManager.js
2. Hit CMD + S (CTRL + S on Windows) and save the file in your project's `js/plugins/` folder.

# Features
## Smart cache layer
Provides its own cache layer between MV's default image cache and the filesystem. MV's default Bitmap cache links to the data objects cached by the plugin, so memory is not increased.

Audio is also cached in memory, which is entirely new and not something MV does by default! This *vastly* increases the playback responsiveness of audio, with the only exception being BGM's on Android Chrome, which cannot handle this at this time.

## Preload files or entire folders on game start
You can (rather easily) tell the plugin to preload both individual files or entire folders (and their subfolders!) on game start.

## Configurable memory limits
Both the audio and image cache limits can be configured via the plugin's Plugin Manager settings. When these are reached, the oldest and least used assets will be purged from the cache to free up space for new items on load.

__Important:__ The plugin will not deny assets to be loaded if your maps or battles contain enough new assets on them to exceed these limits on their own. So the limits are not hard limits, but rather cache limits which the plugin will do its best to adhere to, but it won't stop you from exceeding them by your own hands.

A future addon is planned to make it easier to see how much memory a given map or battle takes up, so you can plan your games better.

## Extensibility
The plugin now has fully documented source code _and_ public interfaces other plugins can use to listen to preload events, check progress, and more.

## Planned addons
With the extensibility in mind, I have plans for at least two future addons plugins:
1. Preload Scene - Show progress bars and images while things are preloading.
2. Memory Monitor - Monitor just how much memory your maps and battles take up in the asset cache while you're testing your game with GUI element.
