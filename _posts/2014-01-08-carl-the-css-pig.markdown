---
layout: post
title: Carl The CSS Pig
date: '2014-01-08 13:17:11'

redirect_from:
    /carl-the-css-pig/
---

Guess what? I am going to be completely unoriginal here and admit that I think CSS positioning is a total pain to get the hang of. I assume tears and blood have been shed over this topic for years and years. Or maybe it's just my tears and blood being shed. Either way, I feel like it should be discussed.

I set out to create an illustration, of sorts, using HTML and CSS to practice positioning. I chose a pig, obviously, and ran into the following challenges which I needed to investigate further: image rotation, creating a CSS triangle, and absolute vs. relative positioning. Also, his name is Carl. 

<em>Oh no! Unfortunately this image has been lost forever</em> 😱

All the shapes were created by styling divs. I placed all the divs within a main div, being the Carl's head. I positioned his head relatively, and all other parts absolutely. I found <a href="http://designshack.net/articles/css/the-lowdown-on-absolute-vs-relative-positioning/" target="_blank">this</a> article helpful as a general overview of the issue.

I had to learn how to create triangles using CSS in order for Carl to have ears. CSS Tricks provides a useful <a href="http://css-tricks.com/snippets/css/css-triangle/" target="_blank">article</a> on this. Assuming your div has a class of "arrow-up", your CSS would look like this:<a href="http://jonibologna.com/wp-content/uploads/2014/01/Screen-Shot-2014-01-08-at-12.11.22-PM.png"><img class="aligncenter size-full wp-image-607" alt="Screen Shot 2014-01-08 at 12.11.22 PM" src="http://jonibologna.com/wp-content/uploads/2014/01/Screen-Shot-2014-01-08-at-12.11.22-PM.png" width="634" height="234" /></a>

In order to manipulate Carl's ears I needed to rotate the second one that I created to mirror the original. While they should have the same class, the second ear with need an additional class in order to select it separately for this alteration.  I found <a href="http://www.w3schools.com/cssref/css3_pr_transform.asp" target="_blank">this</a> to be helpful concerning rotation, and below is the CSS:<a href="http://jonibologna.com/wp-content/uploads/2014/01/Screen-Shot-2014-01-08-at-12.07.59-PM.png"><img class="aligncenter size-full wp-image-606" alt="Screen Shot 2014-01-08 at 12.07.59 PM" src="http://jonibologna.com/wp-content/uploads/2014/01/Screen-Shot-2014-01-08-at-12.07.59-PM.png" width="391" height="377" /></a>

While I plan to keep going with this, I needed a break for the day. Creating life is hard work.

View <a href="http://cdpn.io/GFxlz" target="_blank">this little guy</a> on CodePen.
