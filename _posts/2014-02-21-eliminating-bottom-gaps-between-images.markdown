---
layout: post
title: Eliminating Bottom Gaps Between Images
date: '2014-02-21 13:21:21'

# Legacy
redirect_from:
    /blog/blog/eliminating-bottom-gaps-between-images/
---

Sometimes CSS makes me so happy. Sometimes it makes me cry, but then I find a solution and am even happier than when things just work. Using a trillion images is one recent example of things that start out seemingly easy, become surprisingly tricky, leads to pouting, and ultimately ends in joy and accomplishment.

I am working on a piece for my food site which is comprised almost entirely of images and typography. The first issue I ran into with these images was eliminating white space that existed at the bottom of about 4px. The offending element was made apparent when I added a red border around the image's wrapping anchor tag to find out what the flip is going on. Here's what my "Red Border Investigation" uncovered:

![Red Border Investigation](/content/2014/May/Screen_Shot_2014_05_07_at_7_50_30_AM.png)

By adding a red border to the anchor, it shows that the inside image was stopping before it hit the bottom of the outside anchor.

The <a href="http://stackoverflow.com/questions/7774814/remove-white-space-below-image">solution I used</a> for this made me emotional all over again. In a good way. Apparently this space is created by descenders, because <code>&lt;img&gt;</code> is an inline element by default. By changing the image to <code>display: block;</code> this horrendous bit of white space disappears. Tears.

<p data-height="268" data-theme-id="4899" data-slug-hash="wyEpe" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/wyEpe'>Meat Selection </a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>

Happy white space eliminating!
