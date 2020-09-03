---
layout: post
title: A Look At SVG viewBox and viewport
date: '2014-06-17 17:01:22'

# Legacy
redirect_from:
    /svg-viewbox-and-viewport/
---

In using the `<svg>` element we are establishing a fragment consisting of nested details in our document. This fragment has its own viewport and coordinate system which can seem very complex and intimidating when first getting started.

Understanding the workspace of SVG is helpful in properly rendering your artwork, but becomes crucial once you get into more advanced SVG customization, like gradients and patterns where their details rely heavily on the established coordinate system.

While the topic is quite extensive, my hopes are that briefly discussing the purpose and general behavior of SVG viewport and viewBox will provide a foundation to get you going with your SVG workspace.

###viewport
The viewport is the visible section of an SVG. While an SVG can be as wide or as high as we wish, only a certain section of this image can be visible at a time.

The viewport is set through `height` and `width` attributes within the `<svg>`.

If we choose to not define a viewport (although I have encountered issues with Firefox here) the dimensions of this viewport will generally be determined by any other indicators we may have within the SVG, like the width on the outermost SVG element. Though, leaving this undefined leaves our artwork susceptible to being cut off.

I find that the more details you spell out within SVG the happier your image will be across browsers.


###viewBox
The viewBox provides us with very powerful capabilities. It allows us to specify that a given set of graphics stretch to fit a particular container element. These values include four numbers separated by commas or spaces: `min-x`, `min-y`, `width`, and `height` that should generally be set to the bounds of the viewport.

The `min` values represent from what point within the image the viewBox should start, while the `width` and `height` establish the size of the box.

If we choose to not define a viewBox the image will not scale to match the bounds set by the viewport.

####preserveAspectRatio
If the viewport and `viewBox` do not have the same width to height ratio, the `preserveAspectRatio` attribute directs the browser how to display the image.

The value descriptions here can get pretty lengthy, but the [Mozilla Develeper Network has a great writeup](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/preserveAspectRatio) to get you started.

Left unspecified the default setting here forces uniform scaling and the entire `viewBox` is visible within the viewport.

###Pear Example
Let's take a look at an image of a pear. Within this first example the viewport and `viewBox` are set to matching values, with a `width` of 115px and a `height` of 190px. The `viewBox` is set to cover the entire pear image, and that image is set to fill the bounds of its container.  

####Matching Dimensions

<p data-height="268" data-theme-id="6090" data-slug-hash="3a8c995a969cbcbc5c589aa9ad7de491" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/3a8c995a969cbcbc5c589aa9ad7de491/'>3a8c995a969cbcbc5c589aa9ad7de491</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>


####Reduced viewBox

If we were to take 50px off the `width` and `height` of the pear image `viewBox`, we are reducing the size of what portion of the pear we want visible, but then what is left visible will scale to fit to the bounds of the viewport.  

<p data-height="268" data-theme-id="6090" data-slug-hash="a1f47ea097e886493cf1d483629e655a" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/a1f47ea097e886493cf1d483629e655a/'>a1f47ea097e886493cf1d483629e655a</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>


####Expanding viewport
Let's add an additional 200px to both the `width` and `height` of the viewport. The image will scale up to match these dimensions. The `viewBox` is set to cover the entire image, making the whole pear visible. The viewport contains this whole image and defines the bounds to which the whole pear will fill.

Here's a look at an expanded viewport:

<p data-height="268" data-theme-id="6090" data-slug-hash="8d101869058142d3ce019b249ed35e2b" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/8d101869058142d3ce019b249ed35e2b/'>8d101869058142d3ce019b249ed35e2b</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>


####Altering min Values
The `min` values within the `viewBox` define the origin of the `viewBox` within the parent element; in other words, at what point within the `viewBox` do we want it to begin matching up the viewport. In the above examples the `min` values are set to 0,0 (top left). Let's change these to 50, 30.

<p data-height="268" data-theme-id="6090" data-slug-hash="46aaa8d7e8296945def4490ad5fd69d1" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/46aaa8d7e8296945def4490ad5fd69d1/'>46aaa8d7e8296945def4490ad5fd69d1</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>


The `viewBox` (what will be visible) now starts 50px in from the x axis and 30px in from the y axis. In altering these values we have simply changed the section of the pear we want to focus on.

###Conclusion
Understanding and setting the proper coordinate system for SVG is really helpful when creating and displaying your graphics consistently across browsers.

We reviewed some very basic alterations of an SVG viewport and `viewBox` which hopefully demonstrates the power and usefulness of thoroughly defining SVG workspaces.

Happy `viewBox` setting!
