---
layout: post
title: The Three Columns Dilemma
date: '2014-01-16 15:07:15'

redirect_from:
    /the-three-columns-dilemma/
---

Today I set out to replicate <a href="http://codepen.io/bradfrost/full/zhCwd" target="_blank">this</a> three column gem from Brad Frost using CSS.

I structured this by placing columns 2 and 3 in <code>&lt;div&gt;</code> tags, and the main content in a <code>&lt;main&gt;</code> tag. Once getting everything in order as far as a mobile view, the issue I quickly ran into was getting the main content in the middle once I added a media query for larger screens. Before tackling this thing I assumed I would be floating them all and Internet magic would sort everything out. Well, I was half right.

Floating all the elements was necessary, however, the second and main columns needed a bit more convincing to line up through the use of margin-left values.  

<em>Oh no! Unfortunately this image has been lost forever</em> 😱

<em>Oh no! Unfortunately this image has been lost forever</em> 😱

So, while I plan to dive into grids this week, I decided to punish myself first and do things this way. Brad Frost also has a <a href="http://bradfrost.github.io/this-is-responsive/patterns.html" target="_blank">collection of responsive patterns</a> that make perfect practice pieces.

<p data-height="268" data-theme-id="4899" data-slug-hash="kGvEh" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/kGvEh'>Responsive Columns </a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>

Happy column sorting!
