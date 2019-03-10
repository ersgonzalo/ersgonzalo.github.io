---
layout: post
title: Death to Bloatware
tags: [technology]
description: I hate bloatware that takes up space and resources.
---

Credits to karmickoala in the [Hacker News comments section](https://news.ycombinator.com/item?id=18864220) plus the XDA Developers posts regarding the LG Behaviour. Due to Pokemon Go being unnecessarily wary of rooted phones and manually doing checks against certain filenames and directories, it isn't viable for me to root my LG V35 (and risk other things). The interim to prevent additional battery drain/space from being taken up was discovered on random January Wednesday by looking at the discussions on Hacker News.

What I hadn't realized is that this was what I originally had done on my HTC Droid Incredible 9 years ago. I had manually uninstalled the various carrier apps and other bloat I didn't need individually and poked my head a little deeper into development. Up until this LG V35, I had always rooted my phone and removed any bloatware via Custom ROMs. Until I'm able to modify the hosts file, these modified steps below are a good interim for being non-rooted.

<img src="/images/bloat/Platform Tools.png" />

1. Download Android platform tools for your current OS:
[https://developer.android.com/studio/releases/platform-tools](https://developer.android.com/studio/releases/platform-tools)
2. Install drivers for you Android device in case it is not properly recognized by the computer. You should anyway in case so that it is better recognized on your computer. Depending on the manufacturer, you can navigate down their support portal to find an installation. In my case since I had the LGV35, [this page](https://www.lg.com/us/support-mobile/lg-LMV350ULM#softwareFirmware) was good for me to get drivers for Windows 10 to recognize. 
3. Unzip the Platform Tools package, open cmd or bash and navigate to the unpacked folder via that command line window. 
4. Enable Developer Tools and USB debugging on your Android device.
5. Connect your android device to your computer.
6. Verify you can indeed see your device by using the adb devices command. You many not see it it because you have to accept a condition on your phone for the computer to recognize it due to Android debugging being toggled.
7. List packages available:  
  _adb shell pm list packages_
8. Delete the unwanted package with this command  
  _adb shell pm uninstall --user 0 com.package.name_

<img src="/images/bloat/Bash.png" />

You should be in the clear now to remove any apps. If you were to check your installed apps that you may have disabled, they should no longer be present on your phone. (Although they may still display as "Not Installed" placeholders if you were to toggle the "Show System [Applications]" view on the page, this is okay and better than them being disabled as they should no longer be taking up space.)

P.S. This is also a guide for me in the future for any future phones I may try to debug or help reduce bloat for. Though it could be a tiny bit cumbersome, with these steps documented, I can't possibly be confused in the future!
