---
layout: post
title: Issue with processing-video library [Fedora 26]
---

Well, I was somewhat stuck with the optional work proposed for the first Processing 3 workshop. The initial idea was to take any image and build a new one in gray scale, exactly like the original one, processing it pixel by pixel.

Once this workshop was successfully developed, the teacher suggested doing the same exercise, but with video, taking frame by frame and converting it to grayscale, however, the library suggested by the very Processing 3 documentation was "processing-video" , which was unsuccessful to use, since it presented an error like the one shown in the image below.

Currently my laptop is not very powerful, or CPU, or GPU, or RAM, but it is just to do most of my work without problems, in addition, the operating system on which I was trying everything in this little post is Fedora 26 Workstation

![Error using the library]({{ site.baseurl }}/images/2017-2-22/processing_video_error.png "Architecture error")

~~~
 UnsatisfiedLinkError: Error looking up function 'gst_date_get_type': /usr/lib64/libgstreamer-1.0.so.0.1203.0: undefined symbol: gst_date_get_type
 A library relies on native code that's not available.
 Or only works properly when the sketch is run as a 64-bit application.
~~~

Thanks to the teacher's suggestions, I started to track the error with the gstreamer library, which I had installed in a very old version, so I proceeded to install it in a newer version.

~~~
sudo dnf install gstreamer gstreamer-plugins-base-devel
~~~

This time it seemed to work, however, at the time of running the program, nothing appeared on the screen beyond a black screen, it should be noted that to see the MOV format video that I had prepared for the workshop, I used the software VLC, but in my operating system I did not have the codec to view it in any other player, so I proceeded to download it. [Forum link](https://forums.fedoraforum.org/showthread.php?275467-How-can-I-watch-MOV- files)

~~~
sudo dnf install gstreamer {1,} - {ffmpeg, libav, plugins- {good, ugly, bad {, - free, -nonfree}}} --setopt = strict = 0
~~~
Voilà! Now I can play videos with Processing 3, I just need to do the activity proposed by the teacher in the class ...

![Problem solved!]({{ site.baseurl }}/images/2017-2-22/solved.png "Solved :D")
