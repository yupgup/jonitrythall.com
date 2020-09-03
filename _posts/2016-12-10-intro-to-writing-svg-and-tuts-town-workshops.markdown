---
layout: post
title: Intro To Writing SVG And Tuts+ Town Workshops
date: '2016-12-10 19:01:26'

# Legacy
redirect_from:
    /blog/blog/intro-to-writing-svg-and-tuts-town-workshops/
---

Recently I spent some time gathering all my in-person workshop materials into single GitHub repositories for “Intro to Writing SVG” and “Tuts+ Town: Creating Our First Website” and thought I would share some details on these.

Each workshop has a full and mini version to accommodate different time blocks I have been presented with at schools and Girl Develop It events. The mini versions either eliminate a non-essential section or provide a shortcut, of sorts, in how that section is approached.

I’ll just jump right in to some details about each one, mention where to find all the materials, and include a few bits of advice on conducting workshops in general.

### Intro To Writing SVG
**[View all materials on GitHub](https://github.com/jonitrythall/svgworkshop)**.

This workshop is based on a book I wrote a couple years ago, [Pocket Guide to Writing SVG](http://svgpocketguide.com/book/). It starts by touching on what SVG is and why it’s so important and beneficial to use on the web. The intro is quickly followed with syntax and document structure basics. Students are then able to write and edit graphics in the browser and get started with SVG text.

This was created for beginner adults that have some basic knowledge of HTML/CSS. This version is 2.5 hours long and consists of a presentation with lots of hands-on demos with instructions on CodePen.

![Screenshot SVG rectangle code](/content/2016/12/Screen-Shot-2016-12-09-at-9-09-56-AM.png)

![Screenshot SVG text code](/content/2016/12/Screen-Shot-2016-12-09-at-9-11-46-AM.png)

#### The Mini Version
**[View all materials on GitHub](https://github.com/jonitrythall/minisvgworkshop)**.

![Photo of GDI hackathon](/content/2016/12/FullSizeRender.jpg)

This version is 1 hour long, with the main difference being the elimination of the coordinate system and text sections. Students get started almost immediately with base demos to write basic shapes and edit stroke attributes.

![Illustration of different stroke end options](/content/2016/12/strokelinecap.png)
![SVG grapes with dashed outline](/content/2016/12/strokedasharray.png)

The main goal here becomes piquing interest and leaving students with the resources necessary to further explore this on their own outside of this workshop time.  

### Tuts+ Town Workshop: Creating Our First Website
**[View all materials on GitHub](https://github.com/jonitrythall/tutstownworkshop)**.

![Photo of Joni Trythall teaching](/content/2016/12/IMG_2950.JPG)

This workshop is based on a web design for kids series I created last year for Tuts+ called [Tuts+ Town](https://webdesign.tutsplus.com/series/web-design-for-kids--cms-823). After a brief introduction on how the web and files work it walks students through the basics of creating their own website with HTML and CSS through a highly visual presentation and demos.  

The full curriculum on Tuts+ covers layout, typography, color theory, content, whitespace, and visual hierarchy as well which serves as a great resource to point students to for further learning.

![](/content/2016/12/Screen-Shot-2016-12-09-at-3-38-58-PM.png)

*If you have never created materials for kids before and not sure where to start [I wrote a bit about that last year as well](http://jonibologna.com/designing-web-tutorials-for-kids/).*

#### The Mini Version
**[View all materials on GitHub](https://github.com/jonitrythall/minitutstownworkshop)**.

There are a lot of changes that have to happen to make this work within a condensed timeframe, with the main one being that [CodePen](http://codepen.io/) is used and eliminates the folder/file structure section (so internet is now required).

![Illustration of CSS syntax](/content/2016/12/Screen-Shot-2016-12-09-at-3-58-42-PM.png)

The catch, however, is that all students will have to have a CodePen account prior to the workshop. I recently tried having all students log in to the same account that I created specifically for the class and cannot recommend this approach at all. The tl;dr version of how this played out is that there were major sign in issues and the live preview never loaded for anyone.

The tricky part is that they will need an email address but I have found that kids this age usually have a school email, so just double check with the teacher that this setup would be appropriate.

![Illustration representing linkage of HTML and CSS docs](/content/2016/12/Screen-Shot-2016-12-09-at-4-00-17-PM.png)

While understanding proper folder and file structure is of course crucial eventually the most important part of this initial, mini workshop is getting the students to a point where they can *do something* and see the results on the screen as quickly as possible. Just be sure to add a resource to your reference site (which I will talk a bit more about soon) that explains this process in more detail; like the [second post of the Tuts+ Town series](https://webdesign.tutsplus.com/tutorials/web-design-for-kids-getting-ready-to-build-a-website--cms-23762).

### General Advice
I wish I had something profound to say about the difference between teaching kids versus adults but the truth is I haven’t noticed many, so here is my general advice for conducting workshops for students of all ages:

#### Move Things
* Start each workshop by showing students something *awesome*, depending on the context a basic, fun CSS animation from CodePen can do the trick. For kids I usually refer to a couple of my own like [Franklin](http://codepen.io/jonitrythall/pen/bivaG) or [Nora](http://codepen.io/jonitrythall/pen/xGBNOE), and for adults I usually dig up some wild UI animations like this [Bubble Layout](http://codepen.io/sol0mka/pen/yNOage) by [LegoMushroom](http://codepen.io/sol0mka/).

There are truly few things as delightful as showing a child something that’s moving across the screen and letting them know they can absolutely learn how to make this happen with some basic, foundational web design knowledge.

<p data-height="300" data-theme-id="11708" data-slug-hash="GpVryK" data-default-tab="result" data-user="jonitrythall" data-embed-version="2" data-pen-title="Weird Circle Loader" class="codepen">See the Pen <a href="http://codepen.io/jonitrythall/pen/GpVryK/">Weird Circle Loader</a> by Joni Trythall  (<a href="http://codepen.io/jonitrythall">@jonitrythall</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

Web design and development is an amazing artistic outlet and presenting it exclusively within the context of traditional website may make it challenging to make this connection. This approach helps show the potential of this space and speaks to the fact that there are so many different avenues you can take once you learn some foundational bits.

#### Concepts to Visuals
This is hard stuff. It’s one thing to *tell* someone how the internet works, for example, and quite another to *show* them. Always show students what you are talking about.

![Illustration of how the web works](/content/2016/12/Screen-Shot-2016-12-09-at-4-01-02-PM.png)

The best way to get comfortable with how to approach this is by looking through some infographics or comic based coding books. Here are the books I referenced when creating Tuts+ Town and can recommend:

* [Information Graphics: Human Body](https://www.amazon.com/Information-Graphics-Human-Simon-Rogers/dp/0763671231/ref=sr_1_1?ie=UTF8&qid=1481395104&sr=8-1&keywords=information+graphics+human+body)
* [Information Graphics: Space](https://www.amazon.com/Information-Graphics-Space-Simon-Rogers/dp/0763677698/ref=sr_1_1?ie=UTF8&qid=1481395127&sr=8-1&keywords=information+graphics+space)
* [Information Graphics: Animal Kingdom](https://www.amazon.com/Information-Graphics-Kingdom-Simon-Rogers/dp/0763671223/ref=sr_1_1?ie=UTF8&qid=1481395142&sr=8-1&keywords=information+graphics+animal+kingdom)
* [Infographic Guide To Life, The Universe, and Everything](https://www.amazon.com/Infographic-Guide-Universe-Everything-Guides/dp/1844037886/ref=sr_1_1?ie=UTF8&qid=1481395171&sr=8-1&keywords=infographic+guide+to+life+the+universe+and+everything)
* [Build Your Own Website: A Comic Guide to HTML, CSS, and Wordpress](https://www.amazon.com/Build-Your-Own-Website-WordPress/dp/1593275226/ref=sr_1_1?ie=UTF8&qid=1481395192&sr=8-1&keywords=comic+guide+build+your+own+website)

![Photo of infographic books](/content/2016/12/FullSizeRender-1.jpg)

#### Establish Base Materials
The sooner students can make an impact and view changes on a screen the better. There is always time to go back and thoroughly learn about file structure, for example, but it’s important to get them excited enough initially to want to bother with learning those potentially not so glamorous details. Having base code ready to build from makes this all possible.

#### Base Tools
Always work closely with teachers or students to make sure their computers are ready for the workshop, which will save a bunch of time and frustration for everyone the day of the workshop.

Some things to consider:

* All students should have a modern browser installed; I always recommend Chrome.
* A decent, free text editor like [Atom](https://atom.io/).
* Send all files and folders ahead of time so that they are on computers and ready.
* Internet access if using CodePen.
* Also if using CodePen, having students sign up for accounts beforehand will save time.

#### Recruit Teaching Assistants
While I always suggest having TAs in any workshop you will likely need 2-3 times more with kids depending on the size of the class. I have recruited TAs through work, through the school or organization I am conducting the workshop for, and by asking local friends or acquaintances.

I can’t recommend ever conducting any sizable workshop without access to TAs. The entire experience will be in jeopardy as students will fall behind as you try to keep to a schedule because their questions will go unanswered. It’s important to make sure all students are ready before progressing to the next portion of a curriculum and this will become impossible without TAs.

Send all materials to TAs before the class and put together a physical cheatsheet for the day of the workshop with a list of relevant links and sign in information. Also, don’t forget to send along a thank you email or postcard after!

![Photo of TAs assisting with a class taught by Joni Trythall](/content/2016/12/trythall_class_1.jpg)

#### Follow-Up Materials  
Be sure to let students know where they can go from the workshop. You are with them for a very short amount of time and presenting them with an enormous amount of complex information. Having a place to go after the workshop to take another look at slides and have some direction on where to go next is hugely reassuring. I also include my contact information for questions.

It is easy to potentially overthink this but strongly fight the urge or you may find the task too burdensome to complete. This should be a very simple page with some headings and links to:

* Any materials used during the workshop.
* List of references for furthering learning organized by general topic. With the exception of books I am sure to only list free resources here.
* Mention of how to host their work on the web to be able to share with friends and family. For kids I recommend [Neocities](https://neocities.org/) for this and wrote more [about the specifics here](https://webdesign.tutsplus.com/tutorials/web-design-for-kids-wrap-up--cms-24379).
* A list of miscellaneous fun or especially interesting design/development things on the web.

![Screenshot of Tuts Town reference site](/content/2016/12/Screen-Shot-2016-12-09-at-8-50-29-AM.png)

#### Finally, Bring Goodies
*Everyone* loves stickers. Huge bonus points for cute animal characters.

![Joni Bologna stickers](/content/2016/12/Cy20fKUWgAASNXm-1.jpg)

I bring stickers and buttons to every event I go to and workshops are no exception. They get people excited and talking and allows them to leave with something fun to show others; it really adds to the overall experience.

![Future web designer stickers](/content/2016/12/CxV5AZHUcAQMjOS-1.jpg)

*Something to also think about: cookies*

### Happy Workshopping  
I hope these materials, notes, and general workshop advice prove helpful for anyone not quite sure where to start. Feel free to fork these materials and customize them to suite your scenario.

Best of luck and I’d love to hear about any especially fun or interesting workshop tips you many have yourself [on Twitter](https://twitter.com/JoniTrythall).
