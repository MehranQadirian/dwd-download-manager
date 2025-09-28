# 🚀 DWD: The Ultimate Download Manager 🚀

![DWD](https://img.shields.io/badge/DWD-v2.0.0-blue?style=flat-square&logo=python) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**DWD** is a powerful, feature-rich download manager for Linux, written in Python. It supports downloading regular files (e.g., MP3s) and YouTube videos with a sleek, colorful interface, advanced features, and unmatched flexibility. Whether you're downloading a single file or managing a queue of downloads, DWD has you covered! 😎

## ✨ Key Features
- **Parallel Downloads**: Download multiple files simultaneously using configurable threads (default: 3).
- **Multi-Part Downloading**: Split large files into parts for faster downloads (ideal for non-YouTube files with known sizes).
- **YouTube Support**: Download videos in your preferred quality (e.g., `best`, `720p`, `1080p`) using `yt-dlp`.
- **Interactive Menu**: User-friendly CLI menu for single downloads, batch downloads, or queue management.
- **Colorful Progress Bar**: Displays percentage, download speed, and estimated time remaining using the `rich` library.
- **Proxy/VPN Support**: Bypass geo-restrictions or network filters with proxy configuration.
- **Download Queue**: Add multiple URLs to a queue and process them sequentially.
- **File Integrity Check**: Verify downloaded files using SHA256 or MD5 hashes.
- **Resume Downloads**: Automatically resume interrupted downloads for both regular files and YouTube videos.
- **Notifications & Sounds**: Get desktop notifications and play a completion sound when downloads finish.
- **Detailed Logging**: Track download history and errors in `download.log`.
- **Rate Limiting**: Control download speed to manage bandwidth usage.
- **Retry Mechanism**: Automatically retry failed downloads with exponential backoff (default: 3 attempts).
- **File Information Display**: View detailed metadata (e.g., file size, type, YouTube video details) before downloading.

## 🛠️ Easy Installation (1 Minute!)
Follow these steps to get started with DWD on Ubuntu/Debian-based systems:

1. **Install Prerequisites**:
   ```bash
   sudo apt update
   sudo apt install wget mpg123 libnotify-bin
   pipx install yt-dlp requests rich
   ```

2. **Install DWD**:
   - Download the `dwd` script to your `~/Downloads` folder (or any preferred location).
   - Open a terminal in the download folder and run:
     ```bash
     sudo mv ~/Downloads/dwd /usr/local/bin/dwd
     sudo chmod +x /usr/local/bin/dwd
     ```

3. **Verify Installation**:
   - Ensure `/usr/local/bin` is in your `$PATH`:
     ```bash
     echo $PATH
     ```
     If not, add it:
     ```bash
     export PATH=$PATH:/usr/local/bin
     ```
     To make this permanent, add the above line to your `~/.bashrc` or `~/.zshrc`.

   - Check if the script is executable:
     ```bash
     ls -l /usr/local/bin/dwd
     ```

4. **Test DWD**:
   ```bash
   dwd --help
   ```

## 🚀 Usage
Run DWD in various modes depending on your needs:

### 1. Interactive Mode
Launch the interactive menu for a guided experience:
```bash
dwd --interactive
```
The menu allows you to:
- Download a single URL.
- Download multiple URLs from a file.
- Add URLs to a queue.
- Process the download queue.
- Exit the program.

### 2. Download a Single File
Download a file or YouTube video:
```bash
dwd <URL> --output-dir ~/Downloads
```
For YouTube videos with specific quality:
```bash
dwd <YouTube_URL> --youtube --quality 720p
```

### 3. Download Multiple Files
Download multiple URLs in parallel:
```bash
dwd <URL1> <URL2> <URL3> --threads 3
```

### 4. Download from a File
Provide a text file containing URLs (one per line):
```bash
dwd --input-file urls.txt --output-dir ~/Downloads
```

### 5. Queue Downloads
Add URLs to a queue and process them later:
```bash
dwd <URL1> <URL2> --queue
dwd --process-queue --output-dir ~/Downloads
```

### 6. Advanced Options
- **Multi-Part Download**:
  ```bash
  dwd <URL> --multi-part
  ```
- **Rate Limiting**:
  ```bash
  dwd <URL> --rate-limit 500k
  ```
- **Proxy Support**:
  ```bash
  dwd <URL> --proxy http://proxy:port
  ```
- **File Integrity Check**:
  ```bash
  dwd <URL> --hash-check <expected_hash> --hash-type sha256
  ```
- **Play Completion Sound**:
  ```bash
  dwd <URL> --sound
  ```

### Full Command Options
Run `dwd --help` to see all available options:
```bash
dwd --help
```

## 📋 Example Commands
- Download a YouTube video in 1080p with a completion sound:
  ```bash
  dwd https://www.youtube.com/watch?v=example --youtube --quality 1080p --sound
  ```
- Download a large file with multi-part downloading:
  ```bash
  dwd http://example.com/largefile.zip --multi-part --output-dir ~/Downloads
  ```
- Process a queue of URLs with a proxy:
  ```bash
  dwd <URL1> <URL2> --queue
  dwd --process-queue --proxy http://proxy:port
  ```

## 🐛 Troubleshooting
- **No sound on completion**: Ensure `mpg123` is installed (`sudo apt install mpg123`).
- **No notifications**: Install `libnotify-bin` (`sudo apt install libnotify-bin`).
- **YouTube download fails**: Update `yt-dlp` (`pipx upgrade yt-dlp`).
- **Permission issues**: Verify the script is executable (`chmod +x /usr/local/bin/dwd`).
- **Check logs**: View `download.log` in the working directory for detailed error messages.

## 📜 License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## 🙌 Contributing
Feel free to fork this repository, submit issues, or create pull requests to improve DWD! Let's make downloading even cooler! 🚀
