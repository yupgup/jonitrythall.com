---
layout: post
title: Using Text In SVG As Outlines
date: '2014-01-23 09:32:41'

redirect_from:
    /using-text-in-svg-as-outlines/
---

I started building a full site this week and was instantly confronted with the fact that I do not have a handle on using SVG on the web. This was made apparent when I tried to add a text based SVG image into my site without first converting the text to outlines. Curses!

When you save an SVG that consists of text and try to add it into a site, well, the browser will not recognize the font and it will be turned into something generic and ugly. To fix this we need to convert the text to an outline. The first thing you will want to do is get the artboard to fit snuggly around the text. Do this by going to Object &gt; Artboards &gt; Fit to Artwork Bounds. 

<em>Oh no! Unfortunately this image has been lost forever</em> 😱

<em>Oh no! Unfortunately this image has been lost forever</em> 😱

Once you have your final font in place, you will need to convert it to outlines. You do this by selecting all, then going to Type &gt; Create Outlines.

<em>Oh no! Unfortunately this image has been lost forever</em> 😱

<em>Oh no! Unfortunately this image has been lost forever</em> 😱

Once you have finalized your color selection, save the file as a SVG file and add image to your HTML. Below is an example of the HTML and image rendered on the web. 

<em>Oh no! Unfortunately this image has been lost forever</em> 😱

<em>Oh no! Unfortunately this image has been lost forever</em> 😱

Chris Coyier gets more into the topic <a href="http://css-tricks.com/using-svg/" target="_blank">here</a>. Also worth checking out is <a href="http://coding.smashingmagazine.com/2012/01/16/resolution-independence-with-svg/" target="_blank">this</a> Smashing Magazine article by David Bushell.

Happy effortless resizing!
