---
layout: post
title: "Coding and Cookies Session 1: HTML, CSS, GIT"
date:   2015-10-10 16:25:00
categories: tutorials
---
#Demo the things
We're making the CV I'm showing off at [hugodf.github.io/codingandcookies1](http://hugodf.github.io/codingandcookies1).

You get the whole repo at many stages at [github.com/HugoDF/codingandcookies1](https://github.com/HugoDF/codingandcookies1)
#Get the HTML set up
Create your HTML elements and declare the doctype (document type) like so:

```html
<!doctype html>
<html>
  <head>
  </head>
  <body>
  </body>
</html>
```

In your `head` tag add the following: `<meta description="have some description for your page">`

Quick rundown of vocabulary `meta` is the tag (like `html`, `head`, `body`), description is an attribute (which we'll see more instances of later). We use the term **element** and **tag** quite interchangeably although they aren't quite the same. The tag is more what you would have in your .html file while you edit it and the element is more what you see in the browser (as far as I can explain in a non-garbled way).

Some elements have an opening and a closing tag while others self-close. A self-closing tag is usually one that doesn't contain anything that's meant to be displayed.

Now add `<title></title>` under the meta-description tag we've just put into our code. 

Within the title tag, put the title of the page "CV - YOUR NAME".

Our code now looks like this:

```html
<!doctype html>
<html>
  <head>
    <meta description="CV of YOUR NAME">
    <title>CV - YOUR NAME</title>  
  </head>
  <body>

  </body>
</html>
```

Opening this up will show you a blank page, but the "title" tag means that the browser knows how to name the page (you can see "CV - YOUR NAME" on the tab in which it's open).

![Shot of the title bar][image-1]

Now you can inspect the source code by right-clicking on the page and clicking "inspect element". You can inspect the page and opening up the tags, you see that our code is there.

![Inspector][image-2]

#Get started with the header
Now let's start by making the first section of the CV, the header section.

This is the header of the CV right? 

Well that's the name of the tag: `header`. Inside our header, we have headings of different sizes. The heading elements are `h1`, `h2`, `h3`, `h4` and so on.

Add the following code to your `cv.html` file (after the opening `body` tag).

```html
<header>
  <h1>Hugo Di Francesco</h1>
  <h2>Cookie Master</h2>
</header>
```

Go to your browser and refresh the page. Ok it's not that pretty but hey, we're getting content up right?

Next we're going to tackle that section on the left, the one that has your contact details, skills, languages and so on. Again we're going to use a fancy HTML5 tag called `aside`. You can now call yourself a HTML5 ninja (disclosure I have never used this tag, ever because you can replicate its behaviour with generic elements... more on that later). Your body tag should look something like this:

```html
<body>
  <header>
    <h1>Hugo Di Francesco</h1>
    <h2>Cookie Master</h2>
  </header>
  <aside>
    My skills are going to go here
  </aside>
</body>
```
##Sidebar content creation
We now need to complete the first section (the sidebar) which is "contact".
We're going to open up a `div` element (div stands for division, this is one of the generic elements I was talking about earlier). Within it we're going to put a heading, a `h3` (3 because it should be smaller and lower down the hierarchy of the page with regards to the name and current position) with "contact". So `aside` looks like this:

```html
<aside>
  <div>
    <h3>Contact</h3>
  </div>
</aside>
```

###Anchors (links)
Within "contact" we probably want to add some details right? Like an email and a website URL. The fun bit is that when someone clicks on either of those, we can actually make them interact.
This is done with the `a` tag, the "anchor" tag. This tag has an attribute called `href` which stands for hypertext reference which means we can point it to say a website or an email address (email is some wizardry if I'm honest). After the "contact" heading, let's add the following code:

```html
<h3>Contact</h3>
<p><a href="http://twitter.com/hugo__df">@hugo__df</a></p>
<p><a href="mailto:hdifrancesco@gmail.com">hdifrancesco@gmail.com</a></p>
```

Ok so this line makes sense right?

```html
<p><a href="http://twitter.com/hugo__df">@hugo__df</a></p>
```

We're pointing the hypertext reference to `http://hugodf.github.io` (which is my personal page). Note that we are putting `http://` at the start, this tells the browser we're not trying to direct to another page on our site which would have a `href` value of `/page_name`.

```html
<a href="mailto:hdifrancesco@gmail.com">hdifrancesco@gmail.com</a>
```

Our next line is more interesting. In the `href`, we're stating `mailto`, this is a cool trick that allows you to tell the browser:

"Hey, you should open an email client with `hdifrancesco@gmail.com` as the recipient". 

Which, when you click it, is exactly what it does. You can look up more tricks like "telephone link" (which does something similar to what `mailto` does but for a phone).

What do the `p` tags do? 

Well remove them and see. The `p` or paragraph tag tells the browser "this is a paragraph" so there's a line break after it. In HTML terms, `p` is displayed as a `block`, whereas `a`'s are displayed `inline`. Other elements that display as `block` (that we've seen) are `div`, `aside` and the `h_` (heading) family.

Onto the next section of the left column. We need to add languages and expertise right? So let's add the following (pretty much just copy paste your "contact" `div` and change the content)

```html
<div>
  <h3>Languages</h3>
  <p>Fluent: HTML, CSS, Javascript</p>
  <p>Conversational: Ruby, Python, Java</p>
</div>
<div>
  <h3>Skills</h3>
  <h4>Linguistic</h4>
  <p>French, English, Spanish</p>
  <h4>Eating-abilities</h4>
  <p>Ben&amp;Jerry's champion of 10 Downing Street</p>
</div>
```

Ok so we know what those `h4` and `p` and all that stand for... What about `&amp;`?

Well, that's just an ampersand, HTML needs to use `&` to designate the start of some special characters (like right arrow: `$rarr;`) so they made `&` a special character :) how lovely.

Alright so now we look like this:

![bare HTML][image-3]

##The CV
Let's tackle the main section of the CV

We know what `div`s are now so let's just get straight into it:
- We're going to add a `div`after your previous code.
- Inside that, add a `p` that contains your intro text/statement.
So you've got:

```html
<div class="main-feed">
  <p>I do some things like coding and cookies, but then again, I'm not too into it you know</p>
</div>
```

##Class attribute

What does `class="main-feed"` do?

`class` is an attribute, because we're using `div` which is a generic element, we want to give that section a bit more meaning by naming it with a class (also we're going to need this to style it with CSS later). Apart from that (being used for styling and scripting), it doesn't do anything˜ functionally.

We're going to add sections/entries to your CV, they look something like this:

```html
<div class="section">
  <h3>Education</h3>
    <div class="entry">
      <span class="date">2012-2015</span>
      <h4>Hello World School</h4>
      <p>Spent way too long learning the ways of demons and men</p>
    </div>
    <div class="entry">
      <span class="date">2011-2012</span>
      <h4>Om nom nom Oratory</h4>
      <p>I can eat cookies... A lot of them</p>
    </div>
</div>
```

Here, a `section`-class element is something like "experience" or "education" and an `entry` is something that describes your experience and has the date.

We can add as many of these entries and sections as we want, just make sure to use a h3 and to have nice nesting. Adding a couple more we end up with something like the following:

```html
<div class="main-feed">
  <p>I do some things like coding and cookies, but then again, I'm not too into it you know</p>
  <div class="section">
    <h3>Education</h3>
    <div class="entry">
      <span class="date">2012-2015</span>
      <h4>Hello World School</h4>
      <p>Spent way too long learning the ways of demons and men</p>
    </div>
    <div class="entry">
      <span class="date">2011-2012</span>
      <h4>Om nom nom Oratory</h4>
      <p>I can eat cookies... A lot of them</p>
    </div>
  </div>
  <div class="section">
    <h3>Experience</h3>
    <div class="entry">
      <span class="date">April 2015</span>
      <h4>Beer Picker, <a href="beerpicker.herokuapp.com">beerpicker.herokuapp.com</a></h4>
      <p>Randomly picks out some beers: Sinatra, YAML, CSS</p>
    </div>
  </div>
</div>
```

#Time for styling

Let's create a file called `cv.css` (in the same folder as cv.html) and link to it in our `head` tag:

```html
<head>
  <meta description="CV of YOUR NAME">
  <title>CV - YOUR NAME</title>
  <link rel="stylesheet" type="text/css" href="cv.css">
</head>
```

Now in `cv.css`, enter the following:

```css
body{
  font-family: 'Helvetica', sans-serif;
  background-color: red;
}
```

As you can see, we've just changed the font and turned the background red. Let's delete that rule (`background-color: red`) and the background goes back to white.

##CSS declarations

There are two parts to a CSS declaration:

1. The selector (here `body`), it tells the browser which element the rules we define in the curly braces (`{}`) should apply to.

2. The rule, which itself is two things: a property (`font-family`) following by a colon (`:`) and a value (`'Helvetica', sans-serif`)

Let's clean up the whole thing.
Add this element to `cv.html` so that you can select most of the content:

```html
<body>
  <div class="cv-container">
    <header>
    <!-- all the things -->
  </div>
</body>
```

Enter these rules in cv.css:

```css
.cv-container{
  max-width: 1024px;
  margin:auto;
}
```

What the above does is tell the browser that the width of `.cv-container` should never exceed `1024px`, `margin: auto` pushes it to the center.

Why is there a `.` before `cv-container`? 

That's our way of telling the browser we're selecting a class. We explained selectors above and now we're applying this, `.cv-container` is a selector that selects all elements that have `class="cv-container"`. If we have selector `#menu-toggle` it would select the first element with `id = "menu-toggle"`.

Now the `margin: auto` rule is actually a trick/workaround that a lot of developers use with `display: block` elements that have a width and need to be centered. The point here is that you will need to experiment _a lot_ with CSS to get good at it (ie. be able to transform a design into code as fast as me :) ).

So we look a tiny bit neater since we're not sprawled across the page any more.

##Big headings

Let's change the size of the headings (in the `header`). Remember they were wrapped in `h1` and `h2` tags. So now let's style them:

```css
h1{
  font-size: 80px;
  font-weight: 100;
  margin-bottom: 20px;
}
h2{
  font-size: 60px;
  font-weight: 100;
}
```

Quick explanation:

- `font-size` determines the height of the letters

- `font-weight` determines the boldness

- `margin-bottom` determines the margin at the bottom of the element

Pretty straightforward right?

The difficulty in CSS is remembering the rule (or set of rules) that do what you want them to. Sometimes their names are easy to remember and conceptualise  other times it's dark, quirky names.

To make it look like the website we also want to center align the headings, and we're going to learn a new trick.
We want to center both headings so we could write something like this.

```css
h1{
  text-align: center;
  //some other rules
}
h2{
  text-align: center;
  //some other rules
}
```

but we can also write it like this:

```css
h1, h2{
  text-align: center;
}
```

This way is a bit more efficient since you're not repeating yourself, you lose a bit of clarity but as long as you remember you did this, you should be ok.

Our `header` looks finished, let's move on.

##The floating sidebar

We've got our fancy HTML5 tag `aside`, it's supposed to be to the left... And it's supposed to not be full-width.

This should fix the full-width:

```css
aside{
  width: 20%;
}
```

Quick reminder: block elements take up all the space given to them (they take up the whole line). So even though the `aside` doesn't take up the width of the page, because it's a block, the rest of the content is on another line.

What we need to do is change that `display` property. `inline-block` is a mix between `inline` and `block`. It has a width (unlike `inline`) but it doesn't take up a whole line (unlike `block`). We have:

```css
aside{
  width: 20%;
  display: inline-block;
}
```

Careful (check in your browser), that doesn't work, what we're missing is `float: left` to tell the browser to stack the `aside` as far left as possible (there are no other elements floated to the left so it goes all the way to the left).

```css
aside{
  width: 20%;
  display: inline-block;
  float: left;
}
```

## The main section

We've got an issue here:

![wrapping text][image-4]

The text wraps, so what we want to do is something similar to what we did with the sidebar to the `.main-feed` except this time, we'll `float: right`:

```css
.main-feed{
  width: 80%;
  float: right;
}
```

##10% date

We can make the date be stuck to the left by using the following declarations:

```css
.date{
  width: 10%;
  float: left;
}
```

##Specific paragraphs

To make the rest of the entry look nice we want to bump the `p`s to the right a little bit, this can be achieved like so:

```css
.entry p{
  margin-left: 10%;
}
```

We've already seen the `margin-left` property, what we haven't yet seen is the `.entry p` selector. Just like using the `,` (comma) allows us to declare rules for multiple selectors, adding one after the other allows us to increase the specificity of the selector. This selector says `select 'p's that are within an element of class 'entry'`. This is quite useful when overriding rules in particular contexts.

Another thing we could do is something like this:

```css
.entry.some-other-class{
  //some rules
}
```

This would select elements that have **both** the `entry` and `some-other-class` classes.

This means: _DON'T FORGET YOUR SPACES_  since `.a.b` is different to `.a .b` :) .

## Anchor-style

These links look terrible:

![ugly default links][image-5]

Let's get rid of the terrible colour, the underline and get them some nice effects on hover, we want them to stand out from the text but not be _that_ ugly.

Here's the CSS:

```css
a{
  text-decoration: none;
  color: #666; //this is dark grey
}
a:hover, a:focus, a:active{
  color: #000; //this is black
}
```

Now they look nicer :) and they give you feedback when you hover over them.

![Nice looking links][image-6]

Let's explain this though: `a:hover, a:focus, a:active`

`:hello` selectors are what we call pseudo-selectors, they allow you to select an element only under certain conditions. Here it's selected when the link (anchor) is hovered, focused, and  active (these are quite rare but are triggered sometimes on phones before the next page loads or the click registers). There are others though like `:first-child`, `:after` (there are extensive lists on places like google).

##Format those headings aside

We want the headings in the aside to be a bit nicer don't we?

Let's right-align the whole thing and make the `h4` sub-headings italic for good measure.

```css
aside{
  width: 20%;
  display: inline-block;
  float: left;//these are the old rules, just find where the aside selector is in your CSS file
  text-align: right;
}
aside h4{
  font-style: italic;
}
```

Now we're looking good :)

The easiest way to put this online is to use GitHub Pages, they've got really nice documentation so just follow the guides :)

[image-1]: http://hugodf.github.io/img/tutorials/screen-1.jpg
[image-2]: http://hugodf.github.io/img/tutorials/screen-2.jpg
[image-3]: http://hugodf.github.io/img/tutorials/screen-3.jpg
[image-4]: http://hugodf.github.io/img/tutorials/screen-4.jpg
[image-5]: http://hugodf.github.io/img/tutorials/screen-5.jpg
[image-6]: http://hugodf.github.io/img/tutorials/screen-6.jpg