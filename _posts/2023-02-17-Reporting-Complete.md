---
layout: post
title:  "Final Report Submitted"
date:   2023-02-17 16:00:00
author: Seth Berrier
---
With the final report submitted to the NSF and under review, we are now working to update this project site and fill in as much detail as possible.  You can look forward to seeing lots of information get filled in over the next few months as we document the software, add data sets, and start to really put the PARSEC equipment through its paces.

One of the first parts of that is available now!  We have completed the first pass at documentation for the the backend server used with PARSEC (the nodejs-canon-capture-server). When this software is running it provides a web server that allows you to read and write settings to Canon cameras that are connected via USB.  It can also control ESPER trigger boxes connected to the computer.

You can read all about the software at the [documentation page]({{ '/docs/capture-server/' | relative_url }}). Here each possible server route is documented detailing how you can access individual cameras and their settings, change their current exposure settings and modes, control where they will send images once the shutter is released, and much, much more!  It supports changing settings in bulk as well so that all cameras or a sub-set of connected cameras can be updated at once and have those settings verified.

This is a LOW-LEVEL back-end piece of software meant to be combined with a GUI front end of some sort and is not intended for use by the general public yet. However, it is our hope that other researches with basic JavaScript and node.js knowledge could use this tool and possibly build their own interface for it or employ it in other ways to do many different photogrammetry based tasks. Feel free to explore the software in its github repository or at the documentation link above.

The next big task will be to document the GUI we are using to control our specific setup here at Stout.  This is the [nodejs-canon-control-client]({{ '/docs/capture-client/' | relative_url }}) and is a front-end GUI for the server we already described above.  It will take much longer to document this piece of software as we did not do so as we were building it (I know, I always tell my students not to do this, but deadlines won out this time).

We will remedy this over the next few months and look forward to releasing this as well to represent a set of tools that less technically knowledgeable users could still take advantage of and use for their own Photogrammetry projects.
