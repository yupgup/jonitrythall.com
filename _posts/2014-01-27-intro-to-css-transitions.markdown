---
layout: post
title: Intro To CSS Transitions
date: '2014-01-27 09:15:19'
published: false

redirect_from:
    /blog/intro-to-css-transitions/
---

I almost feel guilty spending time on this, as it seems like too much fun to be considered work or study time. I previously posted on <a href="http://jonibologna.com/2014/01/intro-to-basic-css-animation/" target="_blank">CSS animations</a> and thought that transitions were worthy of their own post. As with animations, I found <a href="http://learn.shayhowe.com/advanced-html-css/transitions-animations" target="_blank">this lesson by Shay Howe</a> to be especially helpful.

In the spirit of keeping things simple, I started off by making a circle. 

<em>Oh no! Unfortunately this image has been lost forever</em> 😱

The next step is establish what you will want this circle to do once someone hovers over it. We will do this by adding a pseudo class selector on the circle of <code>:hover</code>. There are other pseudo selectors you can use here, but we will use :hover for this example. Define what you will want it to look like when hovered over.

Now, back to the circle. You will need to add specific transition properties here. There are four transition related properties, including: transition-property, transition-duration, transition-timing-function, and transition-delay. You do not need to use all of these to generate a transition. In the code below we are telling the element what part will transition, how long it will take to transition, and to transition at a constant speed from one state to the other. If we added a transition-delay here it would delay the reaction time once the element is hovered over. 

<em>Oh no! Unfortunately this image has been lost forever</em> 😱

<p data-height="268" data-theme-id="4899" data-slug-hash="CveBd" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/CveBd'>Transition Practice </a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>

For further reading I found <a href="http://www.webdesignerdepot.com/2010/01/css-transitions-101/" target="_blank">this article at Web Designer Depot</a> to be pretty neat.

Happy transitioning!
