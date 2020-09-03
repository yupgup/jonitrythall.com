---
layout: post
title: Getting Sassy
date: '2014-01-17 14:03:43'

redirect_from:
    /getting-sassy/
---

Today is the day. <a href="http://www.webdesignerdepot.com/2013/11/the-beginners-guide-to-sass/" target="_blank">Intro</a> to <a href="http://sass-lang.com/guide" target="_blank">Sass</a>.

I wanted to hold off on Sass until I got a full grasp on CSS, in order to better understand its limitations and thus understand the need for Sass. Well, I am realizing more and more that ever fully understanding the ins and outs of CSS is near impossible. Especially for people like me that often get distracted <a href="http://cdpn.io/GFxlz" target="_blank">making pigs</a>. CSS continues to blow my mind each day, so hopefully Sass does not lead to a complete head implosion. Also, if there is a way I can make a more badass pig with code, well, I'm all about it.

Let's review some of the highlights.

<strong>Variables.</strong> Sass allows you to store frequently used CSS values. I can already imagine how this would be helpful in structuring consistent style on a site.

<em>Oh no! Unfortunately this image has been lost forever</em> 😱

<strong>Nesting. </strong>Sass allows you to nest your CSS selectors. This provides great visual organization, much like that of HTML. I already feel relieved by this, as reviewing my CSS can often cause me physical pain. However, knowing not to over-nest seems to be just as important as knowing how to; it is <a href="http://thesassway.com/beginner/the-inception-rule" target="_blank">suggested</a> not to go more than four levels deep. 

<em>Oh no! Unfortunately this image has been lost forever</em> 😱

<strong>Partials. </strong>You can <a href="http://thesassway.com/beginner/how-to-structure-a-sass-project/" target="_blank">create partial Sass files</a>, which allows you to separate your stylesheets into separate files. This file is then saved as a Sass file with a leading underscore: _partial.scss. This allows you to reuse frequently used styling.

<strong>Import.</strong> Sass streamlines the process of combining code documents; it pulls code from one document into another.

<strong>Mixins.</strong> These seem to be similar to variables. But more intense. These allow you to make groups of CSS declarations that you want to reuse throughout your site. To create a mixin you use the @mixin directive and give it a name. This will take a block of styles you created before and apply it to the selector of your choice using the @include directive. Apparently you can <a href="http://www.webdesignerdepot.com/2013/11/the-beginners-guide-to-sass/" target="_blank">include mixins within other mixins</a>, but I wanted to end the week on a fairly good note and needed to stop my research on this topic there.

<em>Oh no! Unfortunately this image has been lost forever</em> 😱

<strong>Extend. </strong>Using @extend allows you to share a set of CSS properties from one selector to another. This feature can apparently <a href="http://css-tricks.com/the-extend-concept/" target="_blank">be overused</a> often, so be aware of that. The following example demonstrates the use of @extend to apply some CSS values from the header to the "footer" text. You can continue additional styling from there, which essentially overrides those aspects of the @extend.

<em>Oh no! Unfortunately this image has been lost forever</em> 😱

View the entire code <a href="http://cdpn.io/CKbzx" target="_blank">here</a>. Also useful: Chris Coyier's <a href="http://css-tricks.com/sass-style-guide/" target="_blank">Sass Style Guide</a>, and <a href="http://alistapart.com/article/getting-started-with-sass/" target="_blank">this</a> article at A List Apart by David Demaree.

JB
