---
title: "A few ways to make grid"
categories:
  - CSS
tags:
  - coding
  - css
  - grid
---

# GRID

Like **flex box**, make **grid** in <father>.

```css
.grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: 0.7fr 0.3fr;
  gap: 5px;
  /*
  row-gap: 5px;
  column-gpa: 5px;
  */
}
```

## Using `grid-area`

There is two ways

- `grid-area`
  - defining all four lines
  - giving it a name and then specify the location with `grid-template-areas`

### defining all four lines

```css
.content {
  grid-area: 1 / 1 / 4 / 2;
}
```

Counting line start with 1, It's counterclockwise starting from the top.

### giving it a name and then specify the location with `grid-template-areas`

giving name like this

```css
.header {
  grid-area: hd;
}
```

this name should without quotes and dont confuse with **classname**.

and specify the location

```css
.wrapper {
  display: grid;
  grid-template-columns: repeat(9, 1fr);
  grid-auto-rows: minmax(100px, auto);
  grid-template-areas:
    "hd hd hd hd   hd   hd   hd   hd   hd"
    "sd sd sd main main main main main main"
    "ft ft ft ft   ft   ft   ft   ft   ft";
}
```

#### auto

using `auto` make the boxes as big as possible.

In this case if there 4 columns.
`grid-template-columns: auto 200px;`
auto 200px auto auto
second block have 200px and the other have same space.

## Using `grid-column` and `grid-row`

```css
.content {
  grid-column: 1 / -1;
  grid-row: 2 / span 2;
}
```

This property is shortcut.
And counting line start with 1.
`grid-column: 1 / -1;` == `grid-column-start: 1; grid-column-end: -1;` this code easy to specify from beginning to end.

Using negative number keep me from counting one by one.

### span in `grid-row: 2 / span 2;`

this span mean cell.

## Using line naming

You can assign some or all of the lines in your grid a name when you define your grid with the `grid-template-rows` and `grid-template-columns` properties. like this

```css
.wrapper {
  display: grid;
  grid-template-columns: [main-start] 1fr [content-start] 1fr [content-end] 1fr [main-end];
  grid-template-rows: [main-start] 100px [content-start] 100px [content-end] 100px [main-end];
}
```

and use the name like this

```css
.box1 {
  grid-column-start: main-start;
  grid-row-start: main-start;
  grid-row-end: main-end;
}
```

## `grid-template`

`grid-template` is a **shortcut to define all this**: - `grid-template-areas` - `grid-template-columns` - `grid-template-rows`

```css
.grid {
  display: grid;
  grid-template:
    "a a a" 1fr
    "b b b" 1fr
    "c c c" 1fr / 1fr 1fr auto;
}
```

The `repeat()` function isn't allowed in these track listings.

- ## Talk to father

  - ### `justify-items`, `align-items` and `place-items`

    **about each one of the cell**

    - justify-items
    - align-items
    - place-items: (vertical), (horizon)

    * stretch(default) : stretch the child to fill the cell.
    * start: Place the item at the beginning of the cell.
    * end: Place the item at the end of the cell.
    * center: Place the item at the center of the cell.

  - ### `justify-content`, `align-content` and `place-content`

    **about the whole grid**

    - justify-content
    - align-content
    - place-content: (vertical), (horizon)

    Can use `start` `end` `center` `space-between` `space-evenly` `space-around` **not** `stretch`

- ## Talk to child

  - ### `justify-self`, `align-self`, `place-self`

    same as above.
