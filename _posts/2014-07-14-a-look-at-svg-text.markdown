---
layout: post
title: A Look at SVG text
date: '2014-07-14 14:53:37'

# Legacy
redirect_from:
    /a-look-at-svg-text/
---

The `<text>` element defines a graphic consisting of text. Writing and editing `<text>` in SVG provides a very powerful ability to create scalable text as graphics that can be easily changed and edited within the SVG code.

The use of the `<text>` element and its abilities are fairly extensive, but hopefully this quick post serves as an introduction to using this element by providing a brief summary of select attributes and a look at the use of a handy related element.

##The text Element

The `<text>` element is included within the `<svg>` element when using SVG inline. The appropriate attributes and properties within this element define the mapping and details of the text to be rendered. Within these attributes we can define specifics such as writing direction, font specification, and painting options.

Here is a look at the basic structure of using the `<text>` element:

<p data-height="268" data-theme-id="6090" data-slug-hash="e62394e43969fecb4269036260a3a575" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/e62394e43969fecb4269036260a3a575/'>1</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>


###x,y,dx,dy

The first letter within a `<text>` element is rendered according to the established `x` and `y` values. While the `x` value determines where to start the text along the x axis, the `y` values determined the horizontal location of the *bottom* of the text.

While `x` and `y` establish coordinates in an absolute space, `dx` and `dy` establish relative coordinates. This is especially handy when used in conjunction with the `<tspan>` element, which will be discussed further in a later section.

The above text starts 30px into the [viewport](http://jonibologna.com/svg-viewbox-and-viewport/) of the SVG, and the bottom of the text is set 90px in from the top of the viewport: `x="30" y="90"`.


###rotate

A rotation can be placed on the individual letters/symbols, and/or on the element as a whole.

A single value within the `rotate` attribute results in each glyph rotating at that value. A string of values can also be used to target and assign a different rotation value to each letter. If there are not enough values to match the number of letters the last value sets the rotation for the remaining characters.  

The text below has a rotation set on the entire graphic through the `transform` element, but also a value for each glyph: `rotate="20,0,5,30,10,50,5,10,65,5"`.

<p data-height="268" data-theme-id="6090" data-slug-hash="d46fe22b170668927920220e13c1093f" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/d46fe22b170668927920220e13c1093f/'>2</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>


###textLength & lengthAdjust

The `textLength` attribute specifies the length of the text. The length of the text will adjust to fit the length specified within this attribute by altering the space between the provided characters.

The following example has a `textLength` value of 900px and the spacing between the characters has increased to fill this space.

<p data-height="268" data-theme-id="6090" data-slug-hash="3020091b8dbd6e77c22827d6c31e35fc" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/3020091b8dbd6e77c22827d6c31e35fc/'>3</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>


When used in conjunction with the `lengthAdjust` attribute, it can be specified that both the letter spacing and glyph size should adjust to fit to these new length values.

A value of `"spacing"` results in an image that resembles the example above where the spacing between the characters has expanded to fill the space.

A value of `"spacingAndGlyphs"` directs both the spacing and the glyph size to adjust accordingly:

<p data-height="268" data-theme-id="6090" data-slug-hash="dec7865c1584e965742d52151236db65" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/dec7865c1584e965742d52151236db65/'>4</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>


##The tspan Element

The `<tspan>` element is significant because SVG does not currently support automatic line breaks or word wrapping. `<tspan>` allows us to draw multiple lines of text by singling out certain words or characters to then be manipulated independently.

Instead of defining a new coordinate system for these additional lines, the `<tspan>` element positions these new lines of text in relation to the previous line of text.

The `<tspan>` element has no visual output on its own, but by specifying more details within the elements we can single out this particular text and have more control over its design and positioning.  


In the example below "are" and "delicious" are located within separate `<tspan>` elements within the `<text>` element. By using `dy` within each of these spans, we are positioning the word along the y axis in relation to the word before it.

While "are" is positioned -30px from "Watermelons", "delicious" is positioned 50px from "are".

<p data-height="268" data-theme-id="6090" data-slug-hash="ea83c21659cf118df5b5d64b14b2a1c9" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/ea83c21659cf118df5b5d64b14b2a1c9/'>5</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>


You can also move each glyph individually through a list of values, as shown in the example below. The letter/symbol is then moved according to the position of the letter/symbol before it, and "delicious" is now positioned according to the "e" in "are".

<p data-height="268" data-theme-id="6090" data-slug-hash="943ca861a5154a2e2fbe3394d2031fda" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/943ca861a5154a2e2fbe3394d2031fda/'>6</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>



##Conclusion

While there is much more detail manipulation and design to be had within SVG `<text>`, this article reviewed some basic attributes in hopes of providing a better understanding of how to get started using this incredibly useful and powerful element.

*This post was originally published on [my CodePen blog](http://codepen.io/jonitrythall/blog/).*
