# HTML DOCUMENT STANDARDS

## Preparing for HTML

Now that we’ve learned about some of the most common HTML elements, it’s time to learn how to set up an HTML file.

HTML files require certain elements to set up the document properly. We can let web browsers know that we are using HTML by starting our document with a document type declaration.

The declaration looks like this:

```html
<!DOCTYPE html>
```

This declaration is an instruction, and it must be the first line of code in your HTML document. It tells the browser what type of document to expect, along with what version of HTML is being used in the document. For now, the browser will correctly assume that the html in `<!DOCTYPE html>` is referring to HTML5, as it is the current standard.

In the future, however, a new standard will override HTML5. To make sure your document is forever interpreted correctly, always include `<!DOCTYPE html>` at the very beginning of your HTML documents.

Lastly, HTML code is always saved in a file with an `.html` extension.

---

## **Table of Contents :**

<ul>
<li><a href="#tag-htmltag">The HTML tag</a></li>
<li><a href="#tag-htmlhead">The Head</a></li>
<li><a href="#tag-htmltitles">Page Titles</a></li>
<li><a href="#tag-htmlHyperlinks">Hyperlinks</a></li>
<li><a href="#tag-htmlcomments">Comments</a></li>
</ul>

### <a id="tag-htmltag" href="#tag-htmltag"><strong><em>The HTML tag :</strong></em></a>

---

The `<!DOCTYPE html>` declaration provides the browser with two pieces of information (the type of document and the HTML version to expect), but it doesn’t actually add any HTML structure or content.

To create HTML structure and content, we must add opening and closing `<html>` tags after declaring `<!DOCTYPE html>`

```html
<!DOCTYPE html>
<html></html>
```

Anything between the opening `<html>` and closing `</html>` tags will be interpreted as HTML code. Without these tags, it’s possible that browsers could incorrectly interpret your HTML code.

### <a id="tag-htmlhead" href="#tag-htmlhead"><strong><em>The Head :</strong></em></a>

---

The `<head>` element contains the metadata for a web page. Metadata is information about the page that isn’t displayed directly on the web page. Unlike the information inside of the `<body>` tag, the metadata in the head is information about the page itself.

The opening and closing head tags typically appear as the first item after your first HTML tag:

```html
<head> </head>
```

### <a id="tag-htmltitles" href="#tag-htmltitles"><strong><em>Page Titles :</strong></em></a>

---

A browser’s tab displays the title specified in the `<title>` tag. The `<title>` tag is always inside of the `<head>`.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>My Coding Journal</title>
  </head>
</html>
```

If we were to open a file containing the HTML code in the example above, the browser would display the words `My Coding Journal` in the title bar (or in the tab’s title).

### <a id="tag-htmlHyperlinks" href="#tag-htmlHyperlinks"><strong><em>Hyperlinks :</strong></em></a>

---

- #### Linking to Other Web Pages :

One of the powerful aspects of HTML (and the Internet), is the ability to link to other web pages.

You can add links to a web page by adding an anchor element `<a>` and including the text of the link in between the opening and closing tags.

```html
<a>This Is A Link To Wikipedia</a>
```

Wait a minute! Technically, the link in the example above is incomplete. How exactly is the link above supposed to work if there is no URL that will lead users to the actual Wikipedia page?

The anchor element in the example above is incomplete without the href attribute. This attribute stands for hyperlink reference and is used to link to a path, or the address to where a file is located (whether it is on your computer or another location). The paths provided to the href attribute are often URLs.

```html
<a href="https://www.wikipedia.org/">This Is A Link To Wikipedia</a>
```

In the example above, the href attribute has been set to the value of the URL https://www.wikipedia.org/. The example now shows the correct use of an anchor element.

- #### Opening Links in a New Window :

Have you ever clicked on a link and observed the resulting web page open in a new browser window? If so, you can thank the `<a>` element’s `target` attribute.

The target attribute specifies how a link should open.

It’s possible that one or more links on your web page link to an entirely different website. In that case, you may want users to read the linked website, but hope that they return to your web page. This is exactly when the `target` attribute is useful!

For a link to open in a new window, the `target` attribute requires a value of `_blank`. The `target` attribute can be added directly to the opening tag of the anchor element, just like the `href` attribute.

```html
<a href="https://en.wikipedia.org/wiki/Brown_bear" target="_blank"
  >The Brown Bear</a
>
```

In the example above, setting the target attribute to `"_blank"` instructs the browser to open the relevant Wikipedia page in a new window.

- #### Linking to Relative Page :

```
project-folder/
|—— about.html
|—— contact.html
|—— index.html
```

The example above shows three different files — **about.html**, **contact.html**, and **index.html** in one folder.

HTML files are often stored in the same folder, as shown in the example above. If the browser is currently displaying **index.html**, it also knows that **about.html** and **contact.html** are in the same folder. Because the files are stored in the same folder, we can link web pages together using a _relative path_ .

```html
<a href="./contact.html">Contact</a>
```

In this example, the `<a>` tag is used with a relative path to link from the current HTML file to the `contact.html` file in the same folder. On the web page, **Contact** will appear as a link.

- #### Linking At Will :

You’ve probably visited websites where not all links were made up of text. Maybe the links you clicked on were images or some other form of content.

So far, we’ve added links that were made up of only text, like the following:

```html
<a href="https://en.wikipedia.org/wiki/Opuntia" target="_blank">Prickly Pear</a>
```

Text-only links, however, would significantly decrease your flexibility as a web developer!

Thankfully, HTML allows you to turn nearly any element into a link by wrapping that element with an anchor element. With this technique, it’s possible to turn images into links by simply wrapping the `<img>` element with an `<a>` element.

```html
<a href="https://en.wikipedia.org/wiki/Opuntia" target="_blank"
  ><img
    src="https://www.Prickly_Pear_Closeup.jpg"
    alt="A red prickly pear fruit"
/></a>
```

In the example above, an image of a prickly pear has been turned into a link by wrapping the outside of the `<img>` element with an `<a>` element.

- #### Linking to Same Page :

At this point, we have all the content we want on our page. Since we have so much content, it doesn’t all fit on the screen. How do we make it easier for a user to jump to different portions of our page?

When users visit our site, we want them to be able to click a link and have the page automatically scroll to a specific section.

In order to link to a target on the same page, we must give the target an `id`, like this:

```html
<p id="top">This is the top of the page!</p>
<h1 id="bottom">This is the bottom!</h1>
```

In this example, the `<p>` element is assigned an `id` of “top” and the `<h1>` element is assigned “bottom.” An `id` can be added to most elements on a webpage.

An `id` should be descriptive to make it easier to remember the purpose of a link. The target link is a string containing the `#` character and the target element’s `id`.

```html
<ol>
  <li><a href="#top">Top</a></li>
  <li><a href="#bottom">Bottom</a></li>
</ol>
```

In the example above, the links to `<p id="top">` and `<h1 id="bottom">` are embedded in an ordered list. These links appear in the browser as a numbered list of links. An `id` is especially helpful for organizing content belonging to a `div!`

### <a id="tag-htmlcomments" href="#tag-htmlcomments"><strong><em>Comments :</strong></em></a>

---

HTML files also allow you to add comments to your code.

Comments begin with `<!-- and end with -->`. Any characters in between will be ignored by your browser.

```html
<!-- This is a comment that the browser will not display. -->
```

Including comments in your code is helpful for many reasons:

1. They help you (and others) understand your code if you decide to come back and review it at a much later date.
2. They allow you to experiment with new code, without having to delete old code.

---

To view the full _HTML_ code and run this on server [Click Here](index.html)
