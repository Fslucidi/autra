# autra

Audio Transcription using Python: Setup on macOS

This README will help you configure your environment for audio transcription using Python, using Homebrew and ffmpeg.

Prerequisites:
Ensure you have Homebrew installed on your Mac to manage packages. Open your Terminal and install Homebrew by running the following command:

```
/bin/bash -c “$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)”
```
Configuration: Set up Homebrew in your shell environment with these commands:
```
echo >> ~/.zprofile
echo ‘eval “$(/opt/homebrew/bin/brew shellenv)”’ >> ~/.zprofile
eval “$(/opt/homebrew/bin/brew shellenv)”
```
Install ffmpeg: ffmpeg is essential for audio file manipulation. Install it using Homebrew:

```
brew install ffmpeg
which ffmpeg
which ffprobe
```
Environment Setup: Configure your PATH for easy access to installed binaries:
```
export PATH=”/opt/homebrew/bin:$PATH”
echo ‘export PATH=”/usr/local/bin:$PATH”’ >> ~/.zshrc
source ~/.zshrc
```
Transcription Methods: There are two methods to choose from for transcription:

# 1. Offline Transcription
This method uses local dictionaries and supports unlimited file sizes. First, install wget and download the language model:
```
brew install wget
wget –no-check-certificate https://alphacephei.com/vosk/models/vosk-model-it-0.22.zip -P ~/Downloads
```
After downloading, unzip the file and specify the model’s path in your Python script. Make sure your audio files are in WAV format. To convert other formats to WAV, use:
```
ffmpeg -i path/to/your/original/file path/to/your/converted/file.wav
```
# 2. Online Transcription
This method is simpler but not suitable for large files. For usage, simply change the path of the audio file in your script as needed and convert the files to the appropriate format:
```
ffmpeg -i path/to/your/original/file.mp3 path/to/your/converted/file.wav
```
Replace path/to/your/original/file and path/to/your/converted/file.wav with the actual paths to your audio files. This setup allows you to transcribe audio effectively using Python on macOS.

You can just select, copy, and paste this text into your README file. Adjust the specific paths and details as necessary for your project.
