# CSS Q & A

## Table of Contents
1. [What is the difference between classes and ID's in CSS?](#1)
1. [What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?](#2)
1. [Describe Floats and how they work.](#3)
1. [Describe z-index and how stacking context is formed.](#4)
1. [Describe BFC(Block Formatting Context) and how it works.](#5)
1. [What are the various clearing techniques and which is appropriate for what context?](#6)
1. [Explain CSS sprites, and how you would implement them on a page or site.](#7)
1. [What are your favourite image replacement techniques and which do you use when?](#8)
1. [How would you approach fixing browser-specific styling issues?](#9)
1. [How do you serve your pages for feature-constrained browsers?](#10)
1. [What techniques/processes do you use?](#11)
1. [What are the different ways to visually hide content (and make it available only for screen readers)?](#12)
1. [Have you ever used a grid system, and if so, what do you prefer?](#13)
1. [Have you used or implemented media queries or mobile specific layouts/CSS?](#14)
1. [Are you familiar with styling SVG?](#15)
1. [How do you optimize your webpages for print?](#16)
1. [What are some of the "gotchas" for writing efficient CSS?](#17)
1. [What are the advantages/disadvantages of using CSS preprocessors?](#18)
1. [Describe what you like and dislike about the CSS preprocessors you have used.](#19)
1. [How would you implement a web design comp that uses non-standard fonts?](#20)
1. [Explain how a browser determines what elements match a CSS selector.](#21)
1. [Describe pseudo-elements and discuss what they are used for.](#22)
1. [Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in difference box models.](#23)
1. [What does * { box-sizing: border-box; } do? What are its advantages?](#24)
1. [List as many values for the display property that you can remember.](#25)
1. [What's the difference between inline and inline-block?](#26)
1. [What's the difference between a relative, fixed, absolute and statically positioned element?](#27)
1. [The 'C' in CSS stands for Cascading. How is priority determined in assigning styles (a few examples)?](#28)
1. [How can you use this system to your advantage?](#29)
1. [What existing CSS frameworks have you used locally, or in production? How would you change/improve them?](#30)
1. [Have you played around with the new CSS Flexbox or Grid specs?](#31)
1. [How is responsive design different from adaptive design?](#32)
1. [Have you ever worked with retina graphics? If so, when and what techniques did you use?](#33)
1. [Is there any reason you'd want to use translate() instead of absolute positioning, or vice-versa? And why?](#34)


## Q & A
<a name="1"></a>
### + What is the difference between classes and ID's in CSS?
```
An ID selector (preceded by hash, #) selects a single element.
A class selector (preceded by a full stop, .) selects all elements that have the class.
```
<a name="2"></a>
### + What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?
[Reference](https://teamtreehouse.com/community/reset-vs-normalizecss) | [Reference 2](https://stackoverflow.com/questions/6887336/what-is-the-difference-between-normalize-css-and-reset-css)
```
TLDR: 
- Resets remove all built-in browser styling
- Normalize aims to make built-in browser styling consistent across browsers.
- Use reset if you want everything set to 0. Use normalize if you want a visual starting point and fixing browser issues.

Resetting: Reset.css will remove all default styling (margin, padding, font styles, etc) applied by the browser to give you a blank canvas.

Normalizing: Normalize.css is a base stylesheet meaning its the starting point for your website styles and it styles the default elements to be consistent across browsers. It also provide bug fixes for common problems: display settings for HTML5 elements, SVG overflow in IE9, button styling bug in iOS.
- More modular
- Doesn't clutter your dev tools
- Better documentation
```
<a name="3"></a>
### + Describe Floats and how they work.
```
Specifying a floated element means that the element remains a part of the flow of the web page (vs. absolutely positioned elements).
Clear property used to control the behavior of floating elements.
  Specifies on which sides of an element floating elements are not allowed to float.

// If element taller than container (and it's floated), it will overflow. Add to containing element to fix the problem:
.clearfix {
  overflow: auto
}

// Modern clearfix hack:
.clearfix::after {
    content: "";
    clear: both;
    display: table;
}

```
<a name="4"></a>
### + Describe z-index and how stacking context is formed.
[Reference](https://www.w3schools.com/cssref/pr_pos_z-index.asp)
```
z-index property specifies the stack order of an element.
- It only works on positioned elements (position:absolute, position:relative, or position:fixed [ANYTHING OTHER THAN static]
- An element with a larger z-index generally covers an element with a lower one.
```
<a name="5"></a>
### + Describe BFC(Block Formatting Context) and how it works.
```
TODO
```
<a name="6"></a>
### + What are the various clearing techniques and which is appropriate for what context?
```
- empty <div> method (or <br> element)
- overflow method: setting overflow property on parent element
  - parent will expand to contain the floats
  - useful for when you already have a container div
- easy clearing method
  - append clearfix class
  .clearfix: after {
    content: ".";
    visibility: hidden;
    display: block;
    height: 0;
    clear: both;
  }
- the future contain-floats value
```
<a name="7"></a>
### + Explain CSS sprites, and how you would implement them on a page or site.
```
- An image sprite is a collection of images put into a single image.
- A web page with many images can take a long time to load and generates multiple server requests.
- Using image sprites will reduce the number of server requests and save bandwidth.
- Example: 
<!DOCTYPE html>
<html>
<head>
<style>
#home {
    width: 46px;
    height: 44px;
    background: url(img_navsprites.gif) 0 0;
}

#next {
    width: 43px;
    height: 44px;
    background: url(img_navsprites.gif) -91px 0;
}
</style>
</head>
<body>

<img id="home" src="img_trans.gif"><br><br>
<img id="next" src="img_trans.gif">

</body>
</html>
```
<a name="8"></a>
### + What are your favourite image replacement techniques and which do you use when?
```
CSS image replacement is a technique of replacing a text element (usually a header tag) with an image.
```
<a name="9"></a>
### + How would you approach fixing browser-specific styling issues?
```
- Use a normalized CSS library
- Implement vendor-specific CSS fixes
- Test in all targeted browsers
```
<a name="10"></a>
### + How do you serve your pages for feature-constrained browsers?
```
- Reduce content and layout
- Add vendor-specific CSS fixes
- Media query, browser detection
```
<a name="11"></a>
### + What techniques/processes do you use?
```
- Add vendor-specific CSS fixes
```
<a name="12"></a>
### + What are the different ways to visually hide content (and make it available only for screen readers)?
[Reference](https://www.sitepoint.com/when-and-how-to-visually-hide-content/)
```
Position content off-screen:

.hidden {
  position: absolute;
  left: -9999em;
  top: auto;
  width: 1px;
  height: 1px;
  overflow: hidden;
}
<div class="hidden">Hidden content here.</div>

CSS clipping:
Clip lets you specify the dimensions of an absolutely positioned element using top, right, bottom, and left values, creating a boxed container for the content. By setting all values to 0 pixels, the content becomes invisible.
.hidden {
  position: absolute !important;
  clip: rect(1px 1px 1px 1px); /* IE6, IE7 */
  clip: rect(1px, 1px, 1px, 1px);
  padding: 0 !important;
  border: 0 !important;
  height: 1px !important; 
  width: 1px !important; 
  overflow: hidden;
}
```
<a name="13"></a>
### + Have you ever used a grid system, and if so, what do you prefer?
```
I've tried Bootstrap.
There's also: Simple Grid, Pure, Flexbox Grid, and Foundation.
```
<a name="14"></a>
### + Have you used or implemented media queries or mobile specific layouts/CSS?
```
Media queries.
```
<a name="15"></a>
### + Are you familiar with styling SVG?
```

```
<a name="16"></a>
### + How do you optimize your webpages for print?

```
Create a stylesheet specifically for print.
Format heading and paragraph tags, links and tables, and
clear unnecessary contents and images.
```
<a name="17"></a>
### + What are some of the "gotchas" for writing efficient CSS?
[Reference](http://jgthms.com/css-interview-questions-and-answers.html)
```
- Ordering your CSS: reset, fonts, generic tags, shared properties,
  common elements, elements, elements in context, colors, z-index, animations, CSS3 vendor-prefix stuff

```
<a name="18"></a>
### + What are the advantages/disadvantages of using CSS preprocessors?
```
TODO
```
<a name="19"></a>
### + Describe what you like and dislike about the CSS preprocessors you have used.
```
TODO
```
<a name="20"></a>
### + How would you implement a web design comp that uses non-standard fonts?
```
TODO
```
<a name="21"></a>
### + Explain how a browser determines what elements match a CSS selector.
```
TODO
```
<a name="22"></a>
### + Describe pseudo-elements and discuss what they are used for.
```
TODO
```
<a name="23"></a>
### + Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.
```
TODO
```
<a name="24"></a>
### + oxWhat does * { box-sizing: border-box; } do? What are its advantages?
```
TODO
```
<a name="25"></a>
### + List as many values for the display property that you can remember.
```
TODO
```
<a name="26"></a>
### + What's the difference between inline and inline-block?
```
TODO
```
<a name="27"></a>
### + What's the difference between a relative, fixed, absolute and statically positioned element?
```
TODO
```
<a name="28"></a>
### + The 'C' in CSS stands for Cascading. How is priority determined in assigning styles (a few examples)? 
```
TODO
```
<a name="29"></a>
### + How can you use this system to your advantage?
```
TODO
```
<a name="30"></a>
### + What existing CSS frameworks have you used locally, or in production? How would you change/improve them?
```
TODO
```
<a name="31"></a>
### + Have you played around with the new CSS Flexbox or Grid specs?
```
TODO
```
<a name="32"></a>
### + How is responsive design different from adaptive design?
```
TODO
```
<a name="33"></a>
### + Have you ever worked with retina graphics? If so, when and what techniques did you use?
```
TODO
```
<a name="34"></a>
### + Is there any reason you'd want to use translate() instead of absolute positioning, or vice-versa? And why?
```
TODO
```



