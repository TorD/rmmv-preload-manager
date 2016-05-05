# Preload Manager for RPG Maker MV
Version 2.0.0 of the Preload Manager plugin marks a complete rewrite with vastly better performance and handling of files. But not only that, it adds a lot of new features too! Let's take a look:

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
Both the audio and image cache limits can be configured via the plugin's Plugin Manager settings.