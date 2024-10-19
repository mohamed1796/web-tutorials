HTML (HyperText Markup Language) is the standard language for creating web pages. It provides the structure and layout for a webpage using a series of elements or "tags." Here are the key concepts a beginner should know:

### 1. **HTML Document Structure**
An HTML document starts with a `<!DOCTYPE html>` declaration, followed by the `<html>` element which contains two main sections: the `<head>` and `<body>`.

- **Example**:
    ```html
    <!DOCTYPE html>
    <html>
      <head>
        <title>My First Web Page</title>
      </head>
      <body>
        <h1>Welcome to HTML!</h1>
        <p>This is a paragraph.</p>
      </body>
    </html>
    ```

### 2. **HTML Elements**
HTML elements are written using tags, and many have opening and closing tags (`<tag>content</tag>`). Some are self-closing (`<tag />`).

- **Example**:
    ```html
    <h1>This is a heading</h1>
    <p>This is a paragraph.</p>
    ```

### 3. **Headings**
Headings range from `<h1>` (most important) to `<h6>` (least important). They define the headings of sections.

- **Example**:
    ```html
    <h1>Main Title</h1>
    <h2>Subheading</h2>
    <h3>Smaller Heading</h3>
    ```

### 4. **Paragraphs**
The `<p>` tag is used for paragraphs of text.

- **Example**:
    ```html
    <p>This is a sample paragraph with some text.</p>
    ```

### 5. **Links**
The `<a>` tag creates hyperlinks, allowing users to navigate from one page to another.

- **Example**:
    ```html
    <a href="https://www.example.com">Click here to visit Example</a>
    ```

### 6. **Images**
The `<img>` tag is used to embed images. It is self-closing and requires a `src` attribute for the image path and an `alt` attribute for alternative text.

- **Example**:
    ```html
    <img src="image.jpg" alt="A description of the image" />
    ```

### 7. **Lists**
HTML supports ordered (`<ol>`) and unordered (`<ul>`) lists. Each item in a list is defined by the `<li>` tag.

- **Example** (Ordered List):
    ```html
    <ol>
      <li>First item</li>
      <li>Second item</li>
    </ol>
    ```

- **Example** (Unordered List):
    ```html
    <ul>
      <li>Item one</li>
      <li>Item two</li>
    </ul>
    ```

### 8. **Forms**
Forms allow users to submit data. The `<form>` tag wraps inputs, text fields, buttons, etc.

- **Example**:
    ```html
    <form action="/submit-form" method="post">
      <label for="name">Name:</label>
      <input type="text" id="name" name="name">
      <input type="submit" value="Submit">
    </form>
    ```

### 9. **Attributes**
Attributes provide additional information about HTML elements. Common attributes include `href` (for links), `src` (for images), `id`, `class`, `style`, etc.

- **Example**:
    ```html
    <p id="intro" class="text">This is a paragraph with an ID and class.</p>
    ```

### 10. **Comments**
Comments in HTML help explain the code and are ignored by the browser.

- **Example**:
    ```html
    <!-- This is a comment -->
    ```

### 11. **Tables**
The `<table>` element is used to display tabular data with rows and columns.

- **Example**:
    ```html
    <table>
      <tr>
        <th>Header 1</th>
        <th>Header 2</th>
      </tr>
      <tr>
        <td>Row 1, Cell 1</td>
        <td>Row 1, Cell 2</td>
      </tr>
    </table>
    ```

### 12. **Div and Span**
- `<div>` is a block-level container used for layout and grouping elements.
- `<span>` is an inline container used to style or group text.

- **Example**:
    ```html
    <div class="container">
      <p>This is inside a div.</p>
    </div>

    <span style="color:red">This text is red.</span>
    ```

### 13. **Semantics**
Semantic elements like `<article>`, `<section>`, `<nav>`, and `<footer>` give meaning to the content structure of your page, improving accessibility and SEO.

- **Example**:
    ```html
    <article>
      <h2>Article Title</h2>
      <p>This is an article.</p>
    </article>

    <footer>
      <p>Footer content goes here.</p>
    </footer>
    ```

These are the essential building blocks to start working with HTML. By understanding these concepts and elements, you’ll be able to create simple yet functional web pages.
