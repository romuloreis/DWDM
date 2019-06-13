# Notas de aula - Entendo GRID

# Reminder: 
  - The new [**fr**](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Basic_Concepts_of_Grid_Layout) unit represents a fraction of the available space in the grid container.
  - use multiple classes for make the examples simpler
  - **class** item item1
  
  ```css
  .item:nth-child(even){
    background: #236fc8;
  }
  ```

## Overview - Intro.

### Grid Layout
A grid layout consists of a parent element (grid container), with one or more child elements.
The CSS Grid Layout Module offers a grid-based layout system, with rows and columns, making it easier to design web pages without having to use floats and positioning.


### Grid Elements
All direct children of the grid container automatically become grid items.
An HTML element becomes a grid container when its display property is set to _grid_ or _inline-grid_.

```html
<!DOCTYPE html>
<html>
<head>
<style>
.grid-container {
  display: grid; /*Set the display property to grid to make a block-level grid container.*/
  /*  display: inline-grid; Set the display property to inline-grid to make an inline grid container.*/
  
  grid-template-columns: auto auto auto;
  background-color: #2196F3;
  padding: 10px;
}
.grid-item {
  background-color: rgba(255, 255, 255, 0.8);
  border: 1px solid rgba(0, 0, 0, 0.8);
  padding: 20px;
  font-size: 30px;
  text-align: center;
}
</style>
</head>
<body>

<h1>Grid Elements</h1>

<p>A Grid Layout must have a parent element with the <em>display</em> property set to <em>grid</em> or <em>inline-grid</em>.</p>

<p>Direct child element(s) of the grid container automatically becomes grid items.</p>

<div class="grid-container">
  <div class="grid-item">1</div>
  <div class="grid-item">2</div>
  <div class="grid-item">3</div>  
  <div class="grid-item">4</div>
  <div class="grid-item">5</div>
  <div class="grid-item">6</div>  
  <div class="grid-item">7</div>
  <div class="grid-item">8</div>
  <div class="grid-item">9</div>  
</div>

</body>
</html>
```


## Drawing time!

### Grid Columns
The vertical lines of grid items are called columns.

### Grid Rows
The horizontal lines of grid items are called rows.

### Grid Gaps
The spaces between each column/row are called gaps.
You can adjust the gap size by using one of the following properties:

 - grid-column-gap (sets the gap between the columns:)
 - grid-row-gap (sets the gap between the rows:)
 - grid-gap (is a shorthand property for the grid-column-gap and the grid-row-gap properties:)

```css
.grid-container {
  display: grid;
  /*adjust the space between the columns.*/
  grid-column-gap: 50px;
  /*sets the gap between the rows*/
  grid-row-gap: 50px;
  /*shorthand property for the grid-column-gap and the grid-row-gap properties*/
  grid-gap: 50px 100px;
  /*grid-gap property can also be used to set both the row gap and the column gap in one value*/
  grid-gap: 50px;
}
```


### Grid Lines
The lines between columns are called column lines.

The lines between rows are called row lines.

Refer to line numbers when placing a grid item in a grid container:

**Example:** 
Place a grid item at column line 1, and let it end on column line 3:

```css
.item1 {
  grid-column-start: 1;
  grid-column-end: 3;
}
```

Place a grid item at row line 1, and let it end on row line 3:
```css
.item1 {
  grid-column-start: 1;
  grid-column-end: 3;
}
```

## Grid Container
To make an HTML element behave as a grid container, you have to set the display property to grid or inline-grid.

Grid containers consist of grid items, placed inside columns and rows.

### The grid-template-columns Property
The grid-template-columns property defines the number of columns in your grid layout, and it can define the width of each column.

The value is a space-separated-list, where each value defines the length of the respective column.

If you want your grid layout to contain 4 columns, specify the width of the 4 columns, or "auto" if all columns should have the same width.

**Example** 
Make a grid with 4 columns:
 > Note: If you have more than 4 items in a 4 columns grid, the grid will automatically add a new row to put the items in.

```html
<!DOCTYPE html>
<html>
<head>
<style>
.grid-container {
  display: grid;
  grid-template-columns: auto auto auto auto;
  grid-gap: 10px;
  background-color: #2196F3;
  padding: 10px;
}

.grid-container > div {
  background-color: rgba(255, 255, 255, 0.8);
  text-align: center;
  padding: 20px 0;
  font-size: 30px;
}
</style>
</head>
<body>

<h1>grid-template-columns</h1>

<p>You can use the <em>grid-template-columns</em> property to specify the number of columns in your grid layout.</p>

<div class="grid-container">
  <div>1</div>
  <div>2</div>
  <div>3</div>  
  <div>4</div>
  <div>5</div>
  <div>6</div>  
  <div>7</div>
  <div>8</div>
</div>

</body>
</html>

```

**Explicit**: The grid-template-columns property can also be used to specify the size (width) of the columns. 

```css
.grid-container {
  display: grid;
  grid-template-columns: 80px 200px auto 40px; /*Set a size for the 4 columns:*/
}
```

**Repit function(qnt, size)**
```css
  grid-template-columns: repeat(4, 220px);
```

**Using Fraction**
```css
  grid-template-columns: 1fr 3fr 1fr;
```

## The grid-template-rows Property
The grid-template-rows property defines the height of each row.
The value is a space-separated-list, where each value defines the height of the respective row:

```css
.grid-container {
  display: grid;
  grid-template-columns: auto auto auto;
  grid-template-rows: 80px 200px;
  grid-gap: 10px;
  background-color: #2196F3;
  padding: 10px;
}
```

### The justify-content Property
The justify-content property is used to align the whole grid inside the container.

 > Note: The grid's total width has to be less than the container's width for the justify-content property to have any effect.

**space-evenly** will give the columns equal amount of space between, and around them:

```html
<!DOCTYPE html>
<html>
<head>
<style>
.grid-container {
  display: grid;
  justify-content: space-evenly;
  grid-template-columns: 50px 50px 50px; /*Make the grid smaller than the container*/
  grid-gap: 10px;
  background-color: #2196F3;
  padding: 10px;
}

.grid-container > div {
  background-color: rgba(255, 255, 255, 0.8);
  text-align: center;
  padding: 20px 0;
  font-size: 30px;
}
</style>
</head>
<body>
<div class="grid-container">
  <div>1</div>
  <div>2</div>
  <div>3</div>  
  <div>4</div>
  <div>5</div>
  <div>6</div>  
</div>


</body>
</html>
```

**space-around** will give the columns equal amount of space around them:

```css
.grid-container {
  display: grid;
  justify-content: space-around;
}
```

**space-between** will give the columns equal amount of space between them:

```css
.grid-container {
  display: grid;
  justify-content: space-between;
}
```

**center** will align the grid in the middle of the container:

```css
.grid-container {
  display: grid;
  justify-content: center;
}
```
**start** will align the grid at the beginning of the container:
```css
.grid-container {
  display: grid;
  justify-content: start;
}

```
**end** will align the grid at the end of the container:

```css
.grid-container {
  display: grid;
  justify-content: end;
}
```

## The align-content Property

The **align-content property** is used to _**vertically**_ align the whole grid inside the container.
 > Note: The grid's total height has to be less than the container's height for the align-content property to have any effect.
 
 - The value "center" will align the rows in the middle of the container:

 - The value "space-evenly" will give the rows equal amount of space between, and around them:

 - The value "space-around" will give the rows equal amount of space around them:

 - The value "space-between" will give the rows equal amount of space between them:

 - The value "start" will align the rows at the beginning of the container:

  - The value "end" will align the rows at the end of the container:


 
 ```html
 <!DOCTYPE html>
<html>
<head>
<style>
.grid-container {
  display: grid;
  height: 400px;
  align-content: center;
  grid-template-columns: auto auto auto;
  grid-gap: 10px;
  background-color: #2196F3;
  padding: 10px;
}

.grid-container > div {
  background-color: rgba(255, 255, 255, 0.8);
  text-align: center;
  padding: 20px 0;
  font-size: 30px;
}
</style>
</head>
<body>

<h1>The align-content Property</h1>

<p>Use the <em>align-content</em> property to vertically align the grid inside the container.</p>

<p>The value "center" will align the rows in the middle of the container:</p>

<div class="grid-container">
  <div>1</div>
  <div>2</div>
  <div>3</div>  
  <div>4</div>
  <div>5</div>
  <div>6</div>  
</div>
</body>
</html>
```

# Child Elements (Items)
A grid container contains grid items.

By default, a container has one grid item for each column, in each row, but you can style the grid items so that they will span multiple columns and/or rows.

## The grid-column Property:
The grid-column property defines on which column(s) to place an item.

You define where the item will start, and where the item will end.

 > Note: The grid-column property is a shorthand property for the grid-column-start and the grid-column-end properties.

To place an item, you can refer to line numbers, or use the keyword "span" to define how many columns the item will span.

Examples:

Item1 will start on column-line 1 and end on column-line 5:

```html
<!DOCTYPE html>
<html>
<head>
<style>
.grid-container {
  display: grid;
  grid-template-columns: auto auto auto auto auto auto;
  grid-gap: 10px;
  background-color: #2196F3;
  padding: 10px;
}

.grid-container > div {
  background-color: rgba(255, 255, 255, 0.8);
  text-align: center;
  padding: 20px 0;
  font-size: 30px;
}

.item1 {
  grid-column: 1 / 5;
}
</style>
</head>
<body>

<h1>The grid-column Property</h1>

<p>Use the <em>grid-column</em> property to specify where to place an item.</p>
<p>Item1 will start on column-line 1 and end on column-line 5:</p>

<div class="grid-container">
  <div class="item1">1</div>
  <div class="item2">2</div>
  <div class="item3">3</div>  
  <div class="item4">4</div>
  <div class="item5">5</div>
  <div class="item6">6</div>
  <div class="item7">7</div>
  <div class="item8">8</div>  
  <div class="item9">9</div>
  <div class="item10">10</div>
  <div class="item11">11</div>
  <div class="item12">12</div>
  <div class="item13">13</div>
  <div class="item14">14</div>
  <div class="item15">15</div>
</div>

</body>
</html>

```

Make "item1" start on column 1 and span 3 columns:

```css
.item1 {
  grid-column: 1 / span 3;
}
```
 
Make "item2" start on column 2 and span 3 columns:
```css
.item2 {
  grid-column: 2 / span 3;
}
```

Make "item2" span 3 columns:
```css
.item2 {
  grid-column: span 3;
}
```

## The grid-row Property:
The grid-row property defines on which row to place an item.

You define where the item will start, and where the item will end.

To place an item, you can refer to line numbers, or use the keyword "span" to define how many rows the item will span:

 > Note: The grid-row property is a shorthand property for the grid-row-start and the grid-row-end properties.

**Examples:**
Make "item1" start on row-line 1 and end on row-line 4:

```css
.item1 {
  grid-row: 1 / 4;
}
```

Make "item1" start on row 1 and span 2 rows:

```css
.item1 {
  grid-row: 1 / span 2;
}
```

## The grid-area Property
You can use the grid-area property to specify where to place an item.

**The syntax is:**

 - _**grid-row-start / grid-column-start / grid-row-end / grid-column-end.**_

The grid-area property can be used as a shorthand property for the grid-row-start, grid-column-start, grid-row-end and the grid-column-end properties.

Examples:
Make "item8" start on row-line 1 and column-line 2, and end on row-line 5 and column line 6:

 ```css
.item8 {
  grid-area: 1 / 2 / 5 / 6;
}
```

Make "item8" start on row-line 2 and column-line 1, and span 2 rows and 3 columns:

```css
.item8 {
  grid-area: 2 / 1 / span 2 / span 3;
}
```

## Naming Grid Items
The grid-area property can also be used to assign names to grid items.
Named grid items can be referred to by the grid-template-areas property of the grid container.

You can use the grid-area property to name grid items.
You can refer to the name when you set up the grid layout, by using the grid-template-areas property on the grid container.

Item1 gets the name "myArea" and spans all five columns in a five columns grid layout:

```css
<!DOCTYPE html>
<html>
<head>
<style>
.item1 {
  grid-area: myArea;
}

.grid-container {
  display: grid;
  grid-template-areas: 'myArea myArea myArea myArea myArea';
  grid-gap: 10px;
  background-color: #2196F3;
  padding: 10px;
}

.grid-container > div {
  background-color: rgba(255, 255, 255, 0.8);
  text-align: center;
  padding: 20px 0;
  font-size: 30px;
}
</style>
</head>
<body>

<h1>The grid-area Property</h1>

<p>You can use the <em>grid-area</em> property to name grid items.</p>

<p>You can refer to the name when you set up the grid layout, by using the <em>grid-template-areas</em> property on the grid container.</p>

<p>Item1, is called "myArea" and will take up the place of all five columns:</p>

<div class="grid-container">
  <div class="item1">1</div>
  <div class="item2">2</div>
  <div class="item3">3</div>  
  <div class="item4">4</div>
  <div class="item5">5</div>
  <div class="item6">6</div>
</div>

</body>
</html>
```
 Each row is defined by apostrophes (' ')

The columns in each row is defined inside the apostrophes, separated by a space.
Note: A period sign represents a grid item with no name.

Let "myArea" span two columns in a five columns grid layout (period signs represent items with no name):

 ```css
 .item1 {
  grid-area: myArea;
}
.grid-container {
  grid-template-areas: 'myArea myArea . . .';
} 

```

To define two rows, define the column of the second row inside another set of apostrophes.
Make "item1" span two columns and two rows:


```css
.grid-container {
  grid-template-areas: 'myArea myArea . . .' 'myArea myArea . . .';
} 

```

Name all items, and make a ready-to-use webpage template:

```css
<!DOCTYPE html>
<html>
<head>
<style>
.item1 { grid-area: header; }
.item2 { grid-area: menu; }
.item3 { grid-area: main; }
.item4 { grid-area: right; }
.item5 { grid-area: footer; }

.grid-container {
  display: grid;
  grid-template-areas:
    'header header header header header header'
    'menu main main main right right'
    'menu footer footer footer footer footer';
  grid-gap: 10px;
  background-color: #2196F3;
  padding: 10px;
}

.grid-container > div {
  background-color: rgba(255, 255, 255, 0.8);
  text-align: center;
  padding: 20px 0;
  font-size: 30px;
}
</style>
</head>
<body>

<h1>The grid-area Property</h1>

<p>You can use the <em>grid-area</em> property to name grid items.</p>

<p>You can refer to the name when you set up the grid layout, by using the <em>grid-template-areas</em> property on the grid container.</p>

<p>This grid layout contains six columns and three rows:</p>

<div class="grid-container">
  <div class="item1">Header</div>
  <div class="item2">Menu</div>
  <div class="item3">Main</div>  
  <div class="item4">Right</div>
  <div class="item5">Footer</div>
</div>

</body>
</html>


```

## The Order of the Items


# REFER

[symbols in CSS Selector](https://techbrij.com/css-selector-adjacent-child-sibling)
