---
title: "Browser"
---

# Browser

> The dream behind the Web is of a common information space in which we communicate by sharing information. Its universality is essential: the fact that a hypertext link can point to anything, be it personal, local or global, be it draft or highly polished.
> 
> Tim Berners-Lee, The World Wide Web: *A very short personal history*[^quote]

##  Protocols

*Styles of communication.*

- **HTTP(S):** *Hypertext Transfer Protocol*, for retrieving named resources. Treats the network as a stream (with fixed order).
- **TCP:** *Transmission Control Protocol*, associates transmissions with ports allowing for unique connections to be established. Listening computer is the **server** connecting is the **client**. Allows for two-way communication.

### The World Wide Web (www)

Set of protocols for visiting pages. Connecting requires listening on port 80 to HTTP protocol. Documents are named via **URL**, *Uniform Resource Locator*, in the form protocol (`http`), server (`quartz.defyingentropy.ml`), then path (`wiki/browser`).

URL: protocol, server, path
ip

## HTML

Structured tree of tags, called the **DOM**, *Document Object Model*. Tags are wrapped in angle brackets `<>`.

Characters with special meaning, such as angle brackets, are called "entities" and expressed between `&` and `;`, like `&lt;` for `<`. As an intellectual writing in markdown, I'm not worried about that.

## JS

JS can be included in HTML via the `<script>` tag. Can either include it literally like 

```HTML
<script>alert("Popup!");</script>
```

or for longer files specify a source:

```HTML
<script src=pop.js></script>
```

Some HMTL attributes, like `button`, contain JS attributes.

### DOM

Can access the DOM through `document` with root node `document.documentElement`. All nodes have a type code:

- 1: element
- 3: text
- 8: comment

Good ol' slowly-evolving standard.

Can attach arbitrary attributes to HTML nodes then get with `getAttribute(name)`.

#### Traversal

![Links between DOM nodes](https://eloquentjavascript.net/img/html-links.svg)

- `document.body.getElementsByTagName(tag)`: returns a list of `tag` elements. The list is live, cast to array to make it static.
- `document.getElementById(id)`: can be used if an `id` is attached to a tag, i.e. 

```HTML
<p>My ostrich Gertrude:</p>
<p><img id="gertrude" src="img/ostrich.png"></p>

<script>
  let ostrich = document.getElementById("gertrude");
  console.log(ostrich.src);
</script>
```
- `document.getElementByClassName(class)`

#### Selectors

CSS selector syntax can be used in `querySelector(selector)` and `querySelectorAll(selector)` to find elements.
#### Editing

- `remove()`: remove from parent node
- `appendChild(node)`: adds to end of child of child list
- `replaceChild(new, old)`: replaces `old` with `new`.
- `insertBefore(new, old)`: inserts `new` before `old`.
- `createTextNode(text)`: creates node with `text`.
- `createElement(type)`: creates a node of `type`.

## Styling

Can change `style` property of blocks:

```HTML
<p><a href=".">Normal link</a></p>
<p><a href="." style="color: green">Green link</a></p>
```

JS gets access through `element.style.property_name`, e.g. `para.style.color = "magneta"`.  Properties with hyphenation, such as `font-family` get camelCased, `fontFamily`.

### Fields

- `color: ...`: self-explanatory
- `display: inline, block, none`: how the element should be displayed
- `position: static, relative, absolute`: `relative` allows an off-set from `static` position. `absolute` ignores other elements and allows for exact positioning.

### CSS

*Cascading Style Sheets*, named as such because multiple rules are combined to determine the final style, with later rules overruling earlier ones.

Identifiers include `.class_name`, `#id`, or simple `element`. They can be strung together, e.g. `p#main.a.b` matches a paragraph with id `main` and classes `a` and `b`. Precedence favors specificity.

Notation `p > a {...}` applies styling to all `<a>` tags that are children of `<p>` tags and `p a {...}` does the same except they can be indirect children.

[^quote]: borrowed from [here](https://eloquentjavascript.net/13_browser.html)