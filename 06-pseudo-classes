### What are Pseudo-Classes?

Pseudo-classes in CSS are keywords added to selectors that specify a special state of the selected elements. They allow you to style elements based on their state, position, or user interaction without adding classes or modifying the DOM.

### Common Pseudo-Classes and Examples

#### 1. `:hover`
Applies styles when the user hovers over an element (e.g., with a mouse).

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <style>
    button {
      background-color: lightblue;
      color: black;
      padding: 10px 20px;
      border: none;
      cursor: pointer;
    }
    button:hover {
      background-color: blue;
      color: white;
    }
  </style>
</head>
<body>
  <button>Hover me!</button>
</body>
</html>
```

---

#### 2. `:focus`
Applies styles when an element receives focus (e.g., a form input is clicked or tabbed into).

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <style>
    input {
      border: 2px solid gray;
      padding: 5px;
    }
    input:focus {
      border-color: green;
      outline: none;
    }
  </style>
</head>
<body>
  <input type="text" placeholder="Focus on me">
</body>
</html>
```

---

#### 3. `:nth-child(n)`
Styles elements based on their position among siblings.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <style>
    ul li:nth-child(odd) {
      background-color: lightgray;
    }
    ul li:nth-child(even) {
      background-color: white;
    }
  </style>
</head>
<body>
  <ul>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
    <li>Item 4</li>
  </ul>
</body>
</html>
```

---

#### 4. `:first-child` and `:last-child`
Styles the first or last child of a parent.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <style>
    p:first-child {
      font-weight: bold;
    }
    p:last-child {
      color: red;
    }
  </style>
</head>
<body>
  <div>
    <p>First paragraph</p>
    <p>Middle paragraph</p>
    <p>Last paragraph</p>
  </div>
</body>
</html>
```

---

#### 5. `:not(selector)`
Styles elements that do not match the specified selector.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <style>
    button:not(.primary) {
      background-color: gray;
      color: white;
    }
    .primary {
      background-color: blue;
      color: white;
    }
  </style>
</head>
<body>
  <button class="primary">Primary Button</button>
  <button>Secondary Button</button>
</body>
</html>
```

---

#### 6. `:disabled` and `:enabled`
Styles form elements based on their state.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <style>
    input:disabled {
      background-color: lightgray;
      color: darkgray;
    }
    input:enabled {
      background-color: white;
      color: black;
    }
  </style>
</head>
<body>
  <input type="text" placeholder="Enabled" enabled>
  <input type="text" placeholder="Disabled" disabled>
</body>
</html>
```

---

#### 7. `:checked`
Applies styles to checkboxes or radio buttons that are selected.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <style>
    input[type="checkbox"]:checked + label {
      color: green;
    }
  </style>
</head>
<body>
  <input type="checkbox" id="agree">
  <label for="agree">I agree</label>
</body>
</html>
```

### Conclusion
Pseudo-classes are powerful tools that help in dynamically styling elements without requiring JavaScript or DOM changes. They are especially useful for interactivity and handling specific element states.
