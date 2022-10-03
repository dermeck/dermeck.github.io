# Donwload Youtube Videos

## Firefox Plugin
https://addons.mozilla.org/de/firefox/addon/easy-youtube-video-download/

## CLI Tool `youtube-dl`

```bash
# install
sudo curl -L https://yt-dl.org/downloads/latest/youtube-dl -o /usr/local/bin/youtube-dl
sudo chmod a+rx /usr/local/bin/youtube-dl
```


```bash
youtube-dl <url-to-video-or-playlist>
```

`/usr/bin/env: ‘python’: No such file or directory`

```bash
# find out if python is installed
whereis python3

# create symlink
sudo ln -s /usr/bin/python3 /usr/bin/python

# or install python3
sudo apt-get install python-is-python3
```


https://askubuntu.com/questions/942930/usr-bin-env-python-no-such-file-or-directory