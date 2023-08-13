---
layout: post
title: "Markdown Cheatsheet"
date: 2016-04-19 19:31:43 +0700
categories: [Information Technology, Tech Tips and Tricks]
tags: [linux, windows]
---

**Markdown** is a way to style text on the web. You control the display of the document; formatting words as
bold or italic, adding images, and creating lists are just a few of the things we can do with Markdown. Mostly,
Markdown is just regular text with a few non-alphabetic characters thrown in, like # or \*.

## Markdown Syntax

### Headers

```
# This is an <h1> tag
## This is an <h2> tag
###### This is an <h6> tag
```

### Emphasis

```
*This text will be italic*
_This will also be italic_
**This text will be bold**
__This will also be bold__
*You **can** combine them*
```

### Lists

#### Unordered

```
* Item 1
* Item 2
 * Item 2a
 * Item 2b
```

#### Ordered

```
1. Item 1
2. Item 2
3. Item 3
 * Item 3a
 * Item 3b
```

### Images

```
![Vận Già Logo](/images/logo.png)
Format: ![Alt Text](url)
```

![Markdown Logo](https://upload.wikimedia.org/wikipedia/commons/thumb/4/48/Markdown-mark.svg/200px-Markdown-mark.svg.png)

### Links

```
http://vegetaz.github.io
[Vận Già](http://vegetaz.github.io)
```

### Block Quotes

```
As Vận Già said:
> I’ve always been more interested
> in the future than in the past.
```

### Backsplash Escapes

Markdown allows you to use backslash escapes to generate literal characters which would otherwise have special meaning in Markdown's formatting syntax.

```
\*literal asterisks\*
```

Markdown provides backslash escapes for the following characters:

```
\ backslash
` backtick
* asterisk
_ underscore
{} curly braces
[] square brackets
() parentheses
# hash mark
+ plus sign
- minus sign (hyphen)
. dot
! exclamation mark
```

## Github Flavored Markdown

### Username @mentions

Typing an @ symbol, followed by a username, will notify that person to come and view the comment. This is called an “@mention”, because you’re mentioning the individual. You can also @mention teams within an organization.

### Issue References

Any number that refers to an Issue or Pull Request will be automatically
converted into a link

```
#1
github-flavored-markdown#1
vegetaz/github-flavored-markdown#1
```

### Emoji

To see a list of every image we support, check out [emoji-cheat-sheet](ww.emoji-cheat-sheet.com)

```
GitHub supports emoji!
:+1: :sparkles: :camel: :tada: :rocket: :metal: :octocat:
```

:+1: :sparkles: :camel: :tada: :rocket: :metal: :octocat:

### Fenced Code Blocks

Markdown coverts text with four leading spaces into a code block; with GFM you can wrap your code with ` ``` ` to create a code block without the leading spaces. Add an optional language identifier and your code will get syntax highlighting

```javascript
function test() {
	console.log("look ma’, no spaces")
}
```

### Task Lists

```
- [x] this is a complete item
- [ ] this is an incomplete item
- [x] @mentions, #refs, [links](), **formatting**, and <del>tags</del> supported
- [x] list syntax required (any unordered or ordered list supported)
```

- [x] this is a complete item
- [ ] this is an incomplete item
- [x] @mentions, #refs, [links](), **formatting**, and <del>tags</del> supported
- [x] list syntax required (any unordered or ordered list supported)

### Tables

You can create tables by assembling a list of words and dividing them
with hyphens - (for the first row), and then separating each column
with a pipe | :

```
First Header | Second Header
------------ | -------------
Content cell 1 | Content cell 2
Content column 1 | Content column 2
```

| First Header     | Second Header    |
| ---------------- | ---------------- |
| Content cell 1   | Content cell 2   |
| Content column 1 | Content column 2 |

To Be continued...
