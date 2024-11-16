The CSS Grid Layout is a powerful layout system designed to help developers create complex and responsive web layouts more easily. It works by defining rows and columns within a container to organize child elements into a grid.

### Key Concepts of CSS Grid Layout
1. **Grid Container**: The parent element with the `display: grid;` property.
2. **Grid Items**: The child elements of the grid container.
3. **Rows and Columns**: Defined using `grid-template-rows` and `grid-template-columns`.

### Basic Example
Here's an example of a simple 2x2 grid layout:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Grid Layout Example</title>
    <style>
        .grid-container {
            display: grid;
            grid-template-columns: 100px 100px; /* Two columns each 100px wide */
            grid-template-rows: 100px 100px; /* Two rows each 100px tall */
            gap: 10px; /* 10px space between grid items */
        }
        
        .grid-item {
            background-color: lightblue;
            border: 1px solid blue;
            display: flex;
            align-items: center;
            justify-content: center;
        }
    </style>
</head>
<body>
    <div class="grid-container">
        <div class="grid-item">1</div>
        <div class="grid-item">2</div>
        <div class="grid-item">3</div>
        <div class="grid-item">4</div>
    </div>
</body>
</html>
```

### Explanation
- **`display: grid;`**: Defines the container as a grid.
- **`grid-template-columns: 100px 100px;`**: Specifies that the container has two columns, each 100 pixels wide.
- **`grid-template-rows: 100px 100px;`**: Specifies that the container has two rows, each 100 pixels tall.
- **`gap: 10px;`**: Adds a 10-pixel gap between grid items.

### Advanced Example: Responsive Grid with `fr` Units
To create a grid layout that adapts to the available space, you can use the `fr` unit, which represents a fraction of the available space.

```css
.grid-container {
    display: grid;
    grid-template-columns: 1fr 2fr 1fr; /* Three columns: 1/4, 1/2, 1/4 width */
    grid-template-rows: auto; /* Rows adjust based on content */
    gap: 20px;
}
```

### Positioning Grid Items with `grid-column` and `grid-row`
You can control where grid items are placed using the `grid-column` and `grid-row` properties.

```css
.grid-item {
    grid-column: 1 / 3; /* Span from column 1 to 3 */
    grid-row: 1 / 2; /* Occupy the first row */
}
```

This snippet positions a grid item to span across the first and second columns and be placed in the first row.

### Example Using `repeat()` and `minmax()`
```css
.grid-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr); /* Creates 3 equal columns */
    grid-template-rows: repeat(2, minmax(100px, auto)); /* 2 rows with a min height of 100px */
}
```

### Complete Code Example
```html
<div class="grid-container">
    <div class="grid-item">A</div>
    <div class="grid-item">B</div>
    <div class="grid-item">C</div>
    <div class="grid-item">D</div>
    <div class="grid-item">E</div>
    <div class="grid-item">F</div>
</div>
```

### Summary
CSS Grid Layout is a flexible and powerful tool for creating complex layouts with ease. It simplifies creating multi-column and multi-row designs and allows for sophisticated responsive designs using a straightforward syntax.
