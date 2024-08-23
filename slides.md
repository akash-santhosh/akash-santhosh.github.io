---
theme: seriph
background: https://salsa.debian.org/debconf-team/public/share/debconf24/-/raw/main/photos/aigarius/group/debconf24_group.jpg
title: DebConf and VideoTeam

  Learn more at [Sli.dev](https://sli.dev)
class: text-center
drawings:
  persist: false
transition: slide-left
mdc: true
---

# DebConf and VideoTeam Experiences

Slide for FUK Meetup

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Let's Roll <carbon:arrow-right class="inline"/>
  </span>
</div>

---
transition: fade-out
---

# What is DebConf?

DebConf is a Project by Debian

- It runs anually and does not host at the same location (so far)
- **DebCamp** - Some attendees find it very valuable that DebConf gives them uninterrupted time to work on their Debian contributions
- **Enable face-to-face interactions** - Many Debian contributors find communication much easier face-to-face than online. Intense technical discussions at DebConf can shortcut weeks or months of mailing list threads.
- **Provide talks and video** - DebConf talks can help to spread information beyond those already heavily involved in an area of Debian work, and can help to recruit more people to work on areas of Debian.
- **Motivate the local community** - It is positive if DebConf leads to a greater involvement in Debian from locals in the region where it is held.



<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>


---
layout: image-left
image: https://debconf-video-team.pages.debian.net/docs/_images/room_setup_video.svg
transition: fade-out
---

# The VideoTeam


- **Main Feed** - code highlighting, live coding with autocompletion

- **Streaming Backend**  
  - uses nginx-rtmp-module (also used by FOSDEM and CCC)
  - downscales internally, using ffmpeg, for lower quality streams
   - converts RTMP streams to HLS with adaptive quality
- Streaming Frontends are plain HTTPS caching proxies, geographically distrubuted
- all configured in the live.debconf.org DNS zone with a small TTL
- javascript player
<br>
<br>


<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---
transition: slide-up
level: 2
layout: image-right
image: https://i.ibb.co/4PQQr7X/sreview.png
---

# The VideoTeam

It's not all about live

## Review System

The Review system is called SReview

- It is written by Wouter
- fully automatic pipeline for
   - preview generation
  - review of start and end cut times
  -final cut generation
  - video transcoding
  - archive publication
- also used by FODSEM


---
---

# The old FTP Archive

Yes, you heard it right, FTP Archive

- It's available at https://meetings-archive.debian.net
- A big bunch of files on a FTP Server (actually a git-annex repo)
- Pretty random mix and amatch of files: videos, subtitles, slides, and ...
- New repository with metadata:
  - scans conference websites and the meetings archive for data
  - https://salsa.debian.org/debconf-video-team/archive-meta
  - can be eventually used for a proper frontend
  - supports all the kinds of files we have 


---
layout:
---

# Youtube
 Peertubeil മാത്രം അല്ലടാ അങ്ങ് യൂട്യൂബിലും ഉണ്ടെടാ പിടി

There were people who randomly upload our videos to Youtube, so why not we do it.

- Channel: https://deb.li/dcvideoyt
  - per-event playlishts
  -  feeds from the archive-meta data
  - generates automatic closed captions which are hilarious of course
- scripts: https://salsa.debian.org/debconf-video-team/youtube.git

---
layout:
---

# Machine Setup and Configuration

- PXE server with Debian Installer preseeding configuration
- everything else (mixing machines, streaming network) configured in ansible
- https://salsa.debian.org/debconf-video-team/ansible.git

---
layout: image
image: https://debconf-video-team.pages.debian.net/docs/_images/streaming.svg
---


---

# Documentation

- static documentation goes in a sphinx repository
  - https://salsa.debian.org/debconf-video-team/docs.git
  - built on https://video.debconf.org
  - also has the live streanm player for MiniConfs
- dynamic documentation on the wiki
  - https://wiki.debian.org/Teams/Debconf/Video
  - slowly migrating from the DebConf wiki to the Debian wiki   
---
layout: center
class: text-center
---

# Thank you

## I've been Akash
Network and Systems Engineer

status.aks.one

  <footer
    v-if="$nav.currentPage !== 4"
    class="absolute bottom-0 left-0 right-0 p-2"
  >
    aks.one | akashsanthosh.com
  </footer>
