---
layout: post
title: Grids & Flexbox Magic
date: '2014-01-31 20:11:00'
published: false

redirect_from:
    /blog/grids-flexbox-magic/
---

Grids. I have been putting off grid systems for a while now. Because I am a glutton for punishment and like to do things the hard way I guess. I also often get distracted coloring. Well, today is finally the day. I will color tomorrow.

A grid is defined as a structure comprising a series of horizontal and vertical lines which intersect and are then used to arrange content. Essentially, it's a way for designers to more easily structure a page for optimal readability. Using a grid is going to allow you to produce designs that are proportionate and uniform. It's about math, but not scary math. Grids are going to allow you to create a page based on ratios and equations, rather than a layout that <em>feels</em> like it works. This <a href="http://www.markboulton.co.uk/journal/five-simple-steps-to-designing-grid-systems-preface" target="_blank">guide by Mark Boulton</a> is one of the more detailed introduction to grids I came across. OK, so I'm sold on using grids, now what?

A grid system. I chose to start with Flexbox here. To get a better concept of how to design with grids and use Flexbox I drew up a simple gird layout to build for a mobile screen. I need to practice something as I'm learning it, otherwise it's complete gibberish.

<em>Oh no! Unfortunately this image has been lost forever</em> 😱

Once I got my content code in order, it was time for Flexbox. The Flexbox (Flexible Box) Layout will help you lay out your page and manage your containers more efficiently than doing it all "manually" with CSS alone. Let's just say "good day to you" overflow: hidden. To enable Flexbox add <code>display: flex;</code> to the parent element CSS.

This is going to switch the body element to use the flexbox layout instead of the regular block layout. All elements in the flow of the document (not absolutely positioned elements!) will now become flexible. Woo!

OK, now we need to give it more specific orders. What direction are we working in? Are there single or multiple lines involved? Add these specifics to the parent element. Chris Coyier wrote an article recently <a href="http://css-tricks.com/snippets/css/a-guide-to-flexbox/" target="_blank">that walks you through your Flexbox command options</a>. It's kind of an amazing resource and will give you a better idea of how to get started with Flexbox properties.

<em>Oh no! Unfortunately this image has been lost forever</em> 😱

We have now said that we are using flex layout, we are working left to right, and using multiple lines. We are so bossy. I then established the widths of the elements by spelling out how many of a particular class should be used in a row, and then Flexbox took it from there.
<p data-height="268" data-theme-id="4899" data-slug-hash="byDhg" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/byDhg'>Intro to Flexbox</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>

You can click on the "Result" tab to see the flexible magic that happened.

I am still trying to get a better understanding of all the capabilities of this thing (...pretty sure this applies to life in general as well) but I wanted to share what I dove into today just incase someone else finds this stuff as flippin' amazing as I do. For further reading, this <a href="http://coding.smashingmagazine.com/2013/05/22/centering-elements-with-flexbox/#top" target="_blank">article by David Storey at Smashing Magazine</a> was a real treat.

Deep in the Internets I also found this <a href="http://the-echoplex.net/flexyboxes/?fixed-height=on&amp;legacy=on&amp;display=flex&amp;flex-direction=row&amp;flex-wrap=wrap&amp;justify-content=flex-start&amp;align-items=flex-start&amp;align-content=flex-start&amp;order%5B%5D=0&amp;flex-grow%5B%5D=0&amp;flex-shrink%5B%5D=1&amp;flex-basis%5B%5D=auto&amp;align-self%5B%5D=auto&amp;order%5B%5D=0&amp;flex-grow%5B%5D=0&amp;flex-shrink%5B%5D=1&amp;flex-basis%5B%5D=auto&amp;align-self%5B%5D=auto&amp;order%5B%5D=0&amp;flex-grow%5B%5D=0&amp;flex-shrink%5B%5D=1&amp;flex-basis%5B%5D=auto&amp;align-self%5B%5D=auto" target="_blank">flexbox playground and generator</a>. Let's just say it makes for a wild Friday night. I would know.

Happy flexing!
