---
layout: post
title: building 1/2 of a music player
tags: [日本語, web development, technology]
description: 
---

Making a music player is much harder than I thought. During my personal hackathon at Fullstack Academy, I decided to build a music player because I was tired of trying out different players when switching between operating systems. I've been lucky that the W3 updated their support for audio within the last few months. With the use of audio tags and the Web Audio API, one can make a fully featured music player like iTunes or foobar2000!

Thankfully, there are designers out there that already provide icons for people to use in their own projects. With a combination of Bootstrap and Font-Awesome, I was able to get the basic outline of ongaku player looking familiar. I stripped out all the roundedness of Bootstrap and tried to emulate Material Design. AngularJS was present to help with toggling between classes and other elements.

One issue while building my application was that I had weird garbled text whenever there were foreign characters on my filepaths. I was confused as to why it looked so unusual and why my files wouldn't play.
![hueheheue](/images/WithWithoutMeta.JPG)

It turns out that if you include the line below:
```
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
```  
you can actually display foreign characters! You can see the difference between the top and bottom of the picture.

Another issue that I ran into when trying to make a front-end html player was trying to get the filepaths of local files. Due to the concerns over privacy you cannot actually get the data from local files via normal means. Though it is possible to drag-and-drop files over into the browser, you can only store them locally within the cache, there is no persistence for the application. 

Though I may be a newbie developer, it was still quite a fun challenge, even if my code doesn't share the finesse that other experienced developers may have. Next up is actually building all of this code into a Chrome Application and documenting it. This way, I can actually create multiple playlists and get the ID3 tags for proper enjoyment and library management! Check out my current progress on [github](https://github.com/ersgonzalo/ongaku-player)!
