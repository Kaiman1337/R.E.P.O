# R.E.P.O Save Manager

![R.E.P.O Save Manager](https://img.shields.io/badge/status-active-brightgreen)

R.E.P.O Save Manager is a lightweight Windows console application designed to **automatically backup and restore game save files** from a specified directory. It monitors save directories, copies updated files to a backup location, and restores saves when needed, ensuring your progress is always safely stored.

---

## Features

- **Automatic backup** of game saves from the user profile directory.
- **Restore saves** from backups if needed.
- Efficient **change detection** to copy only modified files or directories.
- Detailed **logging** of operations with color-coded console output.
- Safe multi-threaded logging using mutex.
- User-friendly console menu with options to update saves, restore saves, or exit.
- Periodic autosave checks with countdown and exit option.

---

## How It Works

- Source saves are read from the user's AppData LocalLow path:
    `%USERPROFILE%\AppData\LocalLow\semiwork\Repo\saves\`

- Backups are stored in the relative path:
    `.\SAVES\`

- Logs are written to:
    `.\logs\`

---

## Logging

- Log files are created inside the logs folder.
- Different log files for update and restore operations (`update_saves_log.txt`, `restore_saves_log.txt`).
- Console output is color-coded for info, warnings, and errors.
- The program compares timestamps of files and directories to detect changes and copies only new or updated saves.

---

## Requirements

- Windows OS (uses Windows API for file handling and console operations)
- C++17 compatible compiler
- Console capable of ANSI escape codes for colored output

---

## Usage

1. Run the executable `R.E.P.O Save Manager.exe`.
2. Select an option from the menu:  
- `1` to update (backup) saves.  
- `2` to restore saves from backup.  
- `E` to exit the program.
3. When in autosave mode, the program will periodically check for changes and update the backups automatically. Press `E` to exit.

---

## Structure

```
D:\R.E.P.O
│   R.E.P.O Save Manager.exe
│
├───logs
│       restore_saves_log.txt
│       update_saves_log.txt
│
└───SAVES
    ├───REPO_SAVE_2025_06_29_22_01_04
    │       REPO_SAVE_2025_06_29_22_01_04.es3
    │       REPO_SAVE_2025_06_29_22_01_04_BACKUP1.es3
    │       REPO_SAVE_2025_06_29_22_01_04_BACKUP10.es3
    │       REPO_SAVE_2025_06_29_22_01_04_BACKUP11.es3
    │       REPO_SAVE_2025_06_29_22_01_04_BACKUP12.es3
    │       REPO_SAVE_2025_06_29_22_01_04_BACKUP13.es3
    │       REPO_SAVE_2025_06_29_22_01_04_BACKUP14.es3
    │       REPO_SAVE_2025_06_29_22_01_04_BACKUP15.es3
    │       REPO_SAVE_2025_06_29_22_01_04_BACKUP16.es3
    │       REPO_SAVE_2025_06_29_22_01_04_BACKUP17.es3
    │       REPO_SAVE_2025_06_29_22_01_04_BACKUP2.es3
    │       REPO_SAVE_2025_06_29_22_01_04_BACKUP3.es3
    │       REPO_SAVE_2025_06_29_22_01_04_BACKUP4.es3
    │       REPO_SAVE_2025_06_29_22_01_04_BACKUP5.es3
    │       REPO_SAVE_2025_06_29_22_01_04_BACKUP6.es3
    │       REPO_SAVE_2025_06_29_22_01_04_BACKUP7.es3
    │       REPO_SAVE_2025_06_29_22_01_04_BACKUP8.es3
    │       REPO_SAVE_2025_06_29_22_01_04_BACKUP9.es3
    │
    ├───REPO_SAVE_2025_07_10_20_22_50
    │       REPO_SAVE_2025_07_10_20_22_50.es3
    │       REPO_SAVE_2025_07_10_20_22_50_BACKUP1.es3
    │       REPO_SAVE_2025_07_10_20_22_50_BACKUP10.es3
    │       REPO_SAVE_2025_07_10_20_22_50_BACKUP11.es3
    │       REPO_SAVE_2025_07_10_20_22_50_BACKUP12.es3
    │       REPO_SAVE_2025_07_10_20_22_50_BACKUP13.es3
    │       REPO_SAVE_2025_07_10_20_22_50_BACKUP14.es3
    │       REPO_SAVE_2025_07_10_20_22_50_BACKUP15.es3
    │       REPO_SAVE_2025_07_10_20_22_50_BACKUP16.es3
    │       REPO_SAVE_2025_07_10_20_22_50_BACKUP17.es3
    │       REPO_SAVE_2025_07_10_20_22_50_BACKUP18.es3
    │       REPO_SAVE_2025_07_10_20_22_50_BACKUP19.es3
    │       REPO_SAVE_2025_07_10_20_22_50_BACKUP2.es3
    │       REPO_SAVE_2025_07_10_20_22_50_BACKUP20.es3
    │       REPO_SAVE_2025_07_10_20_22_50_BACKUP21.es3
    │       REPO_SAVE_2025_07_10_20_22_50_BACKUP22.es3
    │       REPO_SAVE_2025_07_10_20_22_50_BACKUP23.es3
    │       REPO_SAVE_2025_07_10_20_22_50_BACKUP3.es3
    │       REPO_SAVE_2025_07_10_20_22_50_BACKUP4.es3
    │       REPO_SAVE_2025_07_10_20_22_50_BACKUP5.es3
    │       REPO_SAVE_2025_07_10_20_22_50_BACKUP6.es3
    │       REPO_SAVE_2025_07_10_20_22_50_BACKUP7.es3
    │       REPO_SAVE_2025_07_10_20_22_50_BACKUP8.es3
    │       REPO_SAVE_2025_07_10_20_22_50_BACKUP9.es3
    │
    └───REPO_SAVE_2025_07_11_14_26_43
            REPO_SAVE_2025_07_11_14_26_43.es3
            REPO_SAVE_2025_07_11_14_26_43_BACKUP1.es3
            REPO_SAVE_2025_07_11_14_26_43_BACKUP10.es3
            REPO_SAVE_2025_07_11_14_26_43_BACKUP11.es3
            REPO_SAVE_2025_07_11_14_26_43_BACKUP12.es3
            REPO_SAVE_2025_07_11_14_26_43_BACKUP13.es3
            REPO_SAVE_2025_07_11_14_26_43_BACKUP14.es3
            REPO_SAVE_2025_07_11_14_26_43_BACKUP15.es3
            REPO_SAVE_2025_07_11_14_26_43_BACKUP2.es3
            REPO_SAVE_2025_07_11_14_26_43_BACKUP3.es3
            REPO_SAVE_2025_07_11_14_26_43_BACKUP4.es3
            REPO_SAVE_2025_07_11_14_26_43_BACKUP5.es3
            REPO_SAVE_2025_07_11_14_26_43_BACKUP6.es3
            REPO_SAVE_2025_07_11_14_26_43_BACKUP7.es3
            REPO_SAVE_2025_07_11_14_26_43_BACKUP8.es3
            REPO_SAVE_2025_07_11_14_26_43_BACKUP9.es3
```
---