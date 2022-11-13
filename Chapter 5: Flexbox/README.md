# Chapter 5: Flexbox

Flexbox introduces 12 new properties

## 5.1 Flexbox Principles

Applying `display: flex` to an element turns it into a *flex container*, and its direct children into *flex items*.

They align one next to each other in the same row by default.

Flex container fills the available width like a block element, but the flex items may not necessarily fill the width of their flex container.

**Tip:** `display: inline-flex` This creates a flex container that behaves more like an `inline-block` rather than a `block`. It flows inline with other inline elements, but it won't automatically grow to 100% width.
Flex items within it generally behave the same as with `display: flex`. Practically speaking you won't need to use this very often.

![Figure 5.1 A flexbox container and its elements](/Chapter%205%3A%20Flexbox/assets/figure-5.1.png)

A flex container asserts control over the layout of the elements within.

### Flexbox Axis

The items are placed along a line called **main axis**, which goes from the **main-start** (left) the **main-end** (right). Perpendicular to the **cross axis**. This goes from the **cross-start** (top) to the **cross-end** (bottom).


We will build the page shown below:

![Figure 5.2 Finished page with a flexbox layout](/Chapter%205%3A%20Flexbox/assets/figure-5.2.png)

#### Base styles for the page

First, we create a **global box-sizing fix** (chapter 3):

```css
/* :root pseudo-selector is the same as the html tag selector but with more specificity. */
:root {
    box-sizing: border-box;
}

*,
::before,
::after {
    box-sizing: inherit;
}
```

Second, we **set green background color and sans-serif font for the page**:

```css
body {
    background-color: #709b90;
    font-family: Helvetica, Arial, sans-serif;
}
```

Then, **global margins** (chapter 3):

```css
body * + * {
    margin-top: 1.5em;
}
```

And finally, we add  **double-container to center page contents** (chapter 4):

```css
.container {
    max-width: 1080px;
    margin: 0 auto;
}
```

### 5.1.1 Building a basic flexbox menu

For this example, you'll want the navigation menu to look like the figure below:

![Figure 5.3 Navigational menu with items laid out using flexbox](/Chapter%205%3A%20Flexbox/assets/figure-5.3.png)

In case of our page menu, the flex container should be the unordered list `<ul>`. Its children, the list items `<li>`, will be the flex items.

First. you'll apply `display: flex` to the list. You'll also need to override the default list styles from the user agent stylesheet and the lobotomized owl top margins. You'll also apply the colors.

In the markup, you've given the `<ul>`a `site-nav` class, which you can then use to target it in the styles.

#### Applying flexbox and colors to the menu

Makes site-nav the flex container and its children the flex items. Removes the left padding and list bullets in the user agents styles:

```css
.site-nav {
    display: flex;
    padding-left: 0;
    list-style-type: none;
    background-color: #5f4b44;
}
```

Overrides the lobotomized owl top margin:

```css
.site-nav > li {
    margin-top: 0;
}
```

Removes the underline link from link text in the user agent styles:

```css 
.site-nav > li > a {
    background-color: #cc6b5a;
    color: white;
    text-decoration: none;
}
```
