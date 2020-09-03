---
layout: post
title: It's All in Your <code>head</code>
date: '2015-01-05 14:12:18'

# Legacy
redirect_from:
    /blog/blog/its-all-in-your-head/
---

I was recently working on [a small new project](http://jonitrythall.github.io/appleproject/) (with apples) and found myself feeling that the bulk of content witin the <code>head</code> tag was slightly comical. What exactly is all this stuff that (mostly) isn't even seen by the site's user? What's essential? What's just taking up space? What does it all *do*?

I thought it might be helpful to touch on these <code>head</code> tag options, but not so much that this turns into a preachy SEO post.

![Stick figure labeled with head, body, and footer html tags](/content/2015/Jan/head-01.jpg)

### head

The <code>head</code> tag is where information about an HTML document is placed. The <code>title</code> element lives here and you can choose to also add <code>meta</code>, <code>style</code>, <code>script</code>, <code>base</code> and <code>link</code> elements within the <code>head</code>, located right after your opening <code>html</code> tag.

Here's the *very* basic (though not minimal) structure of a site's <code>head</code> that simply has a title, character encoding, and link to a style sheet:

    <html lang="en">
        <head>
        	<meta charset="UTF-8">
            <title>An Apple A Day</title>
            <link type="text/css" rel="stylesheet" href="apples.css">
        </head>
        <body>
            <!-- stuff about cute apples -->
        </body>
    </html>

A proper <code>head</code>, however, will contain much more information here, so let's take a closer look at what's already there and what can be added.

#### title
Having a <code>title</code> for your HTML document is required, and for good reason. It is the name that will represent your site on a browser tab, in search engine results, and in someone's bookmarked site list.

Make it descriptive. Chose a title that truly represents your page's content, as it will be what search engines primarily use to categorize your site. A proper title is important for both SEO and social sharing.

An ideal title would be structured to follow something like this:

**Primary Keyphrase - Secondary Keyphrase | Brand Name**

Also keep in mind that depending on the browser only a certain portion of your title may be displayed in the tab. Google limits the title to a pixel width of 512 (about 60 characters) rather than by a strict character count.

##### hyphens & pipes

Using hyphens or pipes as separators in a title helps in terms of readability when you have more than one keyphrase in your title. There seems to be a bit of debate around this, but as far as I can tell neither of these is better than the other in terms of SEO.

#### link

A <code>link</code> element is ridiculously powerful. It specifies relationships between your document and an external resource. Examples of this would be linking to a style sheet, like included in our little example above, or including a link to a specific font you want to use (such as Google Fonts or Font Awesome).

The attributes used here will depend on what you are linking to your document, but there are a few that are used most often:

##### href
Specifies the URL of the linked resource. This can be to an image for a favicon or to a Google Font URL, for example.

##### rel
This attribute names the *relationship* of the linked resource to the document. The relationship must be a space-seperated list of [link type values](https://developer.mozilla.org/en-US/docs/Web/HTML/Link_types), like our <code>rel="stylesheet"</code> in the first example.

##### type
The <code>type</code> attribute defines the type of content linked to. The value here should be a specific [Internet media type](http://en.wikipedia.org/wiki/Internet_media_type#Type_text), which will most often be <code>text/css</code>.

#### meta

You may find that <code>meta</code> will take up a large portion of your <code>head</code> space along with <code>link</code>. The <code>meta</code> element provides structured metadata about the document that isn't suited to be used within any of the other elements.

While data within <code>meta</code> will not impact your search engine ranking, it will show up in the results.

Here's a look at a particular <code>meta</code> element used on my apple site and the Google search result.

    <meta name="description" content="An apple themed daily coding exercise project by Joni Trythall.">

![Screenshot of Google search results reflecting set metadata of An Apple A Day site](/content/2015/Jan/Screen-Shot-2015-01-03-at-8-40-17-AM.png)

##### name & content
The <code>name</code> attribute within the <code>meta</code> element defines the name of the data to be included within the <code>content</code> attribute. The most commonly used names here will be <code>description</code>, <code>author</code>, and <code>keywords</code>.

##### charset
The <code>charset</code> attribute within a <code>meta</code> element identifies the character encoding used for the page, which converts a sequence of bytes into a sequence of characters.

A value of <code>UTF-8</code> is encouraged here as it well supported and can be used for any international language, for example.

##### Responsive meta Tag
You will want to [include some viewport directives](https://developer.mozilla.org/en-US/docs/Mozilla/Mobile/Viewport_meta_tag) within a <code>meta</code> tag **for responsive sites**. The following snippet tells the browser size to render the page according to the device width:

    <meta name="viewport" content="width=device-width, initial-scale=1">

#### base
The <code>base</code> element specifies the base URL to use for all relative URLs within the document and can [set default link targets](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/base). Because of this fairly domineering role the element plays, there can only be one of them in a document and it should ideally be placed soon after the opening <code>head</code> tag.

Here is a quick look at how this would be used:


    <head>
    	<base href="http://www.jonibologna.com/assets/">
    </head>
    <body>
    	<img src="pigimage.svg" alt="Pig!" />
    </body>

The loading path for the image would be: <code>http://www.jonibologna.com/assets/pigimage.svg</code>

This being said, you may find that you are not using this element very often. <code>base</code> will affect *all* the URLs in the document going forward and any link not needing association with it will need to be overridden, at which point it may be better practice to just remove the element from the <code>head</code>.  

#### script
The <code>script</code> element is used to embed or reference a script within the document. JavaScript files are generally included towards the end of the document before the closing <code>body</code> tag. It will sometimes be necessary, however, to include this script reference in the <code>head</code>, like if the script is needed to help render the HTML doc itself or determine its behavior in a specific way.

##### src
If you not writing inline script, you will need to reference the URL of the external file with the <code>src</code> attribute.


##### type
The <code>type</code> attribute within <code>script</code> identifies the scripting language of the embedded code or external file being referenced. While **this defaults to an assumption of JavaScript** when not specifically spelled out, you may find yourself needing to [use a not as common language](https://developer.mozilla.org/en-US/Add-ons/Code_snippets/Rosetta).

### Conclusion
So, it really is all in your head. It may be tempting to rush through this bit in your HTML document and get to the good stuff (layout! images! color!) but it's pretty important in terms of SEO, accessibility, and the overall functioning of your site to make sure this bit has received sufficient attention.

While this post by no means covers all the attribute options for these <code>head</code> related elements, it should help you get a bit more comfortable with all that code listed seemingly before our site even gets started.
