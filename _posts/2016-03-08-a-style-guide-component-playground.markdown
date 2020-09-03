---
layout: post
title: A Style Guide Component Playground
date: '2016-03-08 14:47:49'

# Legacy
redirect_from:
    /a-style-guide-component-playground/
---

![Component playground illustration](/content/2016/Mar/Screen-Shot-2016-03-07-at-9-34-02-PM.png)

Style guides are very challenging to build, though the initial idea of creating one always sounds like a total dream.

You have to create a bunch of components that are **completely** flexible, preferably CSS only, are well documented, and perform well across browsers. But they greatly contribute to brand consistency and rapid prototyping so we understandably :swoon: endlessly.

I spent a lot of time last year refining a style guide I inherited and rebuilding many components. It quickly becomes apparent that testing the flexibility of these components and experimenting to anticipate odd situations was an essential part of its sustainability.

**Many design and development limitations here can be anticipated and resolved through easy adoption of a &ldquo;playground&rdquo;, that is, an *outside* place to test and tinker with core style guide components.**

Let&rsquo;s take a quick look at the needs, a specific problem I ran into, and the proactive approach I then implemented going forward as a result.

### Needs: Flexibility & Convenience

^^ That&rsquo;s really what it&rsquo;s all about.

Bits of UI that are included within a style guide need to potentially accommodate several products. Sometimes mobile use will be essential, sometimes the layout will be different, sometimes the content and data will be super lengthy, sometimes a combination of these UI pieces is needed.

Whatever the situation the style guide needs to be ready for it. Creating custom UI per project is a huge time sink and challenges the brand consistency we all work so hard to maintain.

Displaying all the appropriate code (both markup and styling) to grab and go is also incredibly handy.

![Screenshot of code samples in style guide](/content/2016/Mar/Screen-Shot-2016-03-07-at-8-55-18-PM.png)

The user shouldn&rsquo;t have to worry too much about testing, digging for code, or writing a bunch of CSS; if a style guide requires too many overrides then it&rsquo;s not a successful project.

In keeping these needs/goals in mind I quickly ran into my first roadblock. I needed to put a `table` inside of tabbed navigation, but each of these on their own were too fragile to make this work.  

#### Example Problem: Tabs

We wouldn&rsquo;t want someone to have to get these tabs *just so* in the event that they need more or fewer tabs than what is demoed in the guide. My priority here was to build tabs with flexbox that were smart enough to readjust when the markup was removed.

<p data-height="268" data-theme-id="18341" data-slug-hash="b85314201c805e74edca1ab5791ed522" data-default-tab="result" data-user="jonitrythall" class="codepen">See the Pen <a href="http://codepen.io/jonitrythall/pen/b85314201c805e74edca1ab5791ed522/">Flexible Tabs</a> by Joni Trythall  (<a href="http://codepen.io/jonitrythall">@jonitrythall</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

If fewer than the displayed five tabs are needed all the user has to do is remove the appropriate `input`, `label`, and content `div` elements. The tabs will then readjust accordingly without having to fuss around with the CSS *at all*.

#### Example Problem: Tables
![Screenshot of new HTML table](/content/2016/Mar/Screen-Shot-2016-03-07-at-1-46-12-PM.png)

The second issue I ran into was in regards to the basic `table`.

I needed to build a `table` that was responsive but also didn't force anyone to scroll to reveal data on mobile. Given these constraints and the inherent challenging nature of HTML tables the only option seemed to be restructuring the data on smaller screens.

The approach I decided to take here was largely inspired by [this table by Geoff Yuen](http://codepen.io/geoffyuen/pen/FCBEg).

<p data-height="268" data-theme-id="18341" data-slug-hash="05dc299c7751f8f77776c368930d4c70" data-default-tab="result" data-user="jonitrythall" class="codepen">See the Pen <a href="http://codepen.io/jonitrythall/pen/05dc299c7751f8f77776c368930d4c70/">Basic Table </a> by Joni Trythall  (<a href="http://codepen.io/jonitrythall">@jonitrythall</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

*[Jump into CodePen to demo the full experience](http://codepen.io/jonitrythall/pen/05dc299c7751f8f77776c368930d4c70) by adjusting the browser window.*

The content still says the same thing but it&rsquo;s displayed in a much friendly way when the screen size warrants it.

I was even able to [put a browser matrix together](http://codepen.io/jonitrythall/pen/aNNoZM/) with it, utilizing `display: none` on mobile for cells without content:

![Screenshot of browser matrix](/content/2016/Mar/Screen-Shot-2016-03-08-at-9-37-48-AM.png)

#### Example Use Case: Tables in Tabs
![Screenshot of a table in tabs](/content/2016/Mar/Screen-Shot-2016-03-07-at-1-45-46-PM.png)

Through experimenting and testing it became clear that with this new solid foundation in place the components were much more flexible and handled being injected into other components with much more class and sophistication.

In the example below the new `table` can be included within the new flexible tabs. The entire scenario, and others like it, can then live within a playground and be tested according to whatever browser matrix you are working with.

<p data-height="268" data-theme-id="18341" data-slug-hash="ZGdwOM" data-default-tab="result" data-user="jonitrythall" class="codepen">See the Pen <a href="http://codepen.io/jonitrythall/pen/ZGdwOM/">Responsive Table in Flexible Tabs</a> by Joni Trythall  (<a href="http://codepen.io/jonitrythall">@jonitrythall</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

### The Component Playground
This is not meant to be anything fancy, and perhaps you&rsquo;ll have a different name for it. It&rsquo;s simply a place to use the components from the style guide *outside* of the style guide and tinker with them like crazy.

It can be as straightforward as a long form test case for cross browser testing purposes and forcing those not ideal (but likely) situations.

What happens when you put the established spinner/loader inside of a button? How will tooltips perform on smaller screens or even within a `table`? ... Let&rsquo;s try all these out for science and within context.

#### Documentation
Don&rsquo;t forget to document any interesting findings or helpful how-tos within the style guide itself. It&rsquo;s an invaluable teaching tool and it can be helpful to think in terms of the user experience just as you would with any other project.

The users of a style guide can be developers, engineers, or marketing professionals; all with varying levels of tech skills. Making it as easy to use as possible and eliminating any surprises will be appreciated by all.

##### An Example

I was also tasked with rebuilding [an icon system with hundreds of SVG icons](https://ux.nowsecure.com/icons.html#svg). I was sure to break these down into manageable bits by creating a grouping system by fidelity level.

I also included special preset classes with instructions and diagrams; don&rsquo;t forget to include language on how to add to this collection in the project&rsquo;s README as well!

![Screenshot of sprite section in style guide](/content/2016/Mar/Screen-Shot-2016-03-07-at-3-36-11-PM.png)

![Screenshot of sprite section in style guide](/content/2016/Mar/Screen-Shot-2016-03-07-at-5-48-24-PM.png)

### Conclusion
In order for a style guide to be an efficient and realistic project for yourself or your team to take on putting the initial thoughtful work into the foundational components is crucial. A big part of making sure these pieces are flexible and convenient is through a testing playground; get weird with it and you&rsquo;ll save yourself bunches of time and headache later.

As a final note, don&rsquo;t forget that a style guide is a *guide*. Taking it too literally can often result in stifling the chance for all innovation going forward. If something isn&rsquo;t working in terms of design or development there has to be resources in place to keep it relevant. It is, afterall, a product in itself.
