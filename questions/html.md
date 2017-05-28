# HTML Q & A

## Table of Contents
1. [What does a doctype do?](#1)
1. [What's the difference between standards mode and quirks mode?](#2)
1. [What's the difference between HTML and XHTML?](#3)
1. [Are there any problems with serving pages as application/xhtml+xml?](#4)
1. [How do you serve a page with content in multiple languages?](#5)
1. [What kind of things must you be wary of when design or developing for multilingual sites?](#6)
1. [What are data- attributes good for?](#7)
1. [Consider HTML5 as an open web platform. What are the building blocks of HTML5?](#8)
1. [Describe the difference between a cookie, sessionStorage and localStorage.](#9)
1. [Describe the difference between `<script>`, `<script async>` and `<script defer>`.](#10)
1. [Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`?](#11)
1. [Do you know any exceptions?](#12)
1. [What is progressive rendering?](#13)
1. [Have you used different HTML templating languages before?](#14)

## Q & A
<a name='1'></a>
### + What does a doctype do?
```
Document Type Declaration (DTD)

TLDR: Declares which version of HTML the page is written in and which features should be supported.

Validation Testing
- It tells the HTML validator which version of (X)HTML standard the web page coding is supposed to comply with. It'll check your code against the specified standard.

Browser
- It tells the browser how to render the page in standards-compliant mode.
- The only purpose of DOCTYPE is to active full standards mode.
- If you serve the page as XHTML using application/xhtml+xml MIME type in the Content-Type HTTP header, you do not need DOCTYPE to enable standards mode, as they such documents always use full standards mode. 

If no DOCTYPE declaration or incorrect:
- Cannot use HTML validator as it requires a DOCTYPE declaration.
- Browser renders the webpage in `Quirks Mode`.
- Stylesheet may not be implemented as planned.
```
<a name='2'></a>
### + What's the difference between standards mode and quirks mode?
```
Quirks mode (AKA Compatibility mode), layout emulates nonstandard behavior in Navigator 4 and IE5. This is to support websites built before adoption of web standards. Standard refers to web standards for both HTML and CSS.

It's a technique used by web browsers to maintain backward compatibility with older webpages. The browser will behave as if it's an older browser.

In Quirks mode, document.body is the root element 
In standard mode, it's the html element (document.documentElement)

Many HTML/CSS features don't work in Quirks mode.
```
<a name='3'></a>
### + What's the difference between HTML and XHTML?
```
HTML:
- Start/end tags not required for every element.
- Only void elements `<br>` `<img>`, and `<link>` may be "self-closed".
- Tags and attributes are case-insensitive.
- Attributes don't need to be quoted.
- Special characters do not have to be escaped.
- Must include HTML5 DOCTYPE.

XHTML: HTML5 that's written and parsed using syntax rules of XML
- Uses a stricter syntax.
- All elements must be closed with an end tag or by self-closing with a />.
- In order for the browser to parse this document according to XML/XHTML rules, it must be send with `Content-type: application/xml+xhtml` reponse header.
```
<a name='4'></a>
### + Are there any problems with serving pages as application/xhtml+xml?
```
Causes IE8 to show DL dialog box for unknown format instead of displayed page.
First version of IE that supports XHTML is IE9.
```
<a name='5'></a>
### + How do you serve a page with content in multiple languages?
```
- Partition your site based on language. 
- Translate each page.
- Change the language meta-tag in the head of each page
- Ex: `<html lang="es">` for a spanish site

```
<a name='6'></a>
### + What kind of things must you be wary of when design or developing for multilingual sites?
```
[Reference](https://www.quora.com/What-kind-of-things-one-should-be-wary-of-when-designing-or-developing-for-multilingual-sites/answer/Ted-Goas?srid=kpHK)
Things to consider:
- How will users select their language? Is there something that happens automatically (possibly using IP address)?
- Text in Images Won't Scale (Will need to have a separate image created for each language)
- Restrictive Word / Sentence Length
- Be mindful of how colors are perceived across different cultures
- remove text content from templates (ALT, TITLE attributes from tags)
- Formatting dates is different depending on location
```
<a name='7'></a>
### + What are data- attributes good for?
```
- They give us the ability to embed custom data attributes on all HTML elements.
- You can access these attributes with CSS(for styling an element with a specific data attribute) or JS.
- Ex: `<li data-type="veg" data-distance="2miles" data-identifier="10318">Salad King</li>`
- Now you can search and sort based on `type`, `distance`, or `identifier`.
```
<a name='8'></a>
### + Consider HTML5 as an open web platform. What are the building blocks of HTML5?
```
HTML (backbone)
  titles, headers, body, footer, tables, input, etc.
CSS (style)
  color, font, position
JS (programming language to provide dynamism to sites)

```
<a name='9'></a>
### + Describe the difference between a cookie, sessionStorage and localStorage.
```

```
<a name='10'></a>
### + Describe the difference between <script>, <script async> and <script defer>.
```

```
<a name='11'></a>
### + Why is it generally a good idea to position CSS <link>s between <head></head> and JS <script>s just before </body>?<a name='1'></a>
### + Do you know any exceptions?
```

```
<a name='12'></a>
### + What is progressive rendering?
```

```
<a name='13'></a>
### + Have you used different HTML templating languages before?
```

```



