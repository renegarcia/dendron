---
id: cfm4n435nhmnbubcoi8a356
title: Code Snippets
desc: ''
updated: 1689264389972
created: 1689264140093
---

# How to set gnome wallpaper using the command line

```sh
gsettings set org.gnome.desktop.background picture-uri file:///path/to/image
```


## Setting bing's image of the day as wallpaper


```sh
wget -O /tmp/wallpaper.jpg "http://www.bing.com/$(wget -q -O- https://binged.it/2ZButYc | sed -e 's/<[^>]*>//g' | cut -d / -f2 | cut -d \& -f1)"

gsettings set org.gnome.desktop.background picture-uri file:////tmp/wallpaper.jpg

```

__Source:__ [https://linuxconfig.org/set-wallpaper-on-ubuntu-20-04-using-command-line](https://linuxconfig.org/set-wallpaper-on-ubuntu-20-04-using-command-line)