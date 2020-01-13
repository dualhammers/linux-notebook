# Linux Setup and important notes

#### Distro: Elementary OS 5.0

#### File Manager: NNN
#### Open as Sudo
"If you are a sudoer, open a new instance of nnn from the built-in prompt with sudo nnn.

You can also have a short and sweet (but powerful) alias (which also works at the nnn prompt):

`alias N='sudo nnn -dHi'`"

Opening nnn with `Sudo nnn` will give you root prompt rather than user prompt.
    *cannot be used with SSH key by default*

#### Music Player: CMUS

#### GDrive: Rclone w/ Custom Command
`#!/bin/bash
rclone mount remote:/ ~/(FOLDERNAME)/ --vfs-cache-mode writes`

#### youtube-dl
`sudo -H pip install --upgrade youtube-dl`
`youtube-dl -x --audio-format mp3 URL`
