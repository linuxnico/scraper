scraper
=======

A scraper for EmulationStation written in Go using hashes.
This currently only works with NES and SNES ROMs.

Installation
------------

```bash
$ go get github.com/sselph/scraper
$ go build github.com/sselph/scraper
```

Usage
-----

```bash
$ cd <rom directory>
$ mkdir images
$ scraper
```

ROMs will be scanned and a gamelist.xml file will be created. All images will be placed inside the images folder.

Raspberry Pi
------------
The Raspberry Pi's build process is a little different. At the time of writing this raspbian has an old version of go 1.0.2 so it can't handle progressive scan jpeg files also when building for the pi you have to specificy the type of ARM processor.

Build:

```bash
$ GOARM=5 go build github.com/sselph/scraper
```

Usage:
Add thumb_only so that it doesn't download the larger progressive jpeg files.

```bash
$ scraper -thumb_only
```
