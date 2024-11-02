CSS Flexbox (Flexible Box Layout) is a powerful layout model that allows you to create responsive and flexible web layouts. Flexbox is particularly useful for arranging elements in rows or columns and aligning them within their container. Here’s a breakdown with examples to help you understand how it works.

### Flex Container and Flex Items

The Flexbox layout consists of a **flex container** and **flex items**:
- **Flex Container**: The parent element where Flexbox properties are applied.
- **Flex Items**: The child elements of the flex container.

### Basic Flexbox Properties

1. **`display: flex;`** - This property is applied to the container element to enable Flexbox layout.

   ```css
   .container {
     display: flex;
   }
   ```

2. **`flex-direction`** - Defines the direction of flex items in the container.
   - `row` (default): Items are placed in a row (horizontally).
   - `column`: Items are placed in a column (vertically).
   - `row-reverse`: Reverses the order in a row.
   - `column-reverse`: Reverses the order in a column.

   ```css
   .container {
     display: flex;
     flex-direction: column;
   }
   ```

3. **`justify-content`** - Aligns items along the main axis (horizontally by default).
   - `flex-start`: Items start from the beginning.
   - `flex-end`: Items align to the end.
   - `center`: Items are centered.
   - `space-between`: Items are spaced evenly, with the first item at the start and last at the end.
   - `space-around`: Items are spaced with equal space around them.

   ```css
   .container {
     display: flex;
     justify-content: space-between;
   }
   ```

4. **`align-items`** - Aligns items along the cross axis (vertically by default).
   - `flex-start`: Aligns items to the top.
   - `flex-end`: Aligns items to the bottom.
   - `center`: Centers items vertically.
   - `stretch`: Stretches items to fill the container.
   - `baseline`: Aligns items based on the baseline of the text.

   ```css
   .container {
     display: flex;
     align-items: center;
   }
   ```

5. **`flex-wrap`** - Controls whether items should wrap onto multiple lines.
   - `nowrap` (default): All items are on a single line.
   - `wrap`: Items wrap to the next line if needed.
   - `wrap-reverse`: Items wrap to the next line in reverse order.

   ```css
   .container {
     display: flex;
     flex-wrap: wrap;
   }
   ```

6. **`align-content`** - Aligns multiple lines of items along the cross axis when `flex-wrap` is enabled.
   - `flex-start`, `flex-end`, `center`, `space-between`, `space-around`, `stretch`

   ```css
   .container {
     display: flex;
     flex-wrap: wrap;
     align-content: space-around;
   }
   ```

### Flex Item Properties

Each flex item can also have its own properties to control its size and behavior.

1. **`flex-grow`** - Defines how much a flex item should grow relative to others.
   - Default is `0` (no growth).
   - A higher value will make the item grow more compared to others.

   ```css
   .item {
     flex-grow: 1;
   }
   ```

2. **`flex-shrink`** - Defines how much a flex item should shrink relative to others.
   - Default is `1` (items will shrink as needed).
   - Setting `0` prevents the item from shrinking.

   ```css
   .item {
     flex-shrink: 0;
   }
   ```

3. **`flex-basis`** - Defines the initial size of a flex item before it grows or shrinks.
   - Can be set in pixels, percentages, or other units.

   ```css
   .item {
     flex-basis: 200px;
   }
   ```

4. **`align-self`** - Overrides the `align-items` property for a specific flex item.
   - Values are the same as `align-items`: `auto`, `flex-start`, `flex-end`, `center`, `baseline`, `stretch`

   ```css
   .item {
     align-self: flex-end;
   }
   ```

### Example Code

```html
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```

```css
.container {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
  height: 200px;
  background-color: #f0f0f0;
}

.item {
  flex-grow: 1;
  padding: 20px;
  background-color: #4caf50;
  color: white;
  margin: 5px;
  text-align: center;
}
```

This example creates a horizontal flex container with three items that are spaced evenly with `space-around`. Each item grows to fill available space. Adjusting these properties lets you create flexible and responsive layouts easily with Flexbox.
