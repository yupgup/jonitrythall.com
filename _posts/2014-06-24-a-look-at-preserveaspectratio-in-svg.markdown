---
layout: post
title: A Look At preserveAspectRatio in SVG
date: '2014-06-24 16:38:33'

# Legacy
redirect_from:
    /blog/blog/a-look-at-preserveaspectratio-in-svg/
---

I recently wrote a post on [understanding SVG viewport and viewBox](http://jonibologna.com/svg-viewbox-and-viewport/) and figured this would be the perfect follow-up topic to quickly dig a little deeper.

Understanding SVG workspace can be really tricky. There is a lot of customization to be had within this space and the more details we provide the more likely our graphics will have consistent output across browsers. Also, the details within our SVG, like gradients or patterns, can rely heavily on the initial coordinate system that we define.  

##viewBox and viewport Summary

The `width` and `height` of our SVG establish the visible area (the viewport), and setting a `viewBox` allows us to specify that our graphics stretch to fit a certain container (usually the viewport). When the values of each are the same, the entire image is visible and scales accordingly when the viewport dimensions are altered. It's a beautiful thing.

If the SVG `viewBox` and viewport do not have the same width to height ratio, `preserveAspectRatio` indicates whether or not to force uniform scaling.

In the following examples we will look at a some cherries and the effect various `preserveAspectRatio` values will have on their visual output. Here are the cherries set to scale uniformly with matching viewport and `viewBox` values.


<p data-height="268" data-theme-id="6090" data-slug-hash="d0ceecfa63eca90cfa211034ddf209e6" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/d0ceecfa63eca90cfa211034ddf209e6/'>1</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>


##preserveAspectRatio Values

`preserveAspectRatio` takes two parameters, `<align>` and `<meetOrSlice>`. The first parameter takes two parts and directs the `viewBox`'s alignment within the viewport, and the second is optional and indicates how the aspect ratio is to be preserved.

`preserveAspectRatio=“xMaxYMax meet”`

These values will align the bottom right corner of the`viewBox` to the bottom right corner of the viewport. `meet` preserves the aspect ratio by scaling the `viewBox` to fit within the viewport as much as possible.

There are three `<meetOrSlice>` options: meet (default), slice, and none. While `meet` ensures complete visibility of the graphic (as much as possible), `slice` attempts to fill the viewport with the `viewBox` and will then slice off any part of the image that does not fit inside the viewport after this scaling. `none` results in no preserved aspect ratio and a potentially distorted image.

You can find a complete list of value combinations and their descriptions [here at the W3C](http://www.w3.org/TR/SVG/coords.html#PreserveAspectRatioAttribute).

##Aspect Ratios and Cherries

Perhaps the most straightforward value here is "none", which establishes that uniform scaling should not be applied. If we then increase the pixel values of the viewport, the cherries will stretch non-uniformly and look distorted and non-delicious.


<p data-height="268" data-theme-id="6090" data-slug-hash="8943154485dcb3662f95a6756f1d097b" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/8943154485dcb3662f95a6756f1d097b/'>2</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>


###Altered Min, Max, Mid Values

Let’s take a look at the effects of a few different value combinations.


<p data-height="268" data-theme-id="6090" data-slug-hash="9edd85f9931af23b30726845c184ee9b" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/9edd85f9931af23b30726845c184ee9b/'>3</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>


The `preserveAspectRatio` here is set to `xMinYMax meet` which is aligning the bottom left corner of the `viewBox` to the bottom left corner of the viewport, which is now outlined. `meet` is ensuring the image is scaling to fit inside the viewport as much as possible.

Changing `xMin` to `xMax` or `xMid` will position the cherry to the right or to the center of the viewport.

Here’s what will happen is we change `meet` to `slice`:


<p data-height="268" data-theme-id="6090" data-slug-hash="2eede68379ac3f2702e5e30342a3ce0b" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/2eede68379ac3f2702e5e30342a3ce0b/'>4</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>


The cherries are no longer being forced to fit within the bounds of the viewport and the excess graphic is sliced off once the `viewBox` fills the viewport.

The alignment values do not have to correlate.  


<p data-height="268" data-theme-id="6090" data-slug-hash="63e0bed4bd9b7519da1c2f287963d4f6" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/63e0bed4bd9b7519da1c2f287963d4f6/'>5</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>


The above example has a `preserveAspectRatio` of `xMinYMid slice`. We are now seeing the cherries aligned along the middle of the y axis of the viewport.

##Conclusion
Establishing your ideal SVG workspace can seem somewhat tedious, but taking the time to define certain details can result in much more powerful and flexible graphics.

######This post was originally published on [my CodePen blog](http://codepen.io/jonitrythall/blog/).
