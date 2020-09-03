---
layout: post
title: Problems with CSS Triangles
date: '2014-03-19 16:51:09'

# Legacy
redirect_from:
    /using-css-triangles/
---

I have been using CSS triangles a lot lately in  drawings. While they are genius and I love them, they can also be annoying and inflexible. I figured out how to make them slightly less annoying and thought I should shout it from the rooftops.

The first issue I ran into was the transparent sides of the triangle appearing very jagged with Firefox. I looked into this for a while and mostly found mentions of hardware acceleration issues. Well, after addressing this I still had those hideous edges.

The only thing that solved the problem for me: making the border of the transparents sides "dotted" instead of "solid". Don't ask me why this works (seriously, don't), but it does. Here's a look at a triangle I used to create a crab claw effect:

	width: 0;
	height: 0;
	border-left: 60px dotted transparent;
	border-right: 60px dotted transparent;
	border-top: 90px solid $background-color;

<p data-height="268" data-theme-id="4899" data-slug-hash="jtomI" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/jtomI/'>Shifty the CSS Crab </a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>

Another issue I ran into is using box shadows on triangles. Given the structure of the triangle, a lovely shadow will appear on the bottom, but the sides will arch out creating a big ugly oval. Not the look I was going for.

To make this work I applied a small box shadow that didn't make the sides get all goofy, and then added `:before` and `:after` pseudo selectors to essentially recreated the sides. I positioned these over the triangle sides and then added the box shadow.   

You can take a look at this bit of hackery with this corner "page turn" effect on my CSS calendar:
<p data-height="268" data-theme-id="4899" data-slug-hash="rJfKD" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/rJfKD/'>Calendar With Corner Page "Turn"</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>

Chris Coyier discusses [shadow solutions here as well](http://css-tricks.com/triangle-with-shadow/).

I suppose this post is equal parts "hey, look how I hacked this triangle into cooperating" and "hey, any suggestions on cleaning this up and making life less difficult?". [Get me on Twitter](https://twitter.com/JoniTrythall) with any suggestions.

Happy triangle manipulating!
