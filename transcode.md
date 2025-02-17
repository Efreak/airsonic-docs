---
layout: docs
title: Setting up transcoding binaries
permalink: /docs/transcode/
---
Transcoders are used by Airsonic to convert media from their on disk format to a format that can be consumed by clients. This is done not only for compatibility but also to save bandwidth when dealing with heavier file types. For example, although your library might use the flac format, bandwidth can be saved by converting to mp3 before transmission.

#### Install the transcoder

##### On Debian 9

Install ffmpeg package:

```
sudo apt install ffmpeg
```

Create a `transcode` directory within your `AIRSONIC_HOME` directory:

```
mkdir /var/airsonic/transcode
```

Within the `transcode` directory symlink to ffmpeg and verify correct permissions:

```
cd transcode/
ln -s /usr/bin/ffmpeg
chown -h user:user ffmpeg
ls -alh
```
```
lrwxrwxrwx 1 user user   15 mai    4 19:57 ffmpeg -> /usr/bin/ffmpeg
```

> **NOTE**:  `user` has to be the user that runs Airsonic

##### On Debian 8

Open your `/etc/apt/source.list`:

```
sudo nano /etc/apt/source.list
```

Add the backports repo to it:

```
deb http://ftp.fr.debian.org/debian/ jessie-backports main contrib
```

Update your package list:

```
sudo apt-get update
```

Install ffmpeg package from jessie-backports:

```
sudo apt-get install ffmpeg -t jessie-backports
```

Create a `transcode` directory within your `AIRSONIC_HOME` directory:

```
mkdir /var/airsonic/transcode
```

Within the `transcode` directory symlink to ffmpeg and verify correct permissions:

```
cd transcode/
ln -s /usr/bin/ffmpeg
chown -h user:user ffmpeg
ls -alh
```
```
lrwxrwxrwx 1 user user   15 mai    4 19:57 ffmpeg -> /usr/bin/ffmpeg
```

> **NOTE**:  `user` has to be the user that runs Airsonic

##### On Ubuntu > 16.04

Install ffmpeg package:

```
sudo apt-get install ffmpeg
```

Create a `transcode` directory within your `AIRSONIC_HOME` directory:

```
mkdir /var/airsonic/transcode
```

Within the `transcode` directory symlink to ffmpeg and verify correct permissions:

```
cd transcode/
ln -s /usr/bin/ffmpeg
chown -h user:user ffmpeg
ls -alh
```
```
lrwxrwxrwx 1 user user   15 mai    4 19:57 ffmpeg -> /usr/bin/ffmpeg
```
> **NOTE**:  `user` has to be the user that runs Airsonic

##### On Red Hat / Fedora

Install ffmpeg package:

```
sudo yum install ffmpeg
```

Create a `transcode` directory within your `AIRSONIC_HOME` directory:

```
mkdir /var/airsonic/transcode
```

Within the `transcode` directory symlink to ffmpeg and verify correct permissions:

```
cd transcode/
ln -s /usr/bin/ffmpeg
chown -h user:user ffmpeg
ls -alh
```
```
lrwxrwxrwx 1 user user   15 mai    4 19:57 ffmpeg -> /usr/bin/ffmpeg
```
> **NOTE**:  `user` has to be the user that runs Airsonic

##### On Windows

Get the ffmpeg package from one of the the project's download pages: [BtbN/FFmpeg-Builds](https://github.com/BtbN/FFmpeg-Builds/releases) or [gyan.dev](https://www.gyan.dev/ffmpeg/builds/#release-builds) or its github mirror, [GyanD/codexffmpeg](https://www.github.com/codexffmpeg/releases) (latest release [here](https://www.gyan.dev/ffmpeg/builds/ffmpeg-release-github))

Unpack the files into the `AIRSONIC_HOME/transcode/` folder.

##### On MacOS

You can install ffmpeg binaries on MacOS using `Homebrew`:

```
brew install ffmpeg
```

Create a `transcode` directory within your `AIRSONIC_HOME` directory:

```
mkdir /var/airsonic/transcode
```

Within the `transcode` directory symlink to ffmpeg and verify correct permissions:

```
cd transcode/
ln -s "$(brew --prefix)/bin/ffmpeg"
chown -h user:user ffmpeg
ls -alh
```
```
lrwxrwxrwx 1 user user   15 mai    4 19:57 ffmpeg -> /usr/bin/ffmpeg
```
> **NOTE**:  `user` has to be the user that runs Airsonic
