---
layout: post
title: Intro To Basic CSS Animation
date: '2014-01-24 12:15:51'

redirect_from:
    /intro-to-basic-css-animation/
---

As if CSS wasn't amazing and mysterious (at least to me) enough already, I find out that you can <em>move</em> things with it. I got chills just typing this.

I set out by trying to find some straight forward tutorials on the subject, but found this to be a more challenging task than anticipated. Many web tutorials for beginners seem to assume a certain level knowledge on behalf of the reader, even going so far as to say "obviously". Well, this just makes me a pouty panda because quite frankly I find exactly nothing obvious about CSS and HTML. Now, I'm not saying there should be a tutorial on CSS animation that first has to teach you HTML and CSS, but I'm not looking to do something<em> fancy</em> with CSS animation right now, I just need to know how to do <em>something</em>. All that being said, <a href="http://learn.shayhowe.com/advanced-html-css/transitions-animations" target="_blank">this</a> writeup by Shay Howe was the best read I came across on the topic so far. <em>
</em>

So let's start by making a circle. 

<em>Oh no! Unfortunately this image has been lost forever</em> 😱

Our next order of business:<strong> </strong>setting<strong> <a title="CSS Tricks" href="http://css-tricks.com/snippets/css/keyframe-animation-syntax/" target="_blank">Keyframes</a> </strong>in our CSS. The @keyframes rule is going to allow you to establish your animation on the selected HTML element. These are created with "@keyframes" followed by a name that ideally will describe what you are going to make the element do. Next you will need to define your keyframes; what shenanigans are you going to have this circle get into?!

<em>Oh no! Unfortunately this image has been lost forever</em> 😱

The first set of values define where you want this guy to be at the start of the page, followed by where you want him (or her) to be 500px into the page, and finally, where you want him (...or her) to be 1000px into the page. You will need to then assign this particular animation to the element that you are about to make awesome. Do this by going to the CSS for that element and assigning it an animation value. For example, <strong>animation: slide 3s infinite; </strong>This tells the element to absorb the values of the <em>slide</em> animation that you already defined, the duration to spend at each defined point, and for how long to do all this.

There is much, much more to say on the issue and lots of magic to be had, but hopefully this gets you moving (ha) and excited.

Also worth scrolling your eyeballs over: <a href="http://coding.smashingmagazine.com/2011/05/17/an-introduction-to-css3-keyframe-animations/" target="_blank">this</a> article at Smashing Magazine by Louis Lazaris. My mind was also blown recently by <a href="http://css-tricks.com/css-animation-tricks/?ref=heydesigner" target="_blank">this</a> tutorial at CSS-TRICKS by Zach Saucier.

See all the code <a href="http://cdpn.io/cDvqh" target="_blank">here</a>.

JB
