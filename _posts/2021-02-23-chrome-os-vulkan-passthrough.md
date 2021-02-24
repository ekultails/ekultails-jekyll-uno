---
title: "EXCLUSIVE: Chromebooks to Support Vulkan Passthrough"
date: 2021-02-23 12:00:00
categories:
  - chromebooks
tags:
  - android
  - chromeos
  - gaming
  - laptop
  - linux
  - vulkan
---

![2021-02-23-chrome-os-vulkan-passthrough](../../images/2021-02-23-chrome-os-vulkan-passthrough.jpg) Passthrough of the Vulkan library from a QEMU hypervisor to a virtual machine is coming to Linux thanks to work sponsored by Google! This is a big deal for many reasons.

Side note: this is an article I’ve done a lot of research in the past and was surprised that no one else has picked up the pieces yet. So here we are: my first exclusive article! Now that I have a blogging platform, it’s the perfect time and place to share this exciting news! Honestly, this is by far my favorite thing I’m looking forward to in 2021.

As it is today, the [Virgil 3D GPU project](https://virgil3d.github.io/) has limited support for OpenGL passthrough to virtual machines. Chrome OS [already uses Virgil](https://www.xda-developers.com/chrome-os-76-gpu-support-linux-apps/) for its Linux (Beta) feature which runs Debian Linux as a LXC container inside of a Chrome OS virtual machine. This allows games to run within the Linux environment with OpenGL acceleration.

The Vulkan passthrough work is being lead by Chia-I Wu who has done work for [Valve in the past at LunarG](https://www.phoronix.com/scan.php?page=news_item&px=MTY4MjA) and is currently working at [Google on "Android Graphics"](https://www.linkedin.com/in/olvaffe/). Work-in-progress commits have been up for both [mesa](https://gitlab.freedesktop.org/mesa/mesa/-/merge_requests/5800) and [virglrenderer](https://gitlab.freedesktop.org/virgl/virglrenderer/-/merge_requests/412) projects for 7 months now. A user named Tomeu Vizoso has also reported that this work extends beyond Chrome OS and works with a normal Linux distribution. The work was originally planned to be released [by Google in 2020](https://bugs.chromium.org/p/chromium/issues/detail?id=996591#c7) but likely was pushed pack due to COVID-19 complications.

What can we likely conclude from all of this? A lot, actually.

- Chromebooks are the main targeted platform. However, the entire Linux community will benefit from this.
- Valve is bringing Steam to Chromebooks via [Borealis](https://chromeunboxed.com/native-steam-borealis-on-chrome-os-likely-arriving-mid-2021/) (an Ubuntu 18.04 virtual machine). Steam uses Proton as a compatibility layer for running Windows games on Linux. Valve only officially supports Vulkan (not OpenGL, although you can technically use OpenGL instead of Vulkan) for translating DirectX <= 12 calls. Borealis is unlikely to be released until the Vulkan passthrough work is done.
- Android is being [moved to a virtual machine](https://chromeunboxed.com/chrome-os-lays-the-groundwork-for-update-to-android-12-snow-cone/) on Chrome OS. Chia-I works on “Android Graphics” so it makes sense that they want to fully support GPU acceleration as they move towards more virtual machines.
- [Zink](https://www.phoronix.com/scan.php?page=news_item&px=Zink-Substantial-Perf-Cominghttps://www.phoronix.com/scan.php?page=news_item&px=Zink-Substantial-Perf-Coming) (OpenGL on Vulkan) will also benefit both Borealis and Android. The Virgil project provides an incomplete form of OpenGL passthrough. By utilizing Zink with full Vulkan support, all of the major graphics back-ends will then be supported on Linux virtual machines. Currently, OpenGL 4.6 and OpenGL ES 3.1 are fully supported via Zink.

tl;dr? Chromebooks are about to become the biggest platform to support Linux gaming.

What an exciting time! Will 2021 be the year of the Linux laptop? Chromebooks have just become the [second most popular operating system](https://arstechnica.com/gadgets/2021/02/the-worlds-second-most-popular-desktop-operating-system-isnt-macos-anymore/) so it’s not impossible! ;-)

Sources:

- [Chromium Bugs Issue 996591: Vulkan does not appear to be working in Crostini](https://bugs.chromium.org/p/chromium/issues/detail?id=996591#c12)
- [GitLab virgl/virglrenderer WIP: add Vulkan renderer](https://gitlab.freedesktop.org/virgl/virglrenderer/-/merge_requests/412)
- [GitLab Mesa/mesa WIP: add virtio-gpu Vulkan driver](https://gitlab.freedesktop.org/mesa/mesa/-/merge_requests/5800)

Follow me (Luke Short) on [Twitter](https://twitter.com/ekultails) or connect with me on [LinkedIn](https://www.linkedin.com/in/luke-short-68872813a/) if you want more in-depth Chrome OS and/or Linux gaming news!
