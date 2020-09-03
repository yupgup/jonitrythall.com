---
layout: post
title: 'The overflow: hidden; Headache'
date: '2013-12-05 10:49:46'
---

I am posting on this partially because I am excited that I am potentially 30% on my way to understanding it, and partially because I have to write it down before I completely lose that 30% entirely from my brain. I could not understand what the heck this meant or what it was doing to the page. The best explanation I have gotten goes a little something like this: when you have floated elements within a contained, those elements are <em>partially</em> removed from the flow of the document. This in turn confuses the container (stupid container) and it collapses. You then need to trigger that contained into getting its act together and wrapping up those floated elements again. Depending on the senario, there are two ways to do this from what I can tell. You can add a footer to the page. This for some reason triggers that container to do it's job. It will expand to meet the footer, and in turn wraps those floated elements. Mostly, though, you would be using overflow: hidden. This will then trigger then container to do its job and contain those floated elements. I know, total sorcery.

I really like <a title="overflow: hidden article" href="http://colinaarts.com/articles/the-magic-of-overflow-hidden/" target="_blank">this</a> explanation as well. He explains that float containment with overflow:hidden is actually just a side-effect of what is happening, which helped ease my mind and stopped me from pressing for more exact explanations of that the hey was happening.

<a href="http://jonibologna.com/wp-content/uploads/2013/11/Screen-Shot-2013-11-30-at-12.27.27-PM.png"><img class="aligncenter size-full wp-image-454" alt="Screen Shot 2013-11-30 at 12.27.27 PM" src="http://jonibologna.com/wp-content/uploads/2013/11/Screen-Shot-2013-11-30-at-12.27.27-PM.png" width="1009" height="655" /></a>
<p class="codepen" data-height="268" data-theme-id="0" data-slug-hash="byvaH" data-user="jonitrythall" data-default-tab="result">See the Pen <a href="http://codepen.io/jonitrythall/pen/byvaH">HR Fragment Reproduction</a> by Joni Trythall (<a href="http://codepen.io/jonitrythall">@jonitrythall</a>) on <a href="http://codepen.io">CodePen</a></p>
OK, my nearing 30 brain better retain this once and for all.

Happy hiding! 