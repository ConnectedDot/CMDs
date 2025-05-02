# Comprehensive HTML Snippets, Commands, and Code Examples

This document provides a structured and comprehensive list of HTML snippets, commands, and code examples, organized by complexity and use case. Each section builds upon the previous one, starting from beginner-level concepts and progressing to advanced techniques.

---

## 1. Beginner-Level HTML



### 1.0 All HTML Tags and Their Uses

Below is a comprehensive list of HTML tags and their purposes:

#### Document Structure
- `<html>`: Root element of an HTML document.
- `<head>`: Contains metadata and links to external resources.
- `<body>`: Contains the content of the document.

#### Metadata
- `<title>`: Sets the title of the document.
- `<meta>`: Defines metadata like character set, viewport, etc.
- `<link>`: Links to external resources like stylesheets.
- `<style>`: Embeds CSS styles within the document.

#### Text Content
- `<h1>` to `<h6>`: Headings, `<h1>` being the largest.
- `<p>`: Paragraphs.
- `<span>`: Inline container for text.
- `<div>`: Block-level container for grouping content.

#### Lists
- `<ul>`: Unordered list.
- `<ol>`: Ordered list.
- `<li>`: List item.

#### Links and Navigation
- `<a>`: Hyperlink.
- `<nav>`: Defines navigation links.

#### Media
- `<img>`: Embeds an image.
- `<video>`: Embeds a video.
- `<audio>`: Embeds audio content.
- `<source>`: Specifies media sources for `<video>` or `<audio>`.

#### Tables
- `<table>`: Defines a table.
- `<thead>`: Groups header rows in a table.
- `<tbody>`: Groups body rows in a table.
- `<tr>`: Table row.
- `<th>`: Table header cell.
- `<td>`: Table data cell.

#### Forms
- `<form>`: Defines a form.
- `<input>`: Input field.
- `<textarea>`: Multi-line text input.
- `<button>`: Button.
- `<label>`: Label for form elements.
- `<select>`: Dropdown list.
- `<option>`: Options within a dropdown.

#### Semantic Elements
- `<header>`: Defines a header for a document or section.
- `<footer>`: Defines a footer for a document or section.
- `<main>`: Main content of the document.
- `<section>`: Groups related content.
- `<article>`: Self-contained content.
- `<aside>`: Content aside from the main content.
- `<figure>`: Groups media content with a caption.
- `<figcaption>`: Caption for `<figure>`.

#### Scripting
- `<script>`: Embeds or links to JavaScript.
- `<noscript>`: Content displayed if JavaScript is disabled.

#### Interactive Elements
- `<details>`: Creates a collapsible content area.
- `<summary>`: Summary for `<details>`.
- `<dialog>`: Defines a dialog box or modal.

#### Inline Text Semantics
- `<b>`: Bold text.
- `<i>`: Italic text.
- `<strong>`: Strong importance.
- `<em>`: Emphasized text.
- `<mark>`: Highlighted text.
- `<code>`: Inline code snippet.
- `<pre>`: Preformatted text.

#### Other
- `<canvas>`: Graphics drawing area.
- `<iframe>`: Embeds another HTML document.
- `<progress>`: Displays progress of a task.
- `<meter>`: Displays a scalar measurement.
- `<time>`: Represents a specific time or duration.

This list covers most of the commonly used HTML tags. For more advanced or less common tags, refer to the official HTML documentation.



### 1.1 Basic HTML Structure
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Basic HTML Page</title>
</head>
<body>
    <h1>Welcome to HTML</h1>
    <p>This is a basic HTML page structure.</p>
</body>
</html>
```

### 1.2 Common Tags
```html
<h1>Heading 1</h1>
<p>This is a paragraph.</p>
<a href="https://example.com">This is a link</a>
<img src="image.jpg" alt="Description of image">
```

### 1.3 Lists
```html
<!-- Ordered List -->
<ol>
    <li>First item</li>
    <li>Second item</li>
</ol>

<!-- Unordered List -->
<ul>
    <li>First item</li>
    <li>Second item</li>
</ul>
```

---

## 2. Intermediate-Level HTML

### 2.1 Forms
```html
<form action="/submit" method="post">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name">
    <button type="submit">Submit</button>
</form>
```

### 2.2 Tables
```html
<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Age</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>John</td>
            <td>30</td>
        </tr>
    </tbody>
</table>
```

### 2.3 Semantic Elements
```html
<header>
    <h1>Website Header</h1>
</header>
<main>
    <p>Main content goes here.</p>
</main>
<footer>
    <p>Footer information.</p>
</footer>
```

---

## 3. Advanced-Level HTML

### 3.1 Multimedia
```html
<!-- Video -->
<video controls>
    <source src="video.mp4" type="video/mp4">
    Your browser does not support the video tag.
</video>

<!-- Audio -->
<audio controls>
    <source src="audio.mp3" type="audio/mpeg">
    Your browser does not support the audio tag.
</audio>
```

### 3.2 Forms with Validation
```html
<form action="/submit" method="post">
    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required>
    <button type="submit">Submit</button>
</form>
```

### 3.3 Canvas
```html
<canvas id="myCanvas" width="200" height="100" style="border:1px solid #000;"></canvas>
<script>
    const canvas = document.getElementById('myCanvas');
    const ctx = canvas.getContext('2d');
    ctx.fillStyle = 'blue';
    ctx.fillRect(10, 10, 150, 75);
</script>
```

---

## 4. Expert-Level HTML

### 4.1 Accessibility Best Practices
```html
<button aria-label="Close">X</button>
```

### 4.2 Custom Data Attributes
```html
<div data-user-id="12345">User Info</div>
```

### 4.3 Progressive Web App (PWA) Manifest
```json
{
    "name": "My App",
    "short_name": "App",
    "start_url": "/",
    "display": "standalone",
    "background_color": "#ffffff",
    "theme_color": "#000000"
}
```

---

This list is a starting point and can be expanded with more examples and use cases as needed.  