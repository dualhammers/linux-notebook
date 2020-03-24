# Linux Setup

Notes on my current linux setup how to get it set up how I want it.

## Current Build

### Distro

Manjaro 

### Shell

Fish

### File Manager

**GUI:** Thurnar
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

### Screenshot tool


### Misc Applications
XBkindKey
youtube-dl
EyeD3
Left
Sublime3
Calibre

### Website Toolchain
[MDBook](https://rust-lang.github.io/mdBook/index.html)
[Book-Summary](https://github.com/dvogt23/book-summary)


## Configuration

### Custom Startup Applications

`gnome-session-properties`

#### Run a custom command at startup

`sh ~/.local/bin/COMMAND.sh`

### Git
#### Switching Branches

`git switch name` if maintaining one orign, will try and create it if not extant
`git switch -c name origin/name` 
`git branch name` - creates a branch
`git checkout -b name` - checkouts a new branch
` git push -u origin branch_name` - Sets up tracking information during push to remote

### mdBook
`mdbook build` - build a book
`mdbook clean` - delete the generated book and any other artifacts
#### Book Summary
`book-summary -n ./SOURCEFOLDER --sort ENTRIES TO START WITH`

### Fish
#### Change Shell to Fish
`chsh -l`
`$ chsh -s full-path-to-shell`


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

#### Update Music Script
```
#!/bin/bash
cmus-remote -C clear
cmus-remote -C "add ~/Music"
cmus-remote -C "update-cache -f"
```
`chmod +x your-script.sh`
`:bind -f common u shell ~/path/to/your-script.sh`

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
`youtube-dl -x --audio-format mp3 https://www.youtube.com/watch?v=Np5oq9sHYz8`

**// Playlist**
`youtube-dl --extract-audio --audio-format mp3 -o "%(title)s.%(ext)s" 'https://www.youtube.com/watch?v=5KpK7yhDRXE&list=PLfGibfZATlGq4e4UsUiPLs3asiOqysjei'`

### XBindKey
#### Elecom Mouse Keys
- Right2: 12
- Forward: 9
- Backward: 8
- Fn1: 10
- Fn2: 11

## Tips and Trickss

### Creating a Launcher 

#### Manjaro
- Right click on desktop >> Create Launcher
`sudo mv Desktop/lancher.desktop /usr/share/applications`

### Formatting a drive to exFat
https://forum.manjaro.org/t/how-to-format-a-usb-stick-so-that-it-is-usable-on-manjaro-windows-and-macos/3972

### Create Sym Links
`rm -r ~/Folder`
`ln -s /data/location ~/folder`

### Managing Remote Drives

#### Mounting a remote drive for use as a regular drive
- `lsblk -a -o uuid,name,mountpoint`
- Add drive to `/etc/fstab`

