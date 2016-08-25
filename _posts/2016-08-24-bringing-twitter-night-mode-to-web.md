---
layout: post
title:  Bringing twitter night mode to web!
date:   2016-08-24 21:00:00 +0530
summary: Extensions to get Android/iOS twitter app like night mode in twitter web on Chrome and Firefox.
---
**tl;dr** - I wrote extensions for Chrome and Firefox to bring twitter's night mode to web. You can install them using the links below:

**Chrome** - [https://chrome.google.com/webstore/detail/twitter-web-night-mode/cadmiljohldbooihfbkjkobepojailca](https://chrome.google.com/webstore/detail/twitter-web-night-mode/cadmiljohldbooihfbkjkobepojailca){:target="_blank"}

**Firefox** - [https://addons.mozilla.org/en-US/firefox/addon/twitter-web-night-mode/](https://addons.mozilla.org/en-US/firefox/addon/twitter-web-night-mode/){:target="_blank"}

This is how it looks:

![twitter web night mode]({{ site.url }}/assets/img/twitter-night-mode-chrome.png)


### More...

Since the time twitter launched [night mode](https://twitter.com/twitter/status/757969656493649921){:target="_blank"} in the Android app, I've been using it and liking it more than the white theme. Later they brought it to their [iOS app](https://twitter.com/twitter/status/767759522437836800){:target="_blank"} as well. I am not sure if they have idea of bringing it to the web app. So I thought of writing browser extensions to build the night mode myself. After all, it's just CSS! I have never written an extension before and I must admit that these browser vendors have made it really really simple to build extensions.

This brings the night mode only to Home page timeline though. You can switch between the night mode and default theme by clicking on the icon in toolbar. It reloads the tab when you disable night mode, couldn't find a way to remove the inserted CSS dynamically. Would appreciate any help! I'm planning to make it available for other pages based on the feedback / usage.

I have used [SASS](http://sass-lang.com/){:target="_blank"} for styles and [Gulp](http://gulpjs.com/){:target="_blank"} for the (simple) build process. I took color codes from the Android app using Firefox's color picker. You can access the code here - [https://github.com/tsriram/twitter-web-night-mode](https://github.com/tsriram/twitter-web-night-mode){:target="_blank"}. Feel free report any issues there.


**Chrome Vs Firefox**

However you have to tweak the extension a bit to make it compatible with both Chrome and Firefox (I haven't looked at other browser extensions yet). 

First, Firefox needs an additional property called [applications](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/manifest.json/applications){:target="_blank"} in [manifest.json](https://developer.chrome.com/extensions/manifest){:target="_blank"} to support versions older versions. I ended up managing this in gulp build script, there ought to be a better way for this I suppose.

Next, the top level object (*chrome* in Chrome and *browser* in Firefox) of the API is different between these two platforms. You have to handle that as well. This is not a big deal, but it'd help to have a common API.

Firefox doesn't support sync storage yet which would help in saving extension preferences and using it across your devices. So I had stick to the local storage for now. Chrome extension didn't need *tabs* permission but Firefox extension won't work without it.

I have tested these on Chrome 52 and Firefox 48 running on Ubuntu. Hope it works on other recent versions & OSes too. If it doesn't, you know where to report it :)


Overall, it was a good learning experience to build the extension and I'm already thinking about what extension to build next :D