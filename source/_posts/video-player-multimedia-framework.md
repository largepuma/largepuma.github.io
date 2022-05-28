---
title: Video Player & Multimedia Framework
tags: []
id: '49001'
categories:
  - - Other
date: 2011-03-05 02:16:37
---

It have been five months after we ended the project of video player on android. In all, it is a success. However, there are many improvement that we should achieve and we can achieve.
<!-- more -->
These days, the most convenient method of implementing various multimedia applications is using multimedia framework. A multimedia framework is a software framework that handles media on a computer and through network. The common framework includes Quicktime, DirectShow, and gstreamer. 

Though using multimedia framework is easy to construct an application, it is't a flexible method. So when there is a task of building a video player on android platform, we decide to implement the main part of application by ourselves, using the ffmpeg as the backend.  The work mainly consists of building the filters, connecting the filters to a pipeline, and signal processing. We succeed build a demo that can play video local or from network smoothly in one and a half month.

There are still some problems that should be solvedl. The application have some filters and one controller. When a user emit some command, for instance PAUSE, this signal should been transport to the filters. So, the smart method is registering all the filters on the controller. When a signal comes, it will transmit the signal to all the filters. It is called publish/subscribe pattern. Besides, the video player mainly uses the pipe/filter pattern.

PS: reference the gstreamer

[http://gstreamer.freedesktop.org/](http://gstreamer.freedesktop.org/)