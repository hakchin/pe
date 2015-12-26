---
title: Markdown
tags: [tool]
keywords: "syntax, markdown"
last_updated: "December 25, 2015"
summary: "blur blur blur"
published: true
---

## Useful Sites
* [Daringfireball Markdown Syntax](https://daringfireball.net/projects/markdown/syntax)

## Overview

### Philosophy

Markdown is intended to be as easy-to-read and easy-to-write as is feasible.

Readability, however, is emphasized above all else. A Markdown-formatted document should be publishable as-is, as plain text, without looking like it’s been marked up with tags or formatting instructions. While Markdown’s syntax has been influenced by several existing text-to-HTML filters — including [Setext](http://docutils.sourceforge.net/mirror/setext.html), [atx](http://www.aaronsw.com/2002/atx/), [Textile](http://textism.com/tools/textile/), [reStructuredText](http://docutils.sourceforge.net/rst.html), [Grutatext](http://www.triptico.com/software/grutatxt.html), and [EtText](http://ettext.taint.org/doc/) — the single biggest source of inspiration for Markdown’s syntax is the format of plain text email.

To this end, Markdown’s syntax is comprised entirely of punctuation characters, which punctuation characters have been carefully chosen so as to look like what they mean. E.g., asterisks around a word actually look like `*emphasis*`. Markdown lists look like, well, lists. Even blockquotes look like quoted passages of text, assuming you’ve ever used email.

### Inline HTML

Markdown’s syntax is intended for one purpose: to be used as a format for *writing* for the web.

Markdown is not a replacement for HTML, or even close to it. Its syntax is very small, corresponding only to a very small subset of HTML tags. The idea is *not* to create a syntax that makes it easier to insert HTML tags. In my opinion, HTML tags are already easy to insert. The idea for Markdown is to make it easy to read, write, and edit prose. HTML is a *publishing* format; Markdown is a *writing* format. Thus, Markdown’s formatting syntax only addresses issues that can be conveyed in plain text.

For any markup that is not covered by Markdown’s syntax, you simply use HTML itself. There’s no need to preface it or delimit it to indicate that you’re switching from Markdown to HTML; you just use the tags.

The only restrictions are that block-level HTML elements — e.g.  `<div>`, `<table>`, `<pre>`, `<p>`, etc. — must be separated from surrounding content by blank lines, and the start and end tags of the block should not be indented with tabs or spaces. Markdown is smart enough not to add extra (unwanted) `<p>` tags around HTML block-level tags.

For example, to add an HTML table to a Markdown article:

```html
This is a regular paragraph.

<table>
    <tr>
        <td>Foo</td>
    </tr>
</table>

This is another regular paragraph.
```

Note that Markdown formatting syntax is not processed within block-level HTML tags. E.g., you can’t use Markdown-style `*emphasis*` inside an HTML block.

Span-level HTML tags — e.g. `<span>`, `<cite>`, or `<del>` — can be used anywhere in a Markdown paragraph, list item, or header. If you want, you can even use HTML tags instead of Markdown formatting; e.g. if you’d prefer to use HTML `<a>` or `<img>` tags instead of Markdown’s link or image syntax, go right ahead.

Unlike block-level HTML tags, Markdown syntax *is* processed within span-level tags.

### Automatic Escaping for Special Characters

In HTML, there are two characters that demand special treatment: &lt; and &amp;. Left angle brackets are used to start tags; ampersands are used to denote HTML entities. If you want to use them as literal characters, you must escape them as entities, e.g. `&lt;`, and `&amp;`.

Ampersands in particular are bedeviling for web writers. If you want to write about ‘AT&amp;T’, you need to write `‘AT&amp;T’`. You even need to escape ampersands within URLs. Thus, if you want to link to:

```
http://images.google.com/images?num=30&amp;q=larry+bird
```

you need to encode the URL as:

```
http://images.google.com/images?num=30&amp;q=larry+bird
```

in your anchor tag href attribute. Needless to say, this is easy to forget, and is probably the single most common source of HTML validation errors in otherwise well-marked-up web sites.

Markdown allows you to use these characters naturally, taking care of all the necessary escaping for you. If you use an ampersand as part of an HTML entity, it remains unchanged; otherwise it will be translated into `&amp;`.

So, if you want to include a copyright symbol &copy; in your article, you can write:

```
&copy;
```

and Markdown will leave it alone. But if you write:

```
AT&T
```

Markdown will translate it to:

```
AT&amp;T
```

Similarly, because Markdown supports [inline HTML](https://daringfireball.net/projects/markdown/syntax#html), if you use angle brackets as delimiters for HTML tags, Markdown will treat them as such. But if you write:

```
4 < 5
```

Markdown will translate it to:

```
4 &lt; 5
```

However, inside Markdown code spans and blocks, angle brackets and ampersands are *always* encoded automatically. This makes it easy to use Markdown to write about HTML code. (As opposed to raw HTML, which is a terrible format for writing about HTML syntax, because every single &lt; and &amp; in your example code needs to be escaped.)

* * *

## Block Elements

### Paragraphs and Line Breaks

A paragraph is simply one or more consecutive lines of text, separated by one or more blank lines. (A blank line is any line that looks like a blank line — a line containing nothing but spaces or tabs is considered blank.) Normal paragraphs should not be indented with spaces or tabs.

The implication of the &quot;one or more consecutive lines of text&quot; rule is that Markdown supports “hard-wrapped” text paragraphs. This differs significantly from most other text-to-HTML formatters (including Movable Type’s “Convert Line Breaks” option) which translate every line break character in a paragraph into a `<br />` tag.

When you *do* want to insert a `<br />` break tag using Markdown, you end a line with two or more spaces, then type return.

Yes, this takes a tad more effort to create a `<br />`, but a simplistic "every line break is a `<br />`" rule wouldn’t work for Markdown. Markdown’s email-style [blockquoting](https://daringfireball.net/projects/markdown/syntax#blockquote) and multi-paragraph [list items](https://daringfireball.net/projects/markdown/syntax#list) work best — and look better — when you format them with hard breaks.

### Headers

Markdown supports two styles of headers, [Setext](http://docutils.sourceforge.net/mirror/setext.html) and [atx](http://www.aaronsw.com/2002/atx/).

Setext-style headers are "underlined" using equal signs (for first-level headers) and dashes (for second-level headers). For example:

```
This is an H1
=============

This is an H2
-------------
```

Any number of underlining =’s or -’s will work.

Atx-style headers use 1-6 hash characters at the start of the line, corresponding to header levels 1-6. For example:

```
# This is an H1

## This is an H2

###### This is an H6
```

Optionally, you may "close" atx-style headers. This is purely cosmetic — you can use this if you think it looks better. The closing hashes don’t even need to match the number of hashes used to open the header. (The number of opening hashes determines the header level.) :

```
# This is an H1 #

## This is an H2 ##

### This is an H3 ######
```

### Blockquotes

Markdown uses email-style &gt; characters for blockquoting. If you’re familiar with quoting passages of text in an email message, then you know how to create a blockquote in Markdown. It looks best if you hard wrap the text and put a &gt; before every line:

```
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
> 
> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
> id sem consectetuer libero luctus adipiscing.
```

Markdown allows you to be lazy and only put the &gt; before the first line of a hard-wrapped paragraph:

```
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
id sem consectetuer libero luctus adipiscing.
```

Blockquotes can be nested (i.e. a blockquote-in-a-blockquote) by adding additional levels of &gt;:

```
> This is the first level of quoting.
>
> > This is nested blockquote.
>
> Back to the first level.
```

Blockquotes can contain other Markdown elements, including headers, lists, and code blocks:

```
> ## This is a header.
>
> 1.   This is the first list item.
> 2.   This is the second list item.
>
> Here's some example code:
>
>     return shell_exec("echo $input | $markdown_script");
```

Any decent text editor should make email-style quoting easy. For example, with BBEdit, you can make a selection and choose Increase Quote Level from the Text menu.

### Lists

Markdown supports ordered (numbered) and unordered (bulleted) lists.

Unordered lists use asterisks, pluses, and hyphens — interchangably — as list markers:

```
* Red
* Green
* Blue
```

is equivalent to:

```
+ Red
+ Green
+ Blue
```

and:

```
- Red
- Green
- Blue
```

Ordered lists use numbers followed by periods:

```
1. Bird
2. McHale
3. Parish
```

It’s important to note that the actual numbers you use to mark the list have no effect on the HTML output Markdown produces. The HTML Markdown produces from the above list is:

```
<ol>
<li>Bird</li>
<li>McHale</li>
<li>Parish</li>
</ol>
```

If you instead wrote the list in Markdown like this:

```
1.  Bird
1.  McHale
1.  Parish
```

or even:

```
3. Bird
1. McHale
8. Parish
```

you’d get the exact same HTML output. The point is, if you want to, you can use ordinal numbers in your ordered Markdown lists, so that the numbers in your source match the numbers in your published HTML. But if you want to be lazy, you don’t have to.

If you do use lazy list numbering, however, you should still start the list with the number 1. At some point in the future, Markdown may support starting ordered lists at an arbitrary number.

List markers typically start at the left margin, but may be indented by up to three spaces. List markers must be followed by one or more spaces or a tab.

To make lists look nice, you can wrap items with hanging indents:

```
*   Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
    Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
    viverra nec, fringilla in, laoreet vitae, risus.
*   Donec sit amet nisl. Aliquam semper ipsum sit amet velit.
    Suspendisse id sem consectetuer libero luctus adipiscing.
```

But if you want to be lazy, you don’t have to:

```
*   Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
viverra nec, fringilla in, laoreet vitae, risus.
*   Donec sit amet nisl. Aliquam semper ipsum sit amet velit.
Suspendisse id sem consectetuer libero luctus adipiscing.
```

If list items are separated by blank lines, Markdown will wrap the items in `<p>` tags in the HTML output. For example, this input:

```
*   Bird
*   Magic
```

will turn into:

```
<ul>
<li>Bird</li>
<li>Magic</li>
</ul>
```

But this:

```
*   Bird

*   Magic
```

will turn into:

```
<ul>
<li><p>Bird</p></li>
<li><p>Magic</p></li>
</ul>
```

List items may consist of multiple paragraphs. Each subsequent paragraph in a list item must be indented by either 4 spaces or one tab:

```
1.  This is a list item with two paragraphs. Lorem ipsum dolor
    sit amet, consectetuer adipiscing elit. Aliquam hendrerit
    mi posuere lectus.

    Vestibulum enim wisi, viverra nec, fringilla in, laoreet
    vitae, risus. Donec sit amet nisl. Aliquam semper ipsum
    sit amet velit.

2.  Suspendisse id sem consectetuer libero luctus adipiscing.
```

It looks nice if you indent every line of the subsequent paragraphs, but here again, Markdown will allow you to be lazy:

```
*   This is a list item with two paragraphs.

    This is the second paragraph in the list item. You're
only required to indent the first line. Lorem ipsum dolor
sit amet, consectetuer adipiscing elit.

*   Another item in the same list.
```

To put a blockquote within a list item, the blockquote’s &gt; delimiters need to be indented:

```
*   A list item with a blockquote:

    > This is a blockquote
    > inside a list item.
```

To put a code block within a list item, the code block needs to be indented *twice* — 8 spaces or two tabs:

```
*   A list item with a code block:

        <code goes here>
```

It’s worth noting that it’s possible to trigger an ordered list by accident, by writing something like this:

```
1986. What a great season.
```

In other words, a *number-period-space* sequence at the beginning of a line. To avoid this, you can backslash-escape the period:

```
1986\. What a great season.

```

### Code Blocks

Pre-formatted code blocks are used for writing about programming or markup source code. Rather than forming normal paragraphs, the lines of a code block are interpreted literally. Markdown wraps a code block in both `<pre>` and `<code>` tags.

To produce a code block in Markdown, simply indent every line of the block by at least 4 spaces or 1 tab. For example, given this input:

```
This is a normal paragraph:

    This is a code block.
```

Markdown will generate:

```
<p>This is a normal paragraph:</p>

<pre><code>This is a code block.
</code></pre>
```

One level of indentation — 4 spaces or 1 tab — is removed from each line of the code block. For example, this:

```
Here is an example of AppleScript:

    tell application "Foo"
        beep
    end tell
```

will turn into:

```
<p>Here is an example of AppleScript:</p>

<pre><code>tell application "Foo"
    beep
end tell
</code></pre>
```

A code block continues until it reaches a line that is not indented (or the end of the article).

Within a code block, ampersands (&amp;) and angle brackets (< and >) are automatically converted into HTML entities. This makes it very easy to include example HTML source code using Markdown — just paste it and indent it, and Markdown will handle the hassle of encoding the ampersands and angle brackets. For example, this:

```
   <div class="footer">
        &copy; 2004 Foo Corporation
    </div>
```

will turn into:

```
<pre><code><div class="footer">
    &copy; 2004 Foo Corporation
</div>
</code></pre>
```

Regular Markdown syntax is not processed within code blocks. E.g., asterisks are just literal asterisks within a code block. This means it’s also easy to use Markdown to write about Markdown’s own syntax.

### Horizontal Rules

You can produce a horizontal rule tag `(<hr />)` by placing three or more hyphens, asterisks, or underscores on a line by themselves. If you wish, you may use spaces between the hyphens or asterisks. Each of the following lines will produce a horizontal rule:

```
* * *

***

*****

- - -

---------------------------------------

* * *
```

***

## Span Elements

### Links

Markdown supports two style of links: *inline* and *reference*.

In both styles, the link text is delimited by [square brackets].

To create an inline link, use a set of regular parentheses immediately after the link text’s closing square bracket. Inside the parentheses, put the URL where you want the link to point, along with an *optional* title for the link, surrounded in quotes. For example:

```
This is [an example](http://example.com/ "Title") inline link.

[This link](http://example.net/) has no title attribute.
```

Will produce:

```
<p>This is <a href="http://example.com/" title="Title">
an example</a> inline link.</p>

<p><a href="http://example.net/">This link</a> has no
title attribute.</p>
```

If you’re referring to a local resource on the same server, you can use relative paths:

```
See my [About](/about/) page for details.   
```

Reference-style links use a second set of square brackets, inside which you place a label of your choosing to identify the link:

```
This is [an example][id] reference-style link.
```

You can optionally use a space to separate the sets of brackets:

```
This is [an example] [id] reference-style link.
```

Then, anywhere in the document, you define your link label like this, on a line by itself:

```
[id]: http://example.com/  "Optional Title Here"
```

That is:

* Square brackets containing the link identifier (optionally indented from the left margin using up to three spaces);

* followed by a colon;

* followed by one or more spaces (or tabs);

* followed by the URL for the link;

* optionally followed by a title attribute for the link, enclosed in double or single quotes, or enclosed in parentheses.

The following three link definitions are equivalent:

```
[foo]: http://example.com/  "Optional Title Here"
[foo]: http://example.com/  'Optional Title Here'
[foo]: http://example.com/  (Optional Title Here)
```

Note: There is a known bug in Markdown.pl 1.0.1 which prevents single quotes from being used to delimit link titles.

The link URL may, optionally, be surrounded by angle brackets:

```
[id]:   "Optional Title Here"
```

You can put the title attribute on the next line and use extra spaces or tabs for padding, which tends to look better with longer URLs:

```
[id]: http://example.com/longish/path/to/resource/here
    "Optional Title Here"
```

Link definitions are only used for creating links during Markdown processing, and are stripped from your document in the HTML output.

Link definition names may consist of letters, numbers, spaces, and punctuation — but they are *not* case sensitive. E.g. these two links:

```
[link text][a]
[link text][A]
```

are equivalent.

The *implicit link name* shortcut allows you to omit the name of the link, in which case the link text itself is used as the name. Just use an empty set of square brackets — e.g., to link the word "Google" to the google.com web site, you could simply write:

```
[Google][]
```

And then define the link:

```
[Google]: http://google.com/
```

Because link names may contain spaces, this shortcut even works for multiple words in the link text:

```
Visit [Daring Fireball][] for more information.
```

And then define the link:

```
[Daring Fireball]: http://daringfireball.net/
```

Link definitions can be placed anywhere in your Markdown document. I tend to put them immediately after each paragraph in which they’re used, but if you want, you can put them all at the end of your document, sort of like footnotes.

Here’s an example of reference links in action:

```
I get 10 times more traffic from [Google] [1] than from
[Yahoo] [2] or [MSN] [3].

  [1]: http://google.com/        "Google"
  [2]: http://search.yahoo.com/  "Yahoo Search"
  [3]: http://search.msn.com/    "MSN Search"
```

Using the implicit link name shortcut, you could instead write:

```
I get 10 times more traffic from [Google][] than from
[Yahoo][] or [MSN][].

  [google]: http://google.com/        "Google"
  [yahoo]:  http://search.yahoo.com/  "Yahoo Search"
  [msn]:    http://search.msn.com/    "MSN Search"
```

Both of the above examples will produce the following HTML output:

```
<p>I get 10 times more traffic from <a href="http://google.com/" title="Google">Google</a> than from
<a href="http://search.yahoo.com/" title="Yahoo Search">Yahoo</a>
or <a href="http://search.msn.com/" title="MSN Search">MSN</a>.</p>
```

For comparison, here is the same paragraph written using Markdown’s inline link style:

```
I get 10 times more traffic from [Google](http://google.com/ "Google")
than from [Yahoo](http://search.yahoo.com/ "Yahoo Search") or
[MSN](http://search.msn.com/ "MSN Search").
```

The point of reference-style links is not that they’re easier to write. The point is that with reference-style links, your document source is vastly more readable. Compare the above examples: using reference-style links, the paragraph itself is only 81 characters long; with inline-style links, it’s 176 characters; and as raw HTML, it’s 234 characters. In the raw HTML, there’s more markup than there is text.

With Markdown’s reference-style links, a source document much more closely resembles the final output, as rendered in a browser. By allowing you to move the markup-related metadata out of the paragraph, you can add links without interrupting the narrative flow of your prose.

### Emphasis

Markdown treats asterisks (*) and underscores (_) as indicators of emphasis. Text wrapped with one * or _ will be wrapped with an HTML `<em>` tag; double *’s or _’s will be wrapped with an HTML `<strong>` tag. E.g., this input:

```
*single asterisks*

_single underscores_

**double asterisks**

__double underscores__
```

will produce:


```
<em>single asterisks</em>

<em>single underscores</em>

<strong>double asterisks</strong>

<strong>double underscores</strong>
```

You can use whichever style you prefer; the lone restriction is that the same character must be used to open and close an emphasis span.

Emphasis can be used in the middle of a word:

```
un*frigging*believable
```

But if you surround an * or _ with spaces, it’ll be treated as a literal asterisk or underscore.

To produce a literal asterisk or underscore at a position where it would otherwise be used as an emphasis delimiter, you can backslash escape it:

```
\*this text is surrounded by literal asterisks\*
```

### Code

To indicate a span of code, wrap it with backtick quotes (`). Unlike a pre-formatted code block, a code span indicates code within a normal paragraph. For example:

```
Use the `printf()` function.
```

will produce:

```
<p>Use the <code>printf()</code> function.</p>
```

To include a literal backtick character within a code span, you can use multiple backticks as the opening and closing delimiters:

```
``There is a literal backtick (`) here.``
```

which will produce this:

```
<p><code>There is a literal backtick (`) here.</code></p>
```

The backtick delimiters surrounding a code span may include spaces — one after the opening, one before the closing. This allows you to place literal backtick characters at the beginning or end of a code span:

```
A single backtick in a code span: `` ` ``

A backtick-delimited string in a code span: `` `foo` ``
```

will produce:

```
<p>A single backtick in a code span: <code>`</code></p>

<p>A backtick-delimited string in a code span: <code>`foo`</code></p>
```

With a code span, ampersands and angle brackets are encoded as HTML entities automatically, which makes it easy to include example HTML tags. Markdown will turn this:

```
Please don't use any `<blink>` tags.
```

into:

```
<p>Please don't use any <code>&lt;blink&gt;</code> tags.</p>
```

You can write this:

```
`&#8212;` is the decimal-encoded equivalent of `&mdash;`.
```

to produce:

```
<p><code>&#8212;</code> is the decimal-encoded
equivalent of <code>&amp;mdash;</code>.</p>
```

### Images

Admittedly, it’s fairly difficult to devise a "natural" syntax for placing images into a plain text document format.

Markdown uses an image syntax that is intended to resemble the syntax for links, allowing for two styles: *inline* and *reference*.

Inline image syntax looks like this:

```
![Alt text](/path/to/img.jpg)

![Alt text](/path/to/img.jpg "Optional title")
```

That is:

* An exclamation mark: !;

* followed by a set of square brackets, containing the alt attribute text for the image;

* followed by a set of parentheses, containing the URL or path to the image, and an optional title attribute enclosed in double or single quotes.

Reference-style image syntax looks like this:

```
![Alt text][id]
```

Where "id" is the name of a defined image reference. Image references are defined using syntax identical to link references:

```
[id]: url/to/image  "Optional title attribute"
```

As of this writing, Markdown has no syntax for specifying the dimensions of an image; if this is important to you, you can simply use regular HTML `<img>` tags.

* * *

## Miscellaneous

### Automatic Links

Markdown supports a shortcut style for creating "automatic" links for URLs and email addresses: simply surround the URL or email address with angle brackets. What this means is that if you want to show the actual text of a URL or email address, and also have it be a clickable link, you can do this:

```
<http://example.com/>
```

Markdown will turn this into:

```
<a href="http://example.com/">http://example.com/</a>
```

Automatic links for email addresses work similarly, except that Markdown will also perform a bit of randomized decimal and hex entity-encoding to help obscure your address from address-harvesting spambots. For example, Markdown will turn this:

```
<address@example.com>
```

into something like this:

```
<a href="&#x6D;&#x61;i&#x6C;&#x74;&#x6F;:&#x61;&#x64;&#x64;&#x72;&#x65;
&#115;&#115;&#64;&#101;&#120;&#x61;&#109;&#x70;&#x6C;e&#x2E;&#99;&#111;
&#109;">&#x61;&#x64;&#x64;&#x72;&#x65;&#115;&#115;&#64;&#101;&#120;&#x61;
&#109;&#x70;&#x6C;e&#x2E;&#99;&#111;&#109;</a>
```


which will render in a browser as a clickable link to "address@example.com".

(This sort of entity-encoding trick will indeed fool many, if not most, address-harvesting bots, but it definitely won’t fool all of them. It’s better than nothing, but an address published in this way will probably eventually start receiving spam.)

### Backslash Escapes

Markdown allows you to use backslash escapes to generate literal characters which would otherwise have special meaning in Markdown’s formatting syntax. For example, if you wanted to surround a word with literal asterisks (instead of an HTML `<em>` tag), you can use backslashes before the asterisks, like this:

```
\*literal asterisks\*
```

Markdown provides backslash escapes for the following characters:

```
\   backslash
`   backtick
*   asterisk
_   underscore
{}  curly braces
[]  square brackets
()  parentheses
#   hash mark
+   plus sign
-   minus sign (hyphen)
.   dot
!   exclamation mark
```
## Markdown Syntax

### External Image
![](http://logdown.com/images/logo.png)

![oneM2M](http://img.etnews.com/ict/2013/term/image_020130329141422.jpg)

<a title="Chinese and Korean History Timeline.xlsx" href="https://www.flickr.com/photos/44489836@N06/22647903164/in/dateposted-public/"><img src="https://farm6.staticflickr.com/5767/22647903164_27c901b173_z.jpg" alt="Chinese and Korean History Timeline" width="640" height="620" /></a>


### External Video

* 아래 그림을 보면 오른쪽 마우스 클릭하여 Copy Embed Code 선택하여 markdown 에 붙여 넣기 하면 youtube 동영상이 삽입된다.

<a data-flickr-embed="true"  href="https://www.flickr.com/photos/44489836@N06/23592539839/in/album-72157661553967886/" title="youtube_right_click"><img src="https://farm6.staticflickr.com/5744/23592539839_3ec335fd27_z.jpg" width="541" height="287" alt="youtube_right_click"></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

* 삽입된 youtube 동영상

<iframe width="854" height="480" src="https://www.youtube.com/embed/dj-x8_7VULc" frameborder="0" allowfullscreen></iframe>

### Bloging with code snippet:

`inline code`

#### Plain Code

```
puts "Hello World!"
```

#### Code with Language

```ruby
puts "Hello World!"
```

### MathJax in Markdown

* [mathjax with jekyll-nice!!](http://gastonsanchez.com/blog/opinion/2014/02/16/Mathjax-with-jekyll.html)


#### Mathjax

```
$$ x = \dfrac{-b \pm \sqrt{b^{2} - 4ac}}{2a} $$
```

$$ x = \dfrac{-b \pm \sqrt{b^{2} - 4ac}}{2a} $$

#### Inline Mathjax

The answser is \\(a^{2} + b^{2} = c^{2}\\).

* inline \\(\dfrac{a}{b}\\) and not inline

$$ \dfrac{a}{b} $$

#### mathjax example

[MathJax](http://www.mathjax.org/) is a simple way of including Tex/LaTex/MathML based mathematics in HTML webpages. To get up and running you need to include the MathJax script in the header of your github pages page, and then write some maths. For LaTex, there are two delimiters you need to know about, one for block or displayed mathematics `\[ ... \]`, and the other for inline mathematics `\( ... \)`.

### Configuration

To enable MathJax support be sure Kramdown is your Markdown flavor of choice and MathJax is set to true in your `_config.yml` file.

```
markdown: kramdown
mathjax: true
```

```
Here is an example MathJax inline rendering \\( 1/x^{2} \\), and here is a block rendering:
$$ \frac{1}{n^{2}} $$
```

Here is an example MathJax inline rendering \\( 1/x^{2} \\), and here is a block rendering:

$$ \frac{1}{n^{2}} $$

The only thing to look out for is the escaping of the backslash when using markdown, so the delimiters become \\[ ... \\] and \\( ... \\) for inline and block maths respectively.



### Table Example

| Tables | Are | Cool |
| ------------- |:-------------:| -----:|
| col 1 | Hello | $1600 |
| col 2 | Hello | $12 |
| col 3 | Hello | $1 |

### Table Example by Hakchin

#### 1년 이내에 이루고 싶은 10가지 목표 (2017년)

| No. | S | T | Timely | Target | Remarks |
| ---------- |:-----:|:---:|:------:|:-----------------------------|---------:|
| 01 | O | O |99991231|123456789012345 |12345 |
| 02 | O | O | | | |
| 03 | O | O | | | |
| 04 | O | O | | | |
| 05 | O | O | | | |
| 06 | O | O | | | |
| 07 | O | O | | | |
| 08 | O | O | | | |
| 09 | O | O | | | |
| 10 | O | O | | | |

Specific: 구체적으로 작성한다.
Target: 목표물이 명확해야 한다.
Achievable: 성취 가능해야 한다.
Realistic: 실현 가능해야 한다.
Timely: 시기 적절하게 기한을 정한다.


## markdown-uml
### Reference Sites
* Online Editor
  * [PlantText](http://www.planttext.com/planttext)
  * [PlantUML homepage](http://plantuml.sourceforge.net/)
* 참고 사이트
  * [UML (Unified Modeling Language)](http://blog.naver.com/hermet/220120846602)
  * [UML이란?](http://onecellboy.tistory.com/334)


### UML Diagram의 종류
* 구조적(Structural)
  * Class Diagram
  * Component Diagram
  * Deployment Diagram

* 행위적(Behavioral)
  * Use Case Diagram
  * Sequence Diagram
  * Collaboration Diagram
  * Statechart Diagram
  * Activity Diagram

<img src="https://docs.google.com/drawings/d/1sHxXx348RH4OHnhrOPMJJPgERLhGG39cBz9hKTQ85p8/pub?w=960&amp;h=514">

### plantuml

#### plantuml-class

{% gist hakchin/4ac3a92da75543b5daac %}

![](http://uml.mvnsearch.org/gist/4ac3a92da75543b5daac)

{% gist hakchin/6e753085ca869f8806c0 %}

![](http://uml.mvnsearch.org/gist/6e753085ca869f8806c0)

{% gist hakchin/21575ff0f534fc065b66 %}

![](http://uml.mvnsearch.org/gist/21575ff0f534fc065b66)

#### 관계 (Relationship)

* Association
* Generalization
* Dependency
* Realization


#### plantuml-sequence

{% gist hakchin/a29ed23af7aa58a6764c %}

![](http://uml.mvnsearch.org/gist/a29ed23af7aa58a6764c)


#### plantuml-component

{% gist hakchin/1354c4215962341b7afa %}

![](http://uml.mvnsearch.org/gist/1354c4215962341b7afa)



#### plantuml-sequence

{% gist hakchin/0c6796799c1c9a50ae0e %}
![http://uml.mvnsearch.org/gist/0c6796799c1c9a50ae0e](http://uml.mvnsearch.org/gist/0c6796799c1c9a50ae0e)



#### Trouble Shooting

아래 그림과 같이 Graphviz 관련 에러가 났을 경우에

<img src="https://docs.google.com/drawings/d/1-5NBjkmTGIbAb0zjyOWbauo_quEVLTOa7OxZ2vOdlbA/pub?w=305&amp;h=228">


다음 명령어로 Graphviz을 설치하여 해결하였다.
* sudo apt-get install graphviz

***

## R Markdown

This is an R Markdown document. Markdown is a simple formatting syntax for authoring HTML, PDF, and MS Word documents. For more details on using R Markdown see <http://rmarkdown.rstudio.com>.

### Getting Started
* [Markdown by Hakchin](https://hakchin.wordpress.com/2015/12/04/markdown)
* [An Example R Markdown](http://www.statpower.net/Content/310/R%20Stuff/SampleMarkdown.html)
* [http://blog.naver.com/edgelab/220218470395](http://blog.naver.com/edgelab/220218470395)
* [An Introduction to R Markdown](http://rpubs.com/mansun_kuo/24330)

### markdown cheatsheet

* [Markdown quick reference by wordpress](https://en.support.wordpress.com/markdown-quick-reference/)
* [stackedit](https://stackedit.io/editor)
* [Mastering Markdown](https://guides.github.com/features/mastering-markdown)
* [markdown cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
* [Some examples of using \\(\LaTeX\\) in R Markdown documents](http://www.calvin.edu/~rpruim/courses/m343/F12/RStudio/LatexExamples.html)


### markdown at atom

### preview

ctrl-shift-m.

### R Markdown 따라하기

### 참조 문서
* [Serve Jekyll Websites with servr and knitr](http://yihui.name/knitr-jekyll/2014/09/jekyll-with-knitr.html)
* [Wordpress에서 Jekyll로…](http://wsyang.com//r/2015/07/26/Goodbye-wordpress-hellow-Jekyll/)

### R 화면에서

> setwd("/Users/sn2ro/OneDrive/git-c/hakchin.github.io")
> servr::jekyll(command = '/Users/sn2ro/.rbenv/shims/jekyll build --watch')

When you click the **Knit** button a document will be generated that includes both content as well as the output of any embedded R code chunks within the document. You can embed an R code chunk like this:

```r
summary(cars)
```

```
## speed dist
## Min. : 4.0 Min. : 2.00
## 1st Qu.:12.0 1st Qu.: 26.00
## Median :15.0 Median : 36.00
## Mean :15.4 Mean : 42.98
## 3rd Qu.:19.0 3rd Qu.: 56.00
## Max. :25.0 Max. :120.00
```

You can also embed plots, for example:

<a data-flickr-embed="true"  href="https://www.flickr.com/photos/44489836@N06/23864936192/in/album-72157661553967886/" title="QrcGNegSRX6KfwiGrtFU_unnamed-chunk-2-1"><img src="https://farm2.staticflickr.com/1641/23864936192_7bf5422877_z.jpg" width="504" height="504" alt="QrcGNegSRX6KfwiGrtFU_unnamed-chunk-2-1"></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

Note that the `echo = FALSE` parameter was added to the code chunk to prevent printing of the R code that generated the plot.

### Key Formatting Constructs
The key formatting constructs are discussed at . You can see above how I constructed main section headings. Now I’m going to create a series of sections using secondary headings.

#### Emphasis
This is italic. This is bold.

#### Superscripts

This is $$y^2$$.

#### Lists
##### Unordered
* Item 1
* Item 2
  * Item 2a
  * Item 2b

##### Ordered
1. Item 1
1. Item 2
1. Item 3
  1. Item 3a
  1. Item 3b

#### Block Quotes
A friend once said:

> It’s always better to give than to receive.

#### Displaying Blocks of Code Without Evaluating

In some situations, you want to display R code but not evaluate it. Here is an example of how you format.

```
This text is displayed verbatim / preformatted
```

#### Displaying R Code Inline in a Sentence
Sometimes, you need to include an R name or command inline in a sentence. Here is how your format it.

The `sqrt` function computes the square root of a number.

#### Evaluating and Inserting R Code in a Sentence
Sometimes, you want a result without showing the user that you used R to get it. Here is an example.

The mean of the numbers 2,3,4 is 3.

There are lots of ways you can exploit this capability. You can do more advanced calculations in a hidden code block, assign the results to variables, and then simply use the variable names to insert the results in a sentence.

In the following example, I compute the sum of the integers from 2 to 19 in a hidden code block. Then I display the result inline.

The sum of the integers from 2 to 19 is 189.

### Typesetting Equations
#### Inline vs. Display Material
Equations can be formatted inline or as displayed formulas. In the latter case, they are centered and set off from the main text. In the former case, the mathematical material occurs smoothly in the line of text.

In order to fit neatly in a line, summation expressions (and similar constructs) are formatted slightly differently in their inline and display versions.

Inline mathematical material is set off by the use of single dollar-sign characters. Consequently, if you wish to use a dollar sign (for example, to indicate currency), you need to preface it with a back-slash. The following examples, followed by their typeset versions, should make this clear

```
This summation expression $\\(\sum_{i=1}^n X_i \\) appears inline.
```

This summation expression \\(\sum_{i=1}^n X_i \\) appears inline.

```
This summation expression is in display form.

$$ \sum_{i=1}^n X_i $$
```



This summation expression is in display form.

$$\sum_{i=1}^n X_i $$





### Some LaTeX Basics
In this section, we show you some rudiments of the LaTeX typesetting language.

#### Subscripts and Superscripts
To indicate a subscript, use the underscore `_` character. To indicate a superscript, use a single caret character ^. Note: this can be confusing, because the R Markdown language delimits superscripts with two carets. In LaTeX equations, a single caret indicates the superscript.

If the subscript or superscript has just one character, there is no need to delimit with braces. However, if there is more than one character, braces must be used.

The following examples illustrate:
```
$$X_i$$
$$X_{i}$$
```
$$ X_i $$

$$ X_{i} $$

Notice that in the above case, braces were not actually needed.

In this next example, however, failure to use braces creates an error, as LaTeX sets only the first character as a subscript

```
$$X_{i,j}$$
$$X_i,j$$
```
$$ X_{i,j} $$

$$ X_i,j $$
Here is an expression that uses both subscripts and superscripts
```
$$X^2_{i,j}$$
```
$$ X^2_{i,j} $$

#### Square Roots
We indicate a square root using the `\sqrt` operator.
```
$$\sqrt{b^2 - 4ac}$$
```
$$ \sqrt{b^2 - 4ac} $$

#### Fractions
Displayed fractions are typeset using the `\frac` operator.
```
$$\frac{4z^3}{16}$$
```
$$ \frac{4z^3}{16} $$

#### Summation Expressions
These are indicated with the `’ operator, followed by a subscript for the material appearing below the summation sign, and a superscript for any material appearing above the summation sign.

Here is an example.

```
$$\sum_{i=1}^{n} X^3_i$$
```
$$ \sum_{i=1}^{n} X^3_i $$

#### Self-Sizing Parentheses
In LaTeX, you can create parentheses, brackets, and braces which size themselves automatically to contain large expressions. You do this using the `\left` and `\right` operators. Here is an example
```
$$\sum_{i=1}^{n}\left( \frac{X_i}{Y_i} \right)$$
```
$$ \sum_{i=1}^{n}\left( \frac{X_i}{Y_i} \right) $$

#### Greek Letters
Many statistical expressions use Greek letters. Much of the Greek alphabet is implemented in LaTeX, as indicated in the LaTeX cheat sheet available at the course website. There are both upper and lower case versions available for some letters.
```
$$\alpha, \beta, \gamma, \Gamma$$
```
$$ \alpha, \beta, \gamma, \Gamma $$

#### Special Symbols
All common mathematical symbols are implemented, and you can find a listing on the LaTeX cheat sheet.

Some examples. (Notice that, in the third example, I use the tilde character for a forced space. Generally LaTeX does spacing for you automatically, and unless you use the tilde character, R will ignore your attempts to add spaces.)

```
$$a \pm b$$
$$x \ge 15$$
$$a_i \ge 0~~~\forall i$$
```
$$ a \pm b $$
$$ x \ge 15 $$
$$ a_i \ge 0~~~\forall i $$

#### Special Functions
LaTeX typesets special functions in a different font from mathematical variables. These functions, such as sin, cos, etc. are indicated in LaTeX with a backslash. Here is an example that also illustrates how to typeset an integral.
```
$$\int_0^{2\pi} \sin x~dx$$
```
$$ \int_0^{2\pi} \sin x~dx $$

#### Matrices
Matrics are presented in the `array` environment. One begins with the statement `\begin{array}` and ends with the statement `\end{array}`. Following the opening statement, a format code is used to indicate the formatting of each column. In the example below, we use the code `{rrr}` to indicate that each column is right justified. Each row is then entered, with cells separated by the `&amp;` symbol, and each line (except the last) terminated by `\\`.

```
$$\begin{array}
{rrr}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{array}
$$
```
$$
\begin{array}
{rrr}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{array}
$$

In math textbooks, matrices are often surrounded by brackets, and are assigned to a boldface letter. Here is an example

```
$$\mathbf{X} = \left[\begin{array}
{rrr}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{array}\right]
$$
```
$$
\mathbf{X} = \left[\begin{array}
{rrr}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{array}\right]
$$

### Hakchin's

[comment1]: # title: "R Markdown"

[comment2]: # This actually is the most platform independent comment

Comment 처리는 아래와 같이 한다.
```
(empty line)
[comment1]: # (This actually is the most platform independent comment)
(empty line)
[comment2]: # (This actually is the most platform independent comment)
This is from http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax
```

***


---

## Overview 


## Getting started

To get started, see these three topics:

1. {{site.data.mydoc.mydoc_urls.mydoc_getting_started.link}}
2. {{site.data.mydoc.mydoc_urls.mydoc_configuration_settings.link}}
3. {{site.data.mydoc.mydoc_urls.mydoc_adding_new_projects.link}}

## PDF Download Option for Help Material

If you would like to download this help file as a PDF, you can do so here. The PDF is comprehensive of all the content in the online help.   

<a target="_blank" class="noCrossRef" href="files/{{site.pdf_file_name}}"><button type="button" class="btn btn-default" aria-label="Left Align"><span class="glyphicon glyphicon-download-alt" aria-hidden="true"></span> PDF Download</button></a>

The PDF contains a timestamp in the header indicating when it was last generated. 

