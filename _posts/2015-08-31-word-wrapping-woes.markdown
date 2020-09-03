---
layout: post
title: Word Wrapping Woes
date: '2015-08-31 14:04:08'

# Legacy
redirect_from:
    /word-wrapping-woes/
---

![This is seriously hard](/content/2015/Aug/wrap-4.png)

For whatever reason I seem to fall face-first into odd, unexpected text wrapping issues more often than I'd like.

I wrote an ebook and wrangling the text wrapping within the blocks of code was a nightmare. Sometimes the height of a block of text is higher than its restrictive container. Those too long URLs though!

*To hyphenate or not? I need to wrap this but not that. I need to hyphenate this but not that. This property won't work without that property. Why is the page still scrolling horizontally?!*

/me *flips table*

There are so many different situations we can run into here that all require a slightly different approach in styling, so this post will review the typical properties used to tackle such issues and review a couple real-world scenarios that seem to present especially tricky text wrapping/overflow issues.

### The Properties
There ends up being a number of "usual suspects" when resolving text wrapping issues through our CSS. Some are fairly straightforward and reasonable while others not so much. Some of them get the job done by themselves while others not so much.

So let's take a quick look.

#### `word-wrap`/`overflow-wrap`
The `word-wrap` property accepts two keyword values: `normal` (default) and `break-word`. These are in addition to the three global values of `inherit`, `initial`, and `unset`.

By default an especially long word will not break. The browser keeps this work intact which can seem fine until viewing on mobile. While the word's container may be responsive the word itself will spill out of these bounds and cause dreaded horizontal scrolling on the entire page.

Here's a very basic look at the default behavior here in the first example within the demo:

 <p data-height="200" data-theme-id="18341" data-slug-hash="2f7e98827821ad6902d91471df628b90" data-default-tab="result" data-user="jonitrythall" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/2f7e98827821ad6902d91471df628b90/'>Word-Wrapping Woes Demo 1</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

The second example within this same demo includes a declaration of `overflow-wrap: break-word;` instructing the browser to break the word before it has a chance to overflow beyond its container.

Important to note: [in the current CSS3 Text Specification draft](http://www.w3.org/TR/css3-text/#overflow-wrap) `word-wrap` has been replaced by `overflow-wrap` and accepts the same values. Here's [a look at the current browser support for this switch](http://caniuse.com/#search=overflow-wrap).

#### `word-break`
The `word-break` property, as I understand it, is for requiring a particular behaviour with CJK (Chinese, Japanese, and Korean) text *only*.

I used to use this on all the things for breaking long words but the correct property, unless working with CJK text, is the more general above mentioned `overflow-wrap`.

#### `hyphens`
The `hyphens` property tells the browser how to handle hyphenation when wrapping and accepts the following values: `none`, `manual`, and `auto`; which there is currently [unfortunate browser support](http://caniuse.com/#search=hyphens) for so you may have to fire up FireFox here.

A value of `none` ensures that words are *never* hyphenated at line breaks.

`manual` hyphenation will only break words at a line break when there is a character in place that directs this. Such specification can be achieved  through either a *hard* or *soft* hyphen literally being included at a specific location in the markup.

A hard hyphen, `&#45;`, will instruct a word to break at a specific location when necessary, but renders on the screen regardless of whether or not it's needed.

A soft hyphen, `&shy;`, accomplishes this same thing but doesn't actually render a hyphen on the screen, which is generally preferred.

A value of `auto` dictates that words can be broken at either specified locations or as is permitted automatically by language-appropriate hyphenation resources (if provided by the browser). *Hyphenation is language specific and the `lang` attribute needs to be defined for the document.*

#### `white-space`
We all have our favorite "break glass in case of emergency" CSS properties that we can trust to get us out of tricky situations; see also `overflow: hidden` and `display: none`. For me, the `white-space` property is just that.

This property establishes how white-space (spaces, tabs, hard returns) within an element is handled, which can prove to be incredibly helpful in some possibly surprising circumstances like troubleshooting and gaining more control of `table` cell content.

There are five property specific values here: `normal` (default), `nowrap`, `pre`, `pre-wrap`, and `pre-line`.

The demo below provides a glimpse into these values in action; be mindful of the extra spacing included in the markup.

<p data-height="268" data-theme-id="18341" data-slug-hash="8d0b9da990348f6bf7f2b57da693b7e5" data-default-tab="result" data-user="jonitrythall" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/8d0b9da990348f6bf7f2b57da693b7e5/'>Word-Wrapping Woes Demo 2</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

By default white-space collapses and lines are broken to fit within the container; as shown in example 1 of the demo where there is extra space added within the text but not maintained when rendering.

`nowrap`, example 2, also disregards this extra space but alternatively does not break the line of text according to container bounds.

`pre` maintains the extra space within the markup and does not break the line, as shown in example 3 from the demo above.

Example 4, `pre-wrap`, shows that this value maintains the added white-space but does force the line to break.

`pre-line` collapses white-space (except for new lines) *and* forces the link of text to fit within the container, as shown in the fifth and final example.

*CSS-Tricks has a [handy table](https://css-tricks.com/almanac/properties/w/whitespace/) that helps summarize all this.*

### Code Blocks
Blocks of code wrapped in `pre` tags do not wrap by default. This can cause a lot of messes with blog posts and technical ebooks on mobile, for example.

From my experience the solution here generally depends on the language within the `pre` and overall intentions, but these issues can often be resolved via forced wrapping (with no hyphenation!) or horizontal scrolling. This may take a bit of trial and error though as the exact combination of properties needed will vary by browser. *Be sure that any overriding `white-space` values do not cause collapsing as this will interfere with the code's syntax.*

I've also run into responsive issues with [gist](https://gist.github.com/)  code that are especially tricky because of the `table` aspect. In these instances I often find I have to apply special styling to the table's *container* to override.

### Ellipsis That Make Sense
IMHO the `text-overflow: ellipsis;` CSS declaration is kind of lame. It's super high maintenance and only works when combined with a bunch of other properties. It also is only valid in regards to a single line of text which makes it especially meh.

There's a jQuery plugin, [dotdotdot](http://dotdotdot.frebsite.nl/), that will create ellipsis when necessary for *multiple* lines of text and you can even add a link at the end for continued reading.

Here's a quick peek:

<p data-height="300" data-theme-id="18341" data-slug-hash="9b097c2cb8479dba75f55fe7605df197" data-default-tab="result" data-user="jonitrythall" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/9b097c2cb8479dba75f55fe7605df197/'>9b097c2cb8479dba75f55fe7605df197</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

### Super Specific Break Location
Sometimes we want our words to break but *only* in very specific places that make sense to us, anding an additional layer of complexity; how do we communicate these break points to the browser?

This is achieved through the use of soft or hard hyphens, as discussed easier, placed within the markup at the location.

In supporting browsers, the following will ensure that *when necessary* this line breaks where the shy hyphenation, `&shy;`, is included:

	Hey what did you do this we&shy;ekend? I painted some pottery, it was p neat.

### Too Long Links
I ran into the too long link problem frequently when, again, preparing an ebook (yes, ebook publishing is the literal worst) with lots of whole links in the footnotes.

By default this will not break and will cause all kinds of trouble on smaller screens. The URL needs to break when appropriate but without hyphenation, as that would render to link invalid. Another important thing to be mindful of here is to be careful where this is applied as it will break all words, not just URLs, if you let it.

`overflow-wrap: break-word;` on the link will ensure the URL breaks at the container's bounds and prevent overflow, though [cross browser support isn't as straightfoward](https://css-tricks.com/snippets/css/prevent-long-urls-from-breaking-out-of-container/) as we might hope for.


### Wrap-Up (HA!)
It can be tricky to get *just the right combination* of these properties lined up to resolve certain exceptional situations that arise, but having a better handle on the options and a heads-up on notorious examples definitely helps take away some of the guess work.

![Thanks for reading](/content/2015/Aug/end-3.png)
