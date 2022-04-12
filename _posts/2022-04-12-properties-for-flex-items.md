---
title: "Properties for flex-items"
categories:
  - CSS
tags:
  - coding
  - css
  - flex
---

### flex

```css
.flex_item {
  flex: 1;
  /* flex: 1 1 0; */
}
```

is same

```css
.flex_item {
  flex-grow: 1;
  flex-shrink: 1;
  flex-basis: 0;
}
```

**flex-grow** and **flex-shrink** are uesful when you do responsive design!
So, check this.

### flex-grow

**flex-grow** is about flex-itme 's expansion.
It is specified as a single <number>.
Negative values are invalid.
Defaults : 0.

If the value is greater than 0, the size of the flex item increases to fill the flex container regardless of the original size
Use you want when screen is bigger, the element is bigger too.
Default : when screen is bigger, the blank is bigger.

### flex-shrink

**flex-shrink** is about flex-itme 's shrink.
It is specified as a single <number>.
Negative values are invalid.
Defaults : 1.

If the size of all flex items is larger than the flex container, items shrink to fit according to **flex-shrink**.

**flex-shrink: 0;** is useful to make fixed width columns. when the value is 0, specify the **width**.

```css
.container {
  display: flex;
}
.item:nth-child(1) {
  flex-shrink: 0;
  width: 100px;
}
.item:nth-child(2) {
  flex-grow: 1;
}
```

### flex-basis

The **flex-basis** property sets the initial main size of a flex item.

The **flex-basis** property is specified as either the keyword content or a <'width'>.
단위를 꼭 써줘야한다. 0값을 줄때도.
Defaults : auto

**<'width'>**
An absolute <length>, a <percentage> of the parent flex container's main size property, or the keyword auto. Negative values are invalid. Defaults to auto.

**content**
max-content, min-content, fit-content, content, fill

```css
.item {
  flex-basis: 0;
}
```

flex-item 's size is deermined by size of **flex container**

```css
.item {
  flex-basis: auto;
}
```

flex-item 's size is deermined by size of **contents**

### again **flex**

initial value : `flex: 0 1 auto;`

So when `flex` is specified single <number>, it mean `flex-grow`.
For example `flex: 2;` is same `flex: 2 1 0;` .

You want fix the size of flex-item. Use `flex: none;`
This mean `flex-grow: 0; flex-shrink: 0; flex-basis: auto;`
