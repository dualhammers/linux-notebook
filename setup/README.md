# Linux Setup

Notes on my current linux setup how to get it set up how I want it.

## Current Build

### Distro

Elementary OS 5.0 Juno

### Shell

Fish

### File Manager

**GUI:** Files
**TUI:** NNN

### Terminal Editor

Micro

### Music Player

CMUS
GPodder

### Video Player

VLC

### Visual Tools

Blender
Krita
Glimpse
Ronin
KdenLive

### Screenshot tool

Flameshot

### Misc Applications

youtube-dl
EyeD3
Left
Sublime3
Calibre
RClone


## Configuration

### Custom Startup Applications

`gnome-session-properties`

#### Run a custom command at startup

`sh ~/.local/bin/COMMAND.sh`


### NNN

### Node

```
sudo npm install npm@latest -g
sudo npm cache clean -f
sudo npm install -g n
sudo npm i -g npm
sudo n stable
```

### EyeD3

```
pip install eyeD3
eyeD3 -a "Artist" -A "Album" -t "Track Title" song.mp3
eyeD3 song.mp3
```

```
#!/bin/bash
cmus-remote -C clear
cmus-remote -C "add ~/Music"
cmus-remote -C "update-cache -f"
```

### Copy image to clipboard

```
xclip -selection clipboard -t image/png -i example.png
```

#### Open as Sudo

```
alias N='sudo nnn -dHi'
```
Opening nnn with `Sudo nnn` will give you root prompt rather than user prompt.
    *cannot be used with SSH key by default*

### Use a .deb File

```
sudo dpkg -i filename.deb
```

### RClone 

#### Mounting Google Drive

`#!/bin/bash
rclone mount remote:/ ~/(FOLDERNAME)/ --vfs-cache-mode writes`

### Youtube-dl

```
sudo wget https://yt-dl.org/downloads/latest/youtube-dl -O /usr/local/bin/youtube-dl
sudo chmod a+rx /usr/local/bin/youtube-dl
```

**// Single**
`youtube-dl -x --audio-format mp3 https://www.youtube.com/watch?v=sfIls6LMAGE`

**// Playlist**
`youtube-dl --extract-audio --audio-format mp3 -o "%(title)s.%(ext)s" 'https://www.youtube.com/watch?v=5KpK7yhDRXE&list=PLfGibfZATlGq4e4UsUiPLs3asiOqysjei'`
