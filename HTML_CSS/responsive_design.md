# Responsive Design

!["responsive-web-design"](/images/responsive-web-design.jpg)

There are two main types of design:
- Fluid: stretches and shrinks to fit the screen
- Fixed: has the same dimensions regardless of the screen size

Mobile and small screens typically use fluid design, while large screens typically have fixed designs.

## Media Queries

Adding `@mediaqueries` to the .css file allows for different styling characteristics at various "break points".

```css
@media only screen and (min-width: 768px) {
  .feature {
    width: 33.3%;
    line-height: 600px;
  }

  .content {
    width: 66.7%;
    float: right
  }

  .footer {
    clear: right;
  }
}
```

### Disable Viewport Zooming

The following **needs** to be added to the `<head>` in the HTML file to ensure proper styling on all devices.

```html
<meta name='viewport' content='width=device-width, initial-scale=1.0, maximum-scale=1.0' />
```

## Sass

From Sass:
> CSS on its own can be fun, but stylesheets are getting larger, more complex, and harder to maintain. This is where a preprocessor can help. Sass lets you use features that don't exist in CSS yet like variables, nesting, mixins, inheritance and other nifty goodies that make writing CSS fun again.

## Flexbox

> The main idea behind the flex layout is to give the container the ability to alter its items' width/height (and order) to best fill the available space (mostly to accommodate to all kind of display devices and screen sizes). A flex container expands items to fill available free space or shrinks them to prevent overflow.

```css
.container {
  display: flex; /* or inline-flex */
  flex-direction: row | row-reverse | column | column-reverse;
  flex-wrap: nowrap | wrap | wrap-reverse;
  flex-flow: <‘flex-direction’> || <‘flex-wrap’;
  justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly | start | end | left | right;
  align-items: stretch | flex-start | flex-end | center | baseline | first baseline | last baseline | start | end | self-start | self-end;
  align-content: flex-start | flex-end | center | space-between | space-around | space-evenly | stretch | start | end | baseline | first baseline | last baseline;
}

.item {
  order: <integer>; /* default is 0 */
  flex-grow: <number>; /* default 0 */
  flex-shrink: <number>; /* default 1 */
  flex-basis: <length> | auto; /* default auto */
  flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ];
  align-self: auto | flex-start | flex-end | center | baseline | stretch;
}
```
