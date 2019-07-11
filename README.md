# YouTube MP3 Downloader
A python tool that let you download and convert to mp3 a YouTube video

## Install
Use the package manager [pip](https://pip.pypa.io/en/stable/) to install youtube-dl.  
```bash
pip install youtube-dl
```
Then you will need to install ffmpeg, for linux based machines, you will just need to use your console.  
Example Ubuntu:  
```bash
sudo apt update
sudo apt install ffmpeg
```
On windows ones instead, you will need to download the [last build](https://ffmpeg.org/download.html#build-windows)  
At this point copy the 3 files you can find on bin folder, and paste them in the main Python's scripts folder  
![alt text](https://i.ibb.co/gmJZ1zC/aaaaaa.png)

## Info
youtube-dl will be used to download the video from youtube  
ffmpeg will convert them to mp3

## Setup
In the first part of the code, we will need to import unicode_literals from __future__ and import youtube_dl  
We want to make the person using the tool to choose the youtube video's link directly in the console, and not in the code, we will make that by declaring a variable named link, which will take the user's input when the tool is runned.
```python
from __future__ import unicode_literals
import youtube_dl
print("Insert the link")
link = input ("")
```
![alt text](https://i.ibb.co/Y2GqT3Q/Cattura.png)

## YTDL Options
We need to specify all the options for the video, like the quality, the codec, etc...  
We will download our video with the maximum quality and in a mp3 format  
```python
ydl_opts = {
    'format': 'bestaudio/best',
    'postprocessors': [{
        'key': 'FFmpegExtractAudio',
        'preferredcodec': 'mp3',
        'preferredquality': '320',
    }],
}
```

## Download and convert
```python
with youtube_dl.YoutubeDL(ydl_opts) as ydl:
    ydl.download([link])
```

## Code
So our code will look like:
```python
from __future__ import unicode_literals
import youtube_dl
print("Insert the link")
link = input ("")

ydl_opts = {
    'format': 'bestaudio/best',
    'postprocessors': [{
        'key': 'FFmpegExtractAudio',
        'preferredcodec': 'mp3',
        'preferredquality': '320',
    }],
}

with youtube_dl.YoutubeDL(ydl_opts) as ydl:
    ydl.download([link])
```

For any issue join this discord server: https://discord.gg/BgjwgWx  
Or contact me on discord: Mental#1424
