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

[INSERTAR CAP CON LA PAGINA TERMINADA]