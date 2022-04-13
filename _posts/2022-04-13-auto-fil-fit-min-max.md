---
title: "auto fill,fit and min, max"
categories:
  - CSS
tags:
  - coding
  - css
  - grid
---

# Auto

### grid-auto-rows, grid-auto-flow, grid-auto-columns

**these are work in repeat() function. and GOOD to make 'responsive website'**

- `grid-auto-rows`: values

  - If a grid item is positioned into a row that is not explicitly sized by grid-template-rows, implicit grid tracks are created to hold it.
  - values
    - keyword, lenght, percentage, minmax, flex...

- `grid-auto-flow`: direction
- `grid-auto-columns` use when `grid-auto-flow: column;` and work in the same way as `grid-auto-rows`

## auto-fit and auto-fill

- `auto-fit` : when the screen is bigger fit the blank space by stretch the element.
- `auto-fill` : when the screen is bigger fill the blank space by make empty columns.

# minmax

The minmax() CSS function defines a size range greater than or equal to min and less than or equal to max. It is used with CSS Grids.

# min-content, max-content

- `min-content` : Reduce the size of the cell by reducing the size of the content as much as possible.
- `max-content` : Increase the size of the cell by the size of the content.

Combining with `repeat()`, `auto-fit`,`auto-fill` and `minmax()` make us not care about size.
More responsive!
