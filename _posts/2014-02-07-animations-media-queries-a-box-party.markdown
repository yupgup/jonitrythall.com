---
layout: post
title: Using Media Queries In Animations
date: '2014-02-07 12:10:07'
tags:
- css-animation
- media-queries
- responsive

# Legacy
redirect_from:
    /blog/blog/animations-media-queries-a-box-party/
---

I recently learned <a href="http://jonibologna.com/2014/01/media-queries-intro/" target="_blank">about media queries</a>. I recently learned <a href="http://jonibologna.com/2014/01/intro-to-basic-css-animation/" target="_blank">about CSS animation</a>. This week I combined the two and it was beautiful, exciting, emotional, and dangerous.

I started off by created a series of boxes and giving them adorable names, and then creating basic faces for them. I added a few different <code>@keyframes</code> to this, but will focus on the eyes. The first thing I knew I wanted to do was have their eyes move, but not all in the same direction. To do this, all the pupils have the same class and every other set of pupils has an additional class. I used <code>class="pupil"</code> and <code>class="pupil pupil-2"</code> because I am not a clever person apparently. You will then assign an animation to "pupil" and a different animation to "pupil-2". The second set of pupils will take on all the styling of the original pupils, but will follow a different set of <code>@keyframes</code>.

The next order of business was adding a media query that would trigger the animation to work only once the screen has been scaled down. Once the <code>@keyframes</code> were set up, I added a media query with the following screen specifications. The CSS for .mouth-open, for example, tells the animations to turn off when a screen is greater than 800px: <a href="http://jonibologna.com/wp-content/uploads/2014/02/Screen-Shot-2014-02-07-at-10.46.37-AM.png"><img class="aligncenter size-full wp-image-883" alt="Screen Shot 2014-02-07 at 10.46.37 AM" src="http://jonibologna.com/wp-content/uploads/2014/02/Screen-Shot-2014-02-07-at-10.46.37-AM.png" width="357" height="421" /></a>

In situations like the tongue, that should disappear completely at full screen, you would add a media query of <code>display: none;</code> on the element. Full screen, these guys do nothing. Smaller screen, they party. Hard.

<p data-height="268" data-theme-id="4899" data-slug-hash="CbemF" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/CbemF'>Responsive Box Party </a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>

For further reading on the topic I found <a href="http://www.webdesignerdepot.com/2013/06/how-to-animate-media-queries/" target="_blank">this article by Sara Vieira</a> and <a href="http://css-tricks.com/animated-media-queries/" target="_blank">this writeup by Chris Coyier</a> to be the most helpful.

Happy responsive designing.
