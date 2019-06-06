# Notas de aula - Entendo GRID

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

The grid-template-columns property can also be used to specify the size (width) of the columns.

```css
.grid-container {
  display: grid;
  grid-template-columns: 80px 200px auto 40px; /*Set a size for the 4 columns:*/
}
```
