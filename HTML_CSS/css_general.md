# CSS General

> Cascading Style Sheets

A presentation language created to style the apperance of content - using, for example, font or colors.

Common practice is to have a separate .css file for each major component (i.e. nav.css, header.css)

## Terms
* Selectors 
  * A selector designates exactly which element or elements within our HTML to target and apply styles
  * Generally target an attribute value (id or class), or target the type of element (`<h1>`, `<p>`).
* Properties
  * A property defines the styles that will be applied to that element.
  * Fall after selector within curly brackets, and immediately preceding a colon.
* Values
  * Determine the behaviou of a property
* CSS Resets
  * To ensure cross-browser compatibility, CSS Resets wipe all CSS styles
  * (http://meyerweb.com/eric/tools/css/reset)

## Selectors

`.class1 {}` --> basic single class
`.class1.class2 {}` --> both classes
`div {}` --> or its name (i.e. h2, p)
`#id {}` --> id tag
`.class1 div` --> specific item of a class (i.e. h2)

### Specificity Hierarchy

01 - Inline Styles (within HTML)
02 - IDs
03 - Classes, attributes, pseudo-classes
04 - Elements, pseudo-elements

In the event of a tie, the most recently loaded .css file wins

## Positioning

`float: left (right, etc)` --> Provides basic implementation of Responsive Web App
\
```css
position: relative;
top (down, left, right): ___px;
```
---> provides an offset from the items <em>static<em> position

```css
position: abosulite;
top (down, left, right): ___px;
```
--> provieds an offset from the items <em>parent<em> position

```css
position: fixed;
top: 0px;
left: 0px;
right: 0px;
```
---> provides an offset from the <em>browser viewport<em> (i.e. a static nav bar)

`z-index: 1` --> used to change the order in which elements are stacked (2 is higher than 1)


## Properties

`background-image: url("/images/cool_background.png")`
--> loads a background image (http://transparenttextures.com) over the item
\


## Design Resources

A site that generates colour schemes is: [coolors](https://coolors.co)
\
Flat icons: [flaticons](https://www.flaticon.com)
\
For special buttons: [bttn.css](https://bttn.surge.sh)
