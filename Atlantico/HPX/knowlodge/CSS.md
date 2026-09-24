
https://css-tricks.com/snippets/css/a-guide-to-flexbox/



### Flexbox basics and terminology 
![A diagram explaining flexbox terminology. The size across the main axis of flexbox is called the main size, the other direction is the cross size. Those sizes have a main start, main end, cross start, and cross end.](https://css-tricks.com/wp-content/uploads/2018/11/00-basic-terminology.svg)

Items will be laid out following either the `main axis` (from `main-start` to `main-end`) or the cross axis (from `cross-start` to `cross-end`).

- **main axis** – The main axis of a flex container is the primary axis along which flex items are laid out. Beware, it is not necessarily horizontal; it depends on the `flex-direction` property (see below).
- **main-start | main-end** – The flex items are placed within the container starting from main-start and going to main-end.
- **main size** – A flex item’s width or height, whichever is in the main dimension, is the item’s main size. The flex item’s main size property is either the ‘width’ or ‘height’ property, whichever is in the main dimension.
- **cross axis** – The axis perpendicular to the main axis is called the cross axis. Its direction depends on the main axis direction.
- **cross-start | cross-end** – Flex lines are filled with items and placed into the container starting on the cross-start side of the flex container and going toward the cross-end side.
- **cross size** – The width or height of a flex item, whichever is in the cross dimension, is the item’s cross size. The cross size property is whichever of ‘width’ or ‘height’ that is in the cross dimension.


### CSS Flexbox properties

![](https://css-tricks.com/wp-content/uploads/2018/10/01-container.svg)

## [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-properties-for-the-parentflex-container)Properties for the Parent  
(flex container)

#### [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-display)display

This defines a flex container; inline or block depending on the given value. It enables a flex context for all its direct children.

```css
.container {
  display: flex; /* or inline-flex */
}
```

Note that CSS columns have no effect on a flex container.

#### [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-flex-direction)flex-direction

![the four possible values of flex-direction being shown: top to bottom, bottom to top, right to left, and left to right](https://css-tricks.com/wp-content/uploads/2018/10/flex-direction.svg)

  
This establishes the main-axis, thus defining the direction flex items are placed in the flex container. Flexbox is (aside from optional wrapping) a single-direction layout concept. Think of flex items as primarily laying out either in horizontal rows or vertical columns.

```css
.container {
  flex-direction: row | row-reverse | column | column-reverse;
}
```

- `row` (default): left to right in `ltr`; right to left in `rtl`
- `row-reverse`: right to left in `ltr`; left to right in `rtl`
- `column`: same as `row` but top to bottom
- `column-reverse`: same as `row-reverse` but bottom to top

#### [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-flex-wrap)flex-wrap

![two rows of boxes, the first wrapping down onto the second](https://css-tricks.com/wp-content/uploads/2018/10/flex-wrap.svg)

By default, flex items will all try to fit onto one line. You can change that and allow the items to wrap as needed with this property.

```css
.container {
  flex-wrap: nowrap | wrap | wrap-reverse;
}
```

- `nowrap` (default): all flex items will be on one line
- `wrap`: flex items will wrap onto multiple lines, from top to bottom.
- `wrap-reverse`: flex items will wrap onto multiple lines from bottom to top.

There are some [visual demos of `flex-wrap` here](https://css-tricks.com/almanac/properties/f/flex-wrap/).

#### [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-flex-flow)flex-flow

This is a shorthand for the `flex-direction` and `flex-wrap` properties, which together define the flex container’s main and cross axes. The default value is `row nowrap`.

```css
.container {
  flex-flow: column wrap;
}
```

#### [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-justify-content)justify-content

![flex items within a flex container demonstrating the different spacing options](https://css-tricks.com/wp-content/uploads/2018/10/justify-content.svg)

  
This defines the alignment along the main axis. It helps distribute extra free space leftover when either all the flex items on a line are inflexible, or are flexible but have reached their maximum size. It also exerts some control over the alignment of items when they overflow the line.

```css
.container {
  justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly | start | end | left | right ... + safe | unsafe;
}
```

- `flex-start` (default): items are packed toward the start of the flex-direction.
- `flex-end`: items are packed toward the end of the flex-direction.
- `start`: items are packed toward the start of the `writing-mode` direction.
- `end`: items are packed toward the end of the `writing-mode` direction.
- `left`: items are packed toward left edge of the container, unless that doesn’t make sense with the `flex-direction`, then it behaves like `start`.
- `right`: items are packed toward right edge of the container, unless that doesn’t make sense with the `flex-direction`, then it behaves like `end`.
- `center`: items are centered along the line
- `space-between`: items are evenly distributed in the line; first item is on the start line, last item on the end line
- `space-around`: items are evenly distributed in the line with equal space around them. Note that visually the spaces aren’t equal, since all the items have equal space on both sides. The first item will have one unit of space against the container edge, but two units of space between the next item because that next item has its own spacing that applies.
- `space-evenly`: items are distributed so that the spacing between any two items (and the space to the edges) is equal.

Note that that browser support for these values is nuanced. For example, `space-between` never got support from some versions of Edge, and start/end/left/right aren’t in Chrome yet. MDN [has detailed charts](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content). The safest values are `flex-start`, `flex-end`, and `center`.

There are also two additional keywords you can pair with these values: `safe` and `unsafe`. Using `safe` ensures that however you do this type of positioning, you can’t push an element such that it renders off-screen (e.g. off the top) in such a way the content can’t be scrolled too (called “data loss”).

#### [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-align-items)align-items

![demonstration of differnet alignment options, like all boxes stuck to the top of a flex parent, the bottom, stretched out, or along a baseline](https://css-tricks.com/wp-content/uploads/2018/10/align-items.svg)

  
This defines the default behavior for how flex items are laid out along the **cross axis** on the current line. Think of it as the `justify-content` version for the cross-axis (perpendicular to the main-axis).

```css
.container {
  align-items: stretch | flex-start | flex-end | center | baseline | first baseline | last baseline | start | end | self-start | self-end + ... safe | unsafe;
}
```

- `stretch` (default): stretch to fill the container (still respect min-width/max-width)
- `flex-start` / `start` / `self-start`: items are placed at the start of the cross axis. The difference between these is subtle, and is about respecting the `flex-direction` rules or the `writing-mode` rules.
- `flex-end` / `end` / `self-end`: items are placed at the end of the cross axis. The difference again is subtle and is about respecting `flex-direction` rules vs. `writing-mode` rules.
- `center`: items are centered in the cross-axis
- `baseline`: items are aligned such as their baselines align

The `safe` and `unsafe` modifier keywords can be used in conjunction with all the rest of these keywords (although note [browser support](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items)), and deal with helping you prevent aligning elements such that the content becomes inaccessible.

#### [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-align-content)align-content

![examples of the align-content property where a group of items cluster at the top or bottom, or stretch out to fill the space, or have spacing.](https://css-tricks.com/wp-content/uploads/2018/10/align-content.svg)

  
This aligns a flex container’s lines within when there is extra space in the cross-axis, similar to how `justify-content` aligns individual items within the main-axis.

**Note:** This property only takes effect on multi-line flexible containers, where `flex-wrap` is set to either `wrap` or `wrap-reverse`). A single-line flexible container (i.e. where `flex-wrap` is set to its default value, `no-wrap`) will not reflect `align-content`.

```css
.container {
  align-content: flex-start | flex-end | center | space-between | space-around | space-evenly | stretch | start | end | baseline | first baseline | last baseline + ... safe | unsafe;
}
```

- `normal` (default): items are packed in their default position as if no value was set.
- `flex-start` / `start`: items packed to the start of the container. The (more supported) `flex-start` honors the `flex-direction` while `start` honors the `writing-mode` direction.
- `flex-end` / `end`: items packed to the end of the container. The (more support) `flex-end` honors the `flex-direction` while end honors the `writing-mode` direction.
- `center`: items centered in the container
- `space-between`: items evenly distributed; the first line is at the start of the container while the last one is at the end
- `space-around`: items evenly distributed with equal space around each line
- `space-evenly`: items are evenly distributed with equal space around them
- `stretch`: lines stretch to take up the remaining space

The `safe` and `unsafe` modifier keywords can be used in conjunction with all the rest of these keywords (although note [browser support](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items)), and deal with helping you prevent aligning elements such that the content becomes inaccessible.

#### [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-gap-row-gap-column-gap)gap, row-gap, column-gap

![](https://css-tricks.com/wp-content/uploads/2021/09/gap-1.svg)

[The `gap` property](https://css-tricks.com/almanac/properties/g/gap/) explicitly controls the space between flex items. It applies that spacing _only between items_ not on the outer edges.

```css
.container {
  display: flex;
  ...
  gap: 10px;
  gap: 10px 20px; /* row-gap column gap */
  row-gap: 10px;
  column-gap: 20px;
}
```

The behavior could be thought of as a _minimum_ gutter, as if the gutter is bigger somehow (because of something like `justify-content: space-between;`) then the gap will only take effect if that space would end up smaller.

It is not exclusively for flexbox, `gap` works in grid and multi-column layout as well.

![](https://css-tricks.com/wp-content/uploads/2018/10/02-items.svg)

## [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-properties-for-the-childrenflex-items)Properties for the Children  
(flex items)

#### [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-order)order

![Diagram showing flexbox order. A container with the items being 1 1 1 2 3, -1 1 2 5, and 2 2 99.](https://css-tricks.com/wp-content/uploads/2018/10/order.svg)

  
By default, flex items are laid out in the source order. However, the `order` property controls the order in which they appear in the flex container.

```css
.item {
  order: 5; /* default is 0 */
}
```

Items with the same `order` revert to source order.

#### [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-flex-grow)flex-grow

![two rows of items, the first has all equally-sized items with equal flex-grow numbers, the second with the center item at twice the width because its value is 2 instead of 1.](https://css-tricks.com/wp-content/uploads/2018/10/flex-grow.svg)

  
This defines the ability for a flex item to grow if necessary. It accepts a unitless value that serves as a proportion. It dictates what amount of the available space inside the flex container the item should take up.

If all items have `flex-grow` set to `1`, the remaining space in the container will be distributed equally to all children. If one of the children has a value of `2`, that child would take up twice as much of the space as either one of the others (or it will try, at least).

```css
.item {
  flex-grow: 4; /* default 0 */
}
```

Negative numbers are invalid.

#### [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-flex-shrink)flex-shrink

This defines the ability for a flex item to shrink if necessary.

```css
.item {
  flex-shrink: 3; /* default 1 */
}
```

Negative numbers are invalid.

#### [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-flex-basis)flex-basis

This defines the default size of an element before the remaining space is distributed. It can be a length (e.g. 20%, 5rem, etc.) or a keyword. The `auto` keyword means “look at my width or height property” (which was temporarily done by the `main-size` keyword until deprecated). The `content` keyword means “size it based on the item’s content” – this keyword isn’t well supported yet, so it’s hard to test and harder to know what its brethren `max-content`, `min-content`, and `fit-content` do.

```css
.item {
  flex-basis:  | auto; /* default auto */
}
```

If set to `0`, the extra space around content isn’t factored in. If set to `auto`, the extra space is distributed based on its `flex-grow` value. [See this graphic.](http://www.w3.org/TR/css3-flexbox/images/rel-vs-abs-flex.svg)

#### [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-flex)flex

This is the shorthand for `flex-grow,` `flex-shrink` and `flex-basis` combined. The second and third parameters (`flex-shrink` and `flex-basis`) are optional. The default is `0 1 auto`, but if you set it with a single number value, like `flex: 5;`, that changes the `flex-basis` to 0%, so it’s like setting `flex-grow: 5; flex-shrink: 1; flex-basis: 0%;`.

```css
.item {
  flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
}
```

**It is recommended that you use this shorthand property** rather than set the individual properties. The shorthand sets the other values intelligently.

#### [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-align-self)align-self

![One item with a align-self value is positioned along the bottom of a flex parent instead of the top where all the rest of the items are.](https://css-tricks.com/wp-content/uploads/2018/10/align-self.svg)

  
This allows the default alignment (or the one specified by `align-items`) to be overridden for individual flex items.

Please see the `align-items` explanation to understand the available values.

```css
.item {
  align-self: auto | flex-start | flex-end | center | baseline | stretch;
}
```

Note that `float`, `clear` and `vertical-align` have no effect on a flex item.

### [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-prefixing-flexbox)Prefixing Flexbox

CSS Flexbox is widely supported in all modern browsers, but requires some vendor prefixing to support the legacy browsers, like Internet Explorer (which has been discontinued for a while now). It doesn’t just include prepending properties with the vendor prefix, but there are actually entirely different property and value names. This is because the Flexbox spec has changed over time, creating an [“old”, “tweener”, and “new”](https://css-tricks.com/old-flexbox-and-new-flexbox/) versions.

Perhaps the best way to handle this is to write in the new (and final) syntax and run your CSS through [Autoprefixer](https://css-tricks.com/autoprefixer/), which handles the fallbacks very well.

Alternatively, here’s a Sass `@mixin` to help with some of the prefixing, which also gives you an idea of what kind of things need to be done:

```scss
@mixin flexbox() {
  display: -webkit-box;
  display: -moz-box;
  display: -ms-flexbox;
  display: -webkit-flex;
  display: flex;
}

@mixin flex($values) {
  -webkit-box-flex: $values;
  -moz-box-flex:  $values;
  -webkit-flex:  $values;
  -ms-flex:  $values;
  flex:  $values;
}

@mixin order($val) {
  -webkit-box-ordinal-group: $val;  
  -moz-box-ordinal-group: $val;     
  -ms-flex-order: $val;     
  -webkit-order: $val;  
  order: $val;
}

.wrapper {
  @include flexbox();
}

.item {
  @include flex(1 200px);
  @include order(2);
}
```

### [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-css-flexbox-examples)CSS Flexbox Examples

Let’s start with a very very simple example, solving an almost daily problem: perfect centering. It couldn’t be any simpler if you use CSS Flexbox.

```css
.parent {
  display: flex;
  height: 300px; /* Or whatever */
}

.child {
  width: 100px;  /* Or whatever */
  height: 100px; /* Or whatever */
  margin: auto;  /* Magic! */
}
```

This relies on the fact a margin set to `auto` in a flex container absorb extra space. So setting a margin of `auto` will make the item perfectly centered in both axes.

Now let’s use some more properties. Consider a list of 6 items, all with fixed dimensions, but can be auto-sized. We want them to be evenly distributed on the horizontal axis so that when we resize the browser, everything scales nicely, and without media queries.

```css
.flex-container {
  /* We first create a flex layout context */
  display: flex;

  /* Then we define the flow direction 
     and if we allow the items to wrap 
   * Remember this is the same as:
   * flex-direction: row;
   * flex-wrap: wrap;
   */
  flex-flow: row wrap;

  /* Then we define how is distributed the remaining space */
  justify-content: space-around;
}
```

Done. Everything else is just some styling concern. Below is a pen featuring this example. Be sure to go to CodePen and try resizing your windows to see what happens.

Let’s try something else. Imagine we have a right-aligned navigation element on the very top of our website, but we want it to be centered on medium-sized screens and single-columned on small devices. Easy enough.

```css
/* Large */
.navigation {
  display: flex;
  flex-flow: row wrap;
  /* This aligns items to the end line on main-axis */
  justify-content: flex-end;
}

/* Medium screens */
@media all and (max-width: 800px) {
  .navigation {
    /* When on medium sized screens, we center it by evenly distributing empty space around items */
    justify-content: space-around;
  }
}

/* Small screens */
@media all and (max-width: 500px) {
  .navigation {
    /* On small screens, we are no longer using row direction but column */
    flex-direction: column;
  }
}
```

Let’s try something even better by playing with flex items flexibility! What about a mobile-first 3-columns layout with full-width header and footer. And independent from source order.

```css
.wrapper {
  display: flex;
  flex-flow: row wrap;
}

/* We tell all items to be 100% width, via flex-basis */
.wrapper > * {
  flex: 1 100%;
}

/* We rely on source order for mobile-first approach
 * in this case:
 * 1. header
 * 2. article
 * 3. aside 1
 * 4. aside 2
 * 5. footer
 */

/* Medium screens */
@media all and (min-width: 600px) {
  /* We tell both sidebars to share a row */
  .aside { flex: 1 auto; }
}

/* Large screens */
@media all and (min-width: 800px) {
  /* We invert order of first sidebar and main
   * And tell the main element to take twice as much width as the other two sidebars 
   */
  .main { flex: 3 0px; }
  .aside-1 { order: 1; }
  .main    { order: 2; }
  .aside-2 { order: 3; }
  .footer  { order: 4; }
}
```

### [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-flexbox-tricks)Flexbox tricks!

[flexbox](https://css-tricks.com/tag/flexbox/) [images](https://css-tricks.com/tag/images/)

**Article** on Oct 3, 2019

### [Adaptive Photo Layout with Flexbox](https://css-tricks.com/adaptive-photo-layout-with-flexbox/)

[![](https://i0.wp.com/css-tricks.com/wp-content/cache/breeze-extra/gravatars/xekW7bvN-80x80.jpeg?resize=80%2C80&ssl=1)](https://css-tricks.com/author/timvandamme/)[Tim Van Damme](https://css-tricks.com/author/timvandamme/)

[flexbox](https://css-tricks.com/tag/flexbox/)

**Article** on Oct 8, 2020

### [Balancing on a Pivot with Flexbox](https://css-tricks.com/balancing-on-a-pivot-with-flexbox/)

[![](https://i0.wp.com/css-tricks.com/wp-content/cache/breeze-extra/gravatars/me-80x80.jpg?resize=80%2C80&ssl=1)](https://css-tricks.com/author/j-merkenich/)[Julian Merkenich](https://css-tricks.com/author/j-merkenich/)

[ellipsis](https://css-tricks.com/tag/ellipsis/) [overflow](https://css-tricks.com/tag/overflow/) [text-overflow](https://css-tricks.com/tag/text-overflow/)

**Link** on Jul 21, 2020

### [Using Flexbox and text ellipsis together](https://css-tricks.com/using-flexbox-and-text-ellipsis-together/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/41a6f9778d12dfedcc7ec3727d64a12491d75d9a65d4b9323feb075391ae6795)](https://css-tricks.com/author/chriscoyier/)[Chris Coyier](https://css-tricks.com/author/chriscoyier/)

**Article** on Jun 19, 2015

### [Useful Flexbox Technique: Alignment Shifting Wrapping](https://css-tricks.com/useful-flexbox-technique-alignment-shifting-wrapping/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/41a6f9778d12dfedcc7ec3727d64a12491d75d9a65d4b9323feb075391ae6795)](https://css-tricks.com/author/chriscoyier/)[Chris Coyier](https://css-tricks.com/author/chriscoyier/)

[ecommerce](https://css-tricks.com/tag/ecommerce/) [shopify](https://css-tricks.com/tag/shopify/)

**Article** on Jan 15, 2016

### [Designing A Product Page Layout with Flexbox](https://css-tricks.com/designing-a-product-page-layout-with-flexbox/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/d348b21b603ab8dbb124029321608bd74ec16726f7bfaf1a23ea1b613d3e5284)](https://css-tricks.com/author/levin-mejia/)[Levin Mejia](https://css-tricks.com/author/levin-mejia/)

**Article** on May 11, 2016

### [Flexbox and Truncated Text](https://css-tricks.com/flexbox-truncated-text/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/41a6f9778d12dfedcc7ec3727d64a12491d75d9a65d4b9323feb075391ae6795)](https://css-tricks.com/author/chriscoyier/)[Chris Coyier](https://css-tricks.com/author/chriscoyier/)

[absolute position](https://css-tricks.com/tag/absolute-position/) [flexbox](https://css-tricks.com/tag/flexbox/)

**Link** on Mar 18, 2020

### [Flexbox and absolute positioning](https://css-tricks.com/flexbox-and-absolute-positioning/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/41a6f9778d12dfedcc7ec3727d64a12491d75d9a65d4b9323feb075391ae6795)](https://css-tricks.com/author/chriscoyier/)[Chris Coyier](https://css-tricks.com/author/chriscoyier/)

**Article** on Mar 10, 2014

### [Filling the Space in the Last Row with Flexbox](https://css-tricks.com/filling-space-last-row-flexbox/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/41a6f9778d12dfedcc7ec3727d64a12491d75d9a65d4b9323feb075391ae6795)](https://css-tricks.com/author/chriscoyier/)[Chris Coyier](https://css-tricks.com/author/chriscoyier/)

### [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-flexbox-browser-support)Flexbox browser support

CSS Flexbox is supported in all modern browsers.

This browser support data is from [Caniuse](http://caniuse.com/#feat=flexbox), which has more detail. A number indicates that browser supports the feature at that version and up.

#### Desktop

|Chrome|Firefox|IE|Edge|Safari|
|---|---|---|---|---|
|21*|28|11|12|6.1*|

#### Mobile / Tablet

|Android Chrome|Android Firefox|Android|iOS Safari|
|---|---|---|---|
|144|147|4.4|7.0-7.1*|

### [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-related-properties)Related properties

[](https://css-tricks.com/tag/align-content/)[](https://css-tricks.com/tag/flexbox/)

### [](https://css-tricks.com/almanac/properties/a/align-content/)

[](https://css-tricks.com/almanac/properties/a/align-content/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/60e8a54180b64b3c9e409f0dcc5b4b124b292edc71648ec4401a6bb0c6e106b1)](https://css-tricks.com/author/34cross/)[](https://css-tricks.com/author/34cross/)

### [](https://css-tricks.com/almanac/properties/a/align-items/)

[](https://css-tricks.com/almanac/properties/a/align-items/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/60e8a54180b64b3c9e409f0dcc5b4b124b292edc71648ec4401a6bb0c6e106b1)](https://css-tricks.com/author/34cross/)[](https://css-tricks.com/author/34cross/)

### [](https://css-tricks.com/almanac/properties/a/align-self/)

[](https://css-tricks.com/almanac/properties/a/align-self/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/60e8a54180b64b3c9e409f0dcc5b4b124b292edc71648ec4401a6bb0c6e106b1)](https://css-tricks.com/author/34cross/)[](https://css-tricks.com/author/34cross/)

### [](https://css-tricks.com/almanac/properties/g/gap/column-gap/)

[](https://css-tricks.com/almanac/properties/g/gap/column-gap/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/a8e040142716a4b44d014d80fbcf99c635b1d8faabfe469b6954a8ef2f168595)](https://css-tricks.com/author/geoffgraham/)[](https://css-tricks.com/author/geoffgraham/)

[](https://css-tricks.com/tag/display/)

### [](https://css-tricks.com/almanac/properties/d/display/)

[](https://css-tricks.com/almanac/properties/d/display/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/82ba1e1fe4aca49cdcd66ff387fee32e787abbd0ae6d42750be22ea7c89a5102)](https://css-tricks.com/author/saracope/)[](https://css-tricks.com/author/saracope/)

### [](https://css-tricks.com/almanac/properties/g/gap/)

[](https://css-tricks.com/almanac/properties/g/gap/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/4526d37720aa1e3389c64d28339da0ca1cbf4f7e6d47ff155f71a565a4db3093)](https://css-tricks.com/author/seyedi/)[](https://css-tricks.com/author/seyedi/)

### [](https://css-tricks.com/almanac/properties/j/justify-items/)

[](https://css-tricks.com/almanac/properties/j/justify-items/)

[![](https://i0.wp.com/css-tricks.com/wp-content/cache/breeze-extra/gravatars/lJ1-nP6Q_400x400-80x80.jpg?resize=80%2C80&ssl=1)](https://css-tricks.com/author/mohitkhare/)[](https://css-tricks.com/author/mohitkhare/)

### [](https://css-tricks.com/almanac/properties/f/flex/)

[](https://css-tricks.com/almanac/properties/f/flex/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/82ba1e1fe4aca49cdcd66ff387fee32e787abbd0ae6d42750be22ea7c89a5102)](https://css-tricks.com/author/saracope/)[](https://css-tricks.com/author/saracope/)

### [](https://css-tricks.com/almanac/properties/f/flex-basis/)

[](https://css-tricks.com/almanac/properties/f/flex-basis/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/60e8a54180b64b3c9e409f0dcc5b4b124b292edc71648ec4401a6bb0c6e106b1)](https://css-tricks.com/author/34cross/)[](https://css-tricks.com/author/34cross/)

### [](https://css-tricks.com/almanac/properties/f/flex-direction/)

[](https://css-tricks.com/almanac/properties/f/flex-direction/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/avatar)](https://css-tricks.com/author/)[](https://css-tricks.com/author/)

### [](https://css-tricks.com/almanac/properties/f/flex-flow/)

[](https://css-tricks.com/almanac/properties/f/flex-flow/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/avatar)](https://css-tricks.com/author/)[](https://css-tricks.com/author/)

[](https://css-tricks.com/tag/flex-grow/)[](https://css-tricks.com/tag/flexbox/)

### [](https://css-tricks.com/almanac/properties/f/flex-grow/)

[](https://css-tricks.com/almanac/properties/f/flex-grow/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/41a6f9778d12dfedcc7ec3727d64a12491d75d9a65d4b9323feb075391ae6795)](https://css-tricks.com/author/chriscoyier/)[](https://css-tricks.com/author/chriscoyier/)

### [](https://css-tricks.com/almanac/properties/f/flex-shrink/)

[](https://css-tricks.com/almanac/properties/f/flex-shrink/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/avatar)](https://css-tricks.com/author/)[](https://css-tricks.com/author/)

### [](https://css-tricks.com/almanac/properties/f/flex-wrap/)

[](https://css-tricks.com/almanac/properties/f/flex-wrap/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/41a6f9778d12dfedcc7ec3727d64a12491d75d9a65d4b9323feb075391ae6795)](https://css-tricks.com/author/chriscoyier/)[](https://css-tricks.com/author/chriscoyier/)

### [](https://css-tricks.com/almanac/properties/j/justify-content/)

[](https://css-tricks.com/almanac/properties/j/justify-content/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/60e8a54180b64b3c9e409f0dcc5b4b124b292edc71648ec4401a6bb0c6e106b1)](https://css-tricks.com/author/34cross/)[](https://css-tricks.com/author/34cross/)

### [](https://css-tricks.com/almanac/properties/j/justify-self/)

[](https://css-tricks.com/almanac/properties/j/justify-self/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/a8e040142716a4b44d014d80fbcf99c635b1d8faabfe469b6954a8ef2f168595)](https://css-tricks.com/author/geoffgraham/)[](https://css-tricks.com/author/geoffgraham/)

### [](https://css-tricks.com/almanac/properties/g/gap/row-gap/)

[](https://css-tricks.com/almanac/properties/g/gap/row-gap/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/a8e040142716a4b44d014d80fbcf99c635b1d8faabfe469b6954a8ef2f168595)](https://css-tricks.com/author/geoffgraham/)[](https://css-tricks.com/author/geoffgraham/)

### [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-more-flexbox-information)More Flexbox information

- [](https://www.w3.org/TR/css-flexbox-1/)
- [](https://www.digitalocean.com/community/cheatsheets/css-flexbox?utm_medium=content_acq&utm_source=css-tricks&utm_campaign=&utm_content=awareness_bestsellers)
- [](https://www.digitalocean.com/community/tutorials/css-centering-using-flexbox?utm_medium=content_acq&utm_source=css-tricks&utm_campaign=&utm_content=awareness_bestsellers)

### [](https://css-tricks.com/solved-flexbox/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/41a6f9778d12dfedcc7ec3727d64a12491d75d9a65d4b9323feb075391ae6795)](https://css-tricks.com/author/chriscoyier/)[](https://css-tricks.com/author/chriscoyier/)

### [](https://css-tricks.com/flexbox-cheat-sheet/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/41a6f9778d12dfedcc7ec3727d64a12491d75d9a65d4b9323feb075391ae6795)](https://css-tricks.com/author/chriscoyier/)[](https://css-tricks.com/author/chriscoyier/)

### [](https://css-tricks.com/dive-into-flexbox/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/41a6f9778d12dfedcc7ec3727d64a12491d75d9a65d4b9323feb075391ae6795)](https://css-tricks.com/author/chriscoyier/)[](https://css-tricks.com/author/chriscoyier/)

[](https://css-tricks.com/tag/flexbox/)[](https://css-tricks.com/tag/grid/)[](https://css-tricks.com/tag/layout/)

### [](https://css-tricks.com/use-cases-for-flexbox/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/41a6f9778d12dfedcc7ec3727d64a12491d75d9a65d4b9323feb075391ae6795)](https://css-tricks.com/author/chriscoyier/)[](https://css-tricks.com/author/chriscoyier/)

[](https://css-tricks.com/tag/flexbox/)[](https://css-tricks.com/tag/grid/)[](https://css-tricks.com/tag/layout/)

### [](https://css-tricks.com/quick-whats-the-difference-between-flexbox-and-grid/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/41a6f9778d12dfedcc7ec3727d64a12491d75d9a65d4b9323feb075391ae6795)](https://css-tricks.com/author/chriscoyier/)[](https://css-tricks.com/author/chriscoyier/)

[](https://css-tricks.com/tag/flexbox/)[](https://css-tricks.com/tag/grid/)

### [](https://css-tricks.com/css-grid-replace-flexbox/)

[![](https://i0.wp.com/css-tricks.com/wp-content/cache/breeze-extra/gravatars/me-black-white-80x80.jpg?resize=80%2C80&ssl=1)](https://css-tricks.com/author/robinrendle/)[](https://css-tricks.com/author/robinrendle/)

[](https://css-tricks.com/tag/flexbox/)[](https://css-tricks.com/tag/grid/)

### [](https://css-tricks.com/grid-for-layout-flexbox-for-components/)

[![](https://i0.wp.com/css-tricks.com/wp-content/cache/breeze-extra/gravatars/me-black-white-80x80.jpg?resize=80%2C80&ssl=1)](https://css-tricks.com/author/robinrendle/)[](https://css-tricks.com/author/robinrendle/)

[](https://css-tricks.com/tag/flexbox/)[](https://css-tricks.com/tag/grid/)

### [](https://css-tricks.com/use-grid-flexbox/)

[![](https://i0.wp.com/css-tricks.com/wp-content/cache/breeze-extra/gravatars/me-black-white-80x80.jpg?resize=80%2C80&ssl=1)](https://css-tricks.com/author/robinrendle/)[](https://css-tricks.com/author/robinrendle/)

### [](https://css-tricks.com/dont-overthink-flexbox-grids/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/41a6f9778d12dfedcc7ec3727d64a12491d75d9a65d4b9323feb075391ae6795)](https://css-tricks.com/author/chriscoyier/)[](https://css-tricks.com/author/chriscoyier/)

[](https://css-tricks.com/tag/logical-properties/)[](https://css-tricks.com/tag/writing-mode/)

### [](https://css-tricks.com/building-multi-directional-layouts/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/04af99c422a2af830c5912efeef0ba0ddbc8af26372158f1598839e6fb31f1eb)](https://css-tricks.com/author/ahmadalfy/)[](https://css-tricks.com/author/ahmadalfy/)

[](https://css-tricks.com/tag/flexbox/)[](https://css-tricks.com/tag/margin/)

### [](https://css-tricks.com/how-auto-margins-work-in-flexbox/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/41a6f9778d12dfedcc7ec3727d64a12491d75d9a65d4b9323feb075391ae6795)](https://css-tricks.com/author/chriscoyier/)[](https://css-tricks.com/author/chriscoyier/)

[](https://css-tricks.com/tag/flexbox/)

### [](https://css-tricks.com/flex-grow-is-weird/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/de3be7ba94c6a1bf0e69c7c0af6de3e54b8bcc53e716f54c972e080745128dac)](https://css-tricks.com/author/mmatuzo/)[](https://css-tricks.com/author/mmatuzo/)

[](https://css-tricks.com/tag/flex-basis/)[](https://css-tricks.com/tag/flex-grow/)[](https://css-tricks.com/tag/flex-shrink/)[](https://css-tricks.com/tag/flexbox/)

### [](https://css-tricks.com/understanding-flex-grow-flex-shrink-and-flex-basis/)

[![](https://i0.wp.com/css-tricks.com/wp-content/cache/breeze-extra/gravatars/me-black-white-80x80.jpg?resize=80%2C80&ssl=1)](https://css-tricks.com/author/robinrendle/)[](https://css-tricks.com/author/robinrendle/)

[](https://css-tricks.com/tag/flexbox/)[](https://css-tricks.com/tag/grid/)[](https://css-tricks.com/tag/internet-explorer/)

### [](https://css-tricks.com/ie10-compatible-grid-auto-placement-with-flexbox/)

[![](https://i0.wp.com/css-tricks.com/wp-content/cache/breeze-extra/gravatars/profile-pic-80x80.png?resize=80%2C80&ssl=1)](https://css-tricks.com/author/bholt/)[](https://css-tricks.com/author/bholt/)

### [](https://css-tricks.com/old-flexbox-and-new-flexbox/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/41a6f9778d12dfedcc7ec3727d64a12491d75d9a65d4b9323feb075391ae6795)](https://css-tricks.com/author/chriscoyier/)[](https://css-tricks.com/author/chriscoyier/)

### [](https://css-tricks.com/using-flexbox/)

[![](https://css-tricks.com/wp-content/cache/breeze-extra/gravatars/41a6f9778d12dfedcc7ec3727d64a12491d75d9a65d4b9323feb075391ae6795)](https://css-tricks.com/author/chriscoyier/)[](https://css-tricks.com/author/chriscoyier/)

### [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-more-flexbox-sources)More Flexbox sources

- [](https://www.w3.org/TR/css-flexbox-1/)
- [](https://www.digitalocean.com/community/cheatsheets/css-flexbox?utm_medium=content_acq&utm_source=css-tricks&utm_campaign=&utm_content=awareness_bestsellers)
- [](https://www.digitalocean.com/community/tutorials/css-centering-using-flexbox?utm_medium=content_acq&utm_source=css-tricks&utm_campaign=&utm_content=awareness_bestsellers)
- [](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox)
- [](https://www.smashingmagazine.com/2018/10/flexbox-use-cases/)

_Psst!_ Create a DigitalOcean account and get[$200 in free credit](https://try.digitalocean.com/css-tricks/?utm_medium=content_acq&utm_source=css-tricks&utm_campaign=global_brand_ad_en&utm_content=conversion_postarticle_psst)for cloud-based hosting and services.

## Comments

Toggle All Comments (there are a lot)

1. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-355721)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-355721)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1583860)
        
        [](http://i.snag.gy/VHJsV.jpg)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1583911)
        
        [](http://inuitcss.com/)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1583984)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1584193)
        
        [](http://tympanus.net/codrops/2013/02/04/creating-nestable-dynamic-grids/)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1584693)
        
        [](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1593663)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1595680)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1596379)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1596460)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1597674)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1597676)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1599014)
        
        [](https://codepen.io/anon/pen/WrOqma)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1600535)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1601177)
        
          
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1601458)
        
          
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1604008)
        
          
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1604516)
        
2. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-369174)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-369174)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1580694)
        
          
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1581202)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1581248)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1581351)
        
3. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-371025)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-371025)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1584164)
        
        [](https://css-tricks.com/using-flexbox/)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1586177)
        
4. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-386137)
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-386137)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-386512)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-386636)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1611735)
        
          
        
          
          
          
          
          
          
        
5. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-386708)
    
      
      
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-386708)
    
6. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-462689)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-462689)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-462767)
        
7. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-469844)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-469844)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1534807)
        
        [](http://sassmeister.com/gist/9781525)
        
8. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-472802)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-472802)
    
9. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-481799)
    
    [](https://gist.github.com/joseph-turner/5674311)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-481799)
    
10. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-482563)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-482563)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1580654)
        
11. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-483992)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-483992)
    
12. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-484404)
    
    [](http://codepen.io/HugoGiraudel/pen/LklCv)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-484404)
    
13. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-492482)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-492482)
    
14. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-513504)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-513504)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1147834)
        
15. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-515572)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-515572)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-515667)
        
        [](https://raw.github.com/timhettler/compass-flexbox/master/extensions/compass-flexbox/stylesheets/_flexbox.scss)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1167480)
        
          
          
          
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1581189)
        
        [](http://edensg.github.io/ASM2O/)
        
16. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-522306)
    
    >   
    >   
    >   
    >   
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-522306)
    
17. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-537354)
    
    [](http://codepen.io/anon/pen/pEIKu)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-537354)
    
18. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-545403)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-545403)
    
19. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-547626)
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-547626)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-553241)
        
        [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-537354)
        
20. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-553173)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-553173)
    
21. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-555673)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-555673)
    
22. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-589576)
    
    [](http://cdpn.io/qliuj)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-589576)
    
23. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-602941)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-602941)
    
24. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-610855)
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-610855)
    
25. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-684015)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-684015)
    
26. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-720205)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-720205)
    
27. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-787564)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-787564)
    
28. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-820238)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-820238)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1419165)
        
29. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-888068)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-888068)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1118034)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1147844)
        
30. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1058927)
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1058927)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1147843)
        
        [](https://css-tricks.com/old-flexbox-and-new-flexbox/)
        
31. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1076695)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1076695)
    
32. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1105793)
    
    [](http://cdpn.io/Ihven "Flexbox Alignment Sample")
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1105793)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1373093)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1377306)
        
33. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1134249)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1134249)
    
34. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1147288)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1147288)
    
35. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1149183)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1149183)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1155088)
        
        [](https://css-tricks.com/tricky-textarea-pulltab/)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1155128)
        
36. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1177754)
    
      
      
    
      
    [](http://codepen.io/Gimm/full/KAcnu "wrong main size when flex-driection is column")
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1177754)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1210562)
        
          
        
37. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1217009)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1217009)
    
38. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1288358)
    
      
      
      
      
      
    
      
      
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1288358)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1540857)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1585727)
        
39. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1297628)
    
      
    [](http://msdn.microsoft.com/en-us/library/ie/dn265027\(v=vs.85\).aspx)  
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1297628)
    
40. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1302274)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1302274)
    
41. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1399417)
    
    [](http://noseyparka.me.uk/2014/03/26/a-holy-grail-flexbox-layout/)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1399417)
    
42. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1540782)
    
    [](http://flexiejs.com/)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1540782)
    
43. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1540912)
    
      
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1540912)
    
44. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1542587)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1542587)
    
45. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1544695)
    
    `                  `
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1544695)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1563853)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1586699)
        
46. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1553572)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1553572)
    
47. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1565076)
    
    [](http://codepen.io/HugoGiraudel/pen/qIAwr)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1565076)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1580251)
        
48. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1579845)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1579845)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1579961)
        
49. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1580070)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1580070)
    
50. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1580110)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1580110)
    
51. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1580400)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1580400)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1601412)
        
52. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1580647)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1580647)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1580648)
        
53. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1580733)
    
      
      
      
      
      
      
      
      
    [](http://cdpn.io/rhbmd "codepen link")
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1580733)
    
54. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1581039)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1581039)
    
55. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1581112)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1581112)
    
56. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1581192)
    
      
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1581192)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1593127)
        
57. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1581200)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1581200)
    
58. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1581203)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1581203)
    
59. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1581237)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1581237)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1581238)
        
60. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1581239)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1581239)
    
61. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1581506)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1581506)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1581647)
        
62. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1581808)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1581808)
    
63. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1582067)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1582067)
    
64. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1582831)
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1582831)
    
65. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1583051)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1583051)
    
66. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1583145)
    
      
    
    [](http://beta.caniuse.com/#search=flexbox)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1583145)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1583146)
        
67. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1583726)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1583726)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1583727)
        
68. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1583833)
    
      
    [](http://codepen.io/coxthefox/pen/jtseL)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1583833)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1583835)
        
          
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1584085)
        
69. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1583839)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1583839)
    
70. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1583853)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1583853)
    
71. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1583992)
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1583992)
    
72. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1584052)
    
      
      
    
      
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1584052)
    
73. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1584057)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1584057)
    
74. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1584116)
    
      
      
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1584116)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1584117)
        
75. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1584118)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1584118)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1584120)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1584124)
        
        [](https://www.dropbox.com/s/y8wccmz7hzmkpdb/Zrzut%20ekranu%20z%202014-07-29%2011%3A57%3A31.png)
        
76. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1584162)
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1584162)
    
77. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1584335)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1584335)
    
78. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1584475)
    
      
    [](https://github.com/annebosman/FlexboxLess "github flexboxless")
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1584475)
    
79. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1584625)
    
    [](https://github.com/Modernizr/Modernizr/issues/1414)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1584625)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1585121)
        
        [](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Flexible_boxes)  
          
          
        
80. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1584974)
    
      
      
    
    [](https://imageshack.com/i/exCE1dbBj "Blocks")
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1584974)
    
81. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1585525)
    
    [](http://codepen.io/dalgard/pen/Dbnus)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1585525)
    
82. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1585637)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1585637)
    
83. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1585805)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1585805)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1585808)
        
84. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1585814)
    
      
    [](http://ionlyseespots.github.io/ambient-design/index.html)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1585814)
    
85. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1585885)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1585885)
    
86. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1586033)
    
    [](http://jakearchibald.com/2014/dont-use-flexbox-for-page-layout/ "dont' use flexbox for overall layout")
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1586033)
    
87. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1586127)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1586127)
    
88. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1586164)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1586164)
    
89. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1586378)
    
      
    [](http://www.w3.org/TR/css-flexbox-1/#propdef-flex-basis)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1586378)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1586406)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1586409)
        
          
        [](https://developer.mozilla.org/en-US/docs/CSS/flex-basis)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1586417)
        
90. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1586415)
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1586415)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1593128)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1666526)
        
91. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1586427)
    
    [](https://bugzilla.mozilla.org/show_bug.cgi?id=1082780)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1586427)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1587307)
        
92. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1586725)
    
      
    [](https://github.com/philipperutten/css3-box)[](http://bower.io/search/?q=css3%20less%20layout)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1586725)
    
93. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1586830)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1586830)
    
94. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1586838)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1586838)
    
95. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1587040)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1587040)
    
96. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1587256)
    
    [](http://www.sketchingwithcss.com/flexbox/ "Sketching with Flexbox")[](http://www.sketchingwithcss.com/flexbox-tutorial/ "Flexbox Tutorial")
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1587256)
    
97. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1587433)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1587433)
    
98. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1587475)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1587475)
    
99. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1588592)
    
    [](http://apps.workflower.fi/css-cheats/?name=flexbox)[](https://github.com/sakamies/css-cheats)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1588592)
    
100. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1591486)
    
      
    [](http://hictech.github.io/cssPlusWebsite/)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1591486)
    
101. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1592030)
    
    [](http://codepen.io/HugoGiraudel/pen/LklCv)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1592030)
    
102. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1592127)
    
      
    
      
      
      
    
      
      
      
      
      
      
      
      
      
      
    
      
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1592127)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1592128)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1593129)
        
        [](https://github.com/postcss/autoprefixer)
        
103. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1592370)
    
    [](http://codepen.io/anon/pen/dPVEJd)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1592370)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1592559)
        
        [](http://codepen.io/ionlyseespots/pen/pvaPwq)
        
104. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1592560)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1592560)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1592589)
        
105. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1592765)
    
    [](http://www.datagnosis.com/test_layout.html)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1592765)
    
106. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1592834)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1592834)
    
107. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1593131)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1593131)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1599019)
        
108. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1593300)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1593300)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1593303)
        
109. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1593327)
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1593327)
    
110. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1593341)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1593341)
    
111. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1593460)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1593460)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1593904)
        
112. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1593464)
    
      
    [](http://www.w3.org/TR/css3-flexbox/images/rel-vs-abs-flex.svg)[](http://www.w3.org/TR/css3-flexbox/#flex-property)  
    [](http://www.w3.org/TR/css3-flexbox/#flex-basis-property)
    
      
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1593464)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1593959)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1597325)
        
113. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1593652)
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1593652)
    
114. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1593743)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1593743)
    
115. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1593958)
    
    [](http://codepen.io/trilm/pen/aOoGVz)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1593958)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1596426)
        
        [](http://codepen.io/AndyMaleh/pen/RPmwdz/)[](http://codepen.io/AndyMaleh)[](http://codepen.io/)
        
116. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1594069)
    
      
      
    [](https://jsfiddle.net/Serk0413/y6ugdxgx/10/embedded/result/)  
    [](https://jsfiddle.net/Serk0413/y6ugdxgx/)  
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1594069)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1597518)
        
117. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1594162)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1594162)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1594757)
        
          
        
118. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1594297)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1594297)
    
119. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1594306)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1594306)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1594316)
        
          
        
        [](http://codepen.io/colnago/pen/LVpoGK)
        
120. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1594900)
    
    [](http://codepen.io/mdix/pen/pJNrmM)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1594900)
    
121. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1595210)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1595210)
    
122. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1595251)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1595251)
    
123. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1595264)
    
    [](https://www.ukietech.com/blog/programming/custom-flexbox-grid-using-bootstrap-mixins-sass/)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1595264)
    
124. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1595755)
    
      
    [](https://jsfiddle.net/h0Lww6mk/3/)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1595755)
    
125. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1596093)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1596093)
    
126. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1596118)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1596118)
    
127. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1596444)
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1596444)
    
128. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1596656)
    
      
      
    [](http://stackoverflow.com/q/32229436/2396907)  
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1596656)
    
129. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1596919)
    
    [](http://codepen.io/seasalt/pen/GppzmG)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1596919)
    
130. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1596966)
    
    [](http://stackoverflow.com/questions/32572347/left-aligned-and-centered-grid-with-flexbox)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1596966)
    
131. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1597164)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1597164)
    
132. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1597276)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1597276)
    
133. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1597324)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1597324)
    
134. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1597327)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1597327)
    
135. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1597360)
    
    [](http://codepen.io/anon/pen/VvbzbP?editors=110)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1597360)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1597361)
        
136. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1597479)
    
    [](http://bennettfeely.com/flexplorer/)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1597479)
    
137. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1597867)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1597867)
    
138. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1598893)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1598893)
    
139. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1598894)
    
      
      
      
      
      
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1598894)
    
140. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1598895)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1598895)
    
141. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1598920)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1598920)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1598921)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1598924)
        
        [](http://www.quirksmode.org/blog/archives/2015/07/stop_pushing_th.html)
        
        [](https://dev.opera.com/articles/on-a-moratorium-on-new-browser-features/)
        
142. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1599016)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)  
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1599016)
    
143. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1599037)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1599037)
    
144. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1599150)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1599150)
    
145. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1599416)
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1599416)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1599421)
        
        [](http://stackoverflow.com/)
        
        [](http://lorempixel.com/)
        
146. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1599420)
    
      
    [](http://caniuse.com/#feat=flexbox)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1599420)
    
147. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1599550)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1599550)
    
148. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1599657)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1599657)
    
149. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1599659)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1599659)
    
150. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1599835)
    
      
    [](http://codepen.io/anon/pen/BjXbrw)  
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1599835)
    
151. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1599998)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1599998)
    
152. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1600440)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1600440)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1600512)
        
153. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1600496)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1600496)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1600497)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1601337)
        
154. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1600830)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1600830)
    
155. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1601178)
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1601178)
    
156. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1601197)
    
      
      
      
    [](http://codepen.io/simspace-dev/pen/mPGQdq)  
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1601197)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1601201)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1603732)
        
          
        
157. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1601784)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1601784)
    
158. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1602168)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1602168)
    
159. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1602288)
    
      
      
    
    [](https://jsbin.com/kobefo/1)  
    [](https://bugzilla.mozilla.org/show_bug.cgi?id=984869)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1602288)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1602289)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1602639)
        
        [](http://caniuse.com/)
        
          
        
160. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1603061)
    
    >   
    > [](http://i.snag.gy/VHJsV.jpg)
    
    [](https://plnkr.co/edit/yKLl8irs6xudPHfTh1u9)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1603061)
    
161. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1603320)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1603320)
    
162. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1603623)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1603623)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1603790)
        
163. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1603730)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1603730)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1603896)
        
164. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1603945)
    
      
      
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1603945)
    
165. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1604380)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1604380)
    
166. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1604493)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1604493)
    
167. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1604551)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1604551)
    
168. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1604638)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1604638)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1605759)
        
          
        
169. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1604719)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1604719)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1604720)
        
170. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1604884)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1604884)
    
171. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1604930)
    
      
      
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1604930)
    
172. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1604988)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1604988)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1605621)
        
173. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1604993)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1604993)
    
174. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1605021)
    
    [](http://codepen.io/localnepal/pen/vyXPmy)  
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1605021)
    
175. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1605388)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1605388)
    
176. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1605464)
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1605464)
    
177. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1605893)
    
      
      
      
      
      
      
    
    [](http://codepen.io/bplaced/pen/RKbXJX/)[](http://codepen.io/bplaced)[](http://codepen.io/)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1605893)
    
178. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1605945)
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1605945)
    
179. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1606319)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1606319)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1607787)
        
180. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1606676)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1606676)
    
181. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1606791)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1606791)
    
182. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1607008)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1607008)
    
183. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1608957)
    
    [](https://codepen.io/vlrprbttst/pen/gRYVMO)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1608957)
    
184. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1610583)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1610583)
    
185. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1610672)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1610672)
    
186. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1610737)
    
    [](https://github.com/mobilejazz/Eixample)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1610737)
    
187. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1611705)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1611705)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1612410)
        
188. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1612797)
    
    [](https://codepen.io/seiryoku/pen/pdjYKY)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1612797)
    
189. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1613588)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1613588)
    
190. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1613650)
    
      
      
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1613650)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1614012)
        
          
        [](https://www.w3.org/TR/css-flexbox-1/#flex-containers)
        
        [](https://github.com/w3c/csswg-drafts/issues)
        
191. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1613870)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1613870)
    
192. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1613970)
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1613970)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1613977)
        
        > [](https://css-tricks.com/license/)
        
193. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1613975)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1613975)
    
194. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1616147)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1616147)
    
195. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1616515)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1616515)
    
196. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1617597)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1617597)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1617699)
        
        [](https://css-tricks.com/flex-grow-is-weird/)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1668242)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1684018)
        
197. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1618216)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1618216)
    
198. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1621986)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1621986)
    
199. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1632652)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1632652)
    
200. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1632685)
    
    [](https://codepen.io/ZaLiTHkA/pen/VxxZER)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1632685)
    
201. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1636179)
    
    [](https://stackoverflow.com/questions/34928565/properly-sizing-and-aligning-the-flex-items-on-the-last-row?noredirect=1)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1636179)
    
202. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1636207)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1636207)
    
203. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1638816)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1638816)
    
204. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1638883)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1638883)
    
205. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1639534)
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1639534)
    
206. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1652522)
    
      
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1652522)
    
207. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1652600)
    
    [](https://developer.mozilla.org/en-US/docs/Web/CSS/place-content)[](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1652600)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1652601)
        
208. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1652685)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1652685)
    
209. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1652884)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1652884)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1652889)
        
210. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1652890)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1652890)
    
211. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1653668)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1653668)
    
212. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1660539)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1660539)
    
213. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1670844)
    
    [](https://poonia.github.io/flexbox/)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1670844)
    
214. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1672122)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1672122)
    
215. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1672708)
    
    [](https://codepen.io/geoffgraham/pen/WmRXaz)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1672708)
    
216. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1672713)
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1672713)
    
217. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1676106)
    
    [](https://github.com/w3c/csswg-drafts/issues/1696)  
    [](https://developer.mozilla.org/en-US/docs/Web/CSS/gap)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1676106)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1755677)
        
218. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1687094)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1687094)
    
219. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1695468)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1695468)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1695648)
        
        [](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-items)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1700035)
        
220. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1700207)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1700207)
    
221. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1711763)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1711763)
    
222. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1718343)
    
      
      
      
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1718343)
    
223. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1751706)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1751706)
    
224. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1752242)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1752242)
    
225. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1752942)
    
    [](https://app.peterrcook.com/flexplorer/)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1752942)
    
226. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1753479)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1753479)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1761872)
        
          
        
227. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1753502)
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1753502)
    
228. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1755667)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1755667)
    
229. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1756880)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1756880)
    
230. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1757915)
    
      
      
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1757915)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1765961)
        
231. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1762427)
    
      
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1762427)
    
232. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1764581)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1764581)
    
233. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1765639)
    
      
    [](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-self)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1765639)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1767021)
        
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1767521)
        
        [](https://stackoverflow.com/questions/32551291/in-css-flexbox-why-are-there-no-justify-items-and-justify-self-properties#33856609)
        
234. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1768794)
    
    [](https://www.dropbox.com/s/xdeltebgmzz23wy/flexbox-question.jpg?dl=0)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1768794)
    
235. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1773347)
    
      
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1773347)
    
236. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1781610)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#justify-content)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1781610)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1781657)
        
          
          
        
          
          
        
        [](https://codepen.io/chriscoyier/pen/OJgVRPL)
        
237. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1785341)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1785341)
    
238. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1794872)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1794872)
    
239. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1795137)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1795137)
    
240. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1795773)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1795773)
    
241. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1797230)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1797230)
    
242. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1797796)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1797796)
    
243. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1797843)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1797843)
    
244. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1797852)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1797852)
    
245. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1797970)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1797970)
    
246. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1802926)
    
    [](https://chromestatus.com/feature/5093352798683136)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1802926)
    
247. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1808144)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1808144)
    
248. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1808146)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1808146)
    
249. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1854816)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1854816)
    
    - [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1854953)
        
250. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1872033)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1872033)
    
251. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1873597)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1873597)
    
252. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1874924)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1874924)
    
253. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1875022)
    
      
      
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1875022)
    
254. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1877316)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1877316)
    
255. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1879485)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1879485)
    
256. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1880432)
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1880432)
    
257. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1880723)
    
    [](https://developer.mozilla.org/en-US/docs/Web/CSS/place-items)  
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1880723)
    
258. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1880767)
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1880767)
    
259. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1880791)
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1880791)
    
260. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1880998)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1880998)
    
261. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1881305)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1881305)
    
262. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1881325)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1881325)
    
263. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1881731)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1881731)
    
264. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1881943)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1881943)
    
265. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1881983)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1881983)
    
266. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1882568)
    
      
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1882568)
    
267. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1882719)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1882719)
    
268. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1882860)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1882860)
    
269. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1882978)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1882978)
    
270. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1883209)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1883209)
    
271. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1883326)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1883326)
    
272. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1883487)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1883487)
    
273. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1883624)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1883624)
    
274. [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1883724)
    
    [](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#comment-1883724)
    

### Leave a Reply

Comment 

Name

Email

Website

Save my name, email, and website in this browser for the next time I comment.

CSS-Tricks is powered by [DigitalOcean](https://www.digitalocean.com/?utm_source=css-tricks.com&utm_medium=cta&utm_campaign=website_link).

#### Keep up to date on web dev

with our hand-crafted newsletter

*

Email Address:

Subscribe

##### DigitalOcean

- [About DO](https://www.digitalocean.com/about?utm_source=css-tricks.com&utm_medium=cta&utm_campaign=website_link)
- [Cloudways](https://www.cloudways.com/en/wordpress-hosting.php?id=1223312)
- [Legal stuff](https://www.digitalocean.com/legal?utm_source=css-tricks.com&utm_medium=cta&utm_campaign=website_link)
- [Get free credit!](https://try.digitalocean.com/css-tricks/?utm_source=wordpress-1242695-4567563.cloudwaysapps.com&utm_medium=cta&utm_campaign=website_link)

##### CSS-Tricks

- [Contact](https://css-tricks.com/contact/)
- [Write for CSS-Tricks!](https://css-tricks.com/guest-writing/)
- [Advertise with us](https://css-tricks.com/advertising/)

##### Social

- [RSS Feeds](https://css-tricks.com/rss-feeds/)
- [CodePen](https://codepen.io/team/css-tricks)
- [Mastodon](https://mastodon.social/@csstricks)
- [Bluesky](https://bsky.app/profile/css-tricks.com)

[](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#top-of-site)

![](https://consent.trustarc.com/get?name=css-tricks.com_cookie-notice.png)

[](https://jetpack.com/upgrade/search/?utm_source=poweredby)