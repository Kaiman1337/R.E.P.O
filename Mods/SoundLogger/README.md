# SoundLogger.dll

## Overview

**SoundLogger.dll** is a simple mod plugin for Unity games using the BepInEx modding framework.  
It logs every sound played in the game, showing the audio clip name and sound type in the console or BepInEx log.

This is useful for debugging audio events or monitoring sounds during gameplay.

---

## Features

- Logs every sound played by patching the game's `Sound.Play()` method.
- Displays the audio clip name and sound type for each sound.
- Lightweight and easy to use.

---

## Installation

1. Ensure you have [BepInEx](https://docs.bepinex.dev/articles/user_guide/installation/index.html) installed for your game.
2. Copy the provided `SoundLogger.dll` file into the `BepInEx/plugins` folder of your game directory.

---

## Usage

- Launch the game normally.
- The mod will automatically initialize and patch the sound system.
- Sound events will be logged in the Unity console or the BepInEx log file.
- Logs will look like this:
    `[SoundLogger] Playing: <sound_name> | Type: <sound_type>`
    `[SoundLogger] [Enemy: <enemy_name>] Playing: <sound_name> | Type: <sound_type>`

---

## Notes

- No configuration needed.
- Works automatically when the DLL is present in the plugins folder.

---

## About

This mod is designed specifically for **R.E.P.O** to log sound information into the console.

---
