# 🚀 DWD: The Ultimate Download Manager 🚀

![DWD](https://img.shields.io/badge/DWD-v1.0-blue?style=flat-square&logo=python) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**DWD** is a powerful and cool download tool for Linux written in Python. It can download regular files (like MP3) and YouTube videos with colorful progress bar, high speed, and professional features. 😎

## ✨ Key Features
- **Parallel Download**: Download multiple files at the same time (up to 3 threads, configurable).
- **YouTube Support**: Download videos in the desired quality (like 720p) with `yt-dlp`.
- **Attractive progress bar**: Show percentage, download speed, and remaining time with `rich`.
- **Proxy/VPN support**: Download from filtered regions.
- **Notifications and sounds**: Desktop notification and download completion sound.
- **Logging**: Download history in `download.log`.
- **Resume incomplete downloads**: Interrupted? Resume again!

## 🛠️ Easy installation (1 minute!)
For immediate use:
1. **Install prerequisites** (on Ubuntu/Debian):
```bash
sudo apt update
```
```bash
sudo apt install wget mpg123 libnotify-bin
```
```bash
pipx install yt-dlp requests rich
```
# How to install this product
  **Go to the Downloads folder where dwd was downloaded.
    Then open a terminal in the same folder and run the following commands.**
  ```bash
  sudo mv ~/Downloads/dwd /usr/local/bin/dwd
  ```
  ```bash
  sudo chmod +x /usr/local/bin/dwd
  ```

# Help : ```bash dwd --help ```

# Check if /usr/local/bin is in $PATH:
  ```bash
  echo $PATH
  ```
**If not, add it:**
```bash
export PATH=$PATH:/usr/local/bin
```
**Verify the file is executable:**
```bash
ls -l /usr/local/bin/dwd
```
