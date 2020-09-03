---
layout: post
title: Sass Variables In CSS Animations
date: '2014-02-05 10:31:32'

tags:
- configuration
- css-animaiton
- sass

# Legacy
redirect_from:
    /blog/blog/newton-the-configurable-css-frog/
---

Sass meets CSS animation. This was officially the most fun I have had with self-assigned homework. I haven't used Sass much since I wrote about it <a href="http://jonibologna.com/2014/01/getting-sassy/" target="_blank">in this post</a> a couple weeks ago, and I can't get my head out of CSS animations these days, so why not practice both at once?

The bulk of my time was spent on creating and positioning the frog with a series of div tags, including the items that I planned on animating. You can select between the "HTML" and "SCSS" tabs on the preview below to see the dirty details.

Once Newton was born and looking flippin' adorable it was time to move onto animation. I posted some <a href="http://jonibologna.com/2014/01/intro-to-basic-css-animation/" target="_blank">basic CSS animation notes</a> recently, so I won't get into that too much again, but I wanted to mention which properties I used on Newton specifically. For the crown to drop on his head I added a negative value at 0% in the keyframe "crowned" and included a rotation at this point as well. The 100% point is where the hat lands and stays on his head. The blushing effect was done with an opacity change within the keyframe, with 0% having an opacity of 0 in keyframe "blush". And finally, for his tongue I included a height of 0 at 0% in the keyframe "slip".

The final step was to create the <a href="http://sass-lang.com/guide" target="_blank">Sass variables</a>. The animations were triggered here by declaring true or false. You can change the color of certain elements as well. The trickiest part with this was getting the elements to not be on the page until someone commands them to be. To do this I added <code>display: none;</code> to each element that was to be animated, and then added <code>display: block;</code> within a <a href="http://sass-lang.com/documentation/file.SASS_REFERENCE.html" target="_blank">Sass @if statement</a>. This directive takes a Sass expression and uses the styles nestled beneath it. So, once the user declares "true" on the variable "$has-crown", for example, this triggers the @if statement which tells <code>display: block;</code> to activate and the crown appears.

<p data-height="268" data-theme-id="4899" data-slug-hash="wuAbi" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/wuAbi'>Newton The Configurable Frog </a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>

The possibilities are quite literally endless, but sometimes I need to sleep and bathe.

Happy configuring!
