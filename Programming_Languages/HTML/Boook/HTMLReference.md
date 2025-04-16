Absolutely! Here's a **detailed HTML Element Reference** with examples and explanations, covering commonly used and essential elements.

---

# 🧩 **HTML Element Reference with Examples**

---

## 📄 **Document Structure Elements**

### `<!DOCTYPE>`
Declares the HTML version used in the document.

```html
<!DOCTYPE html>
```

### `<html>`
Root element of the HTML document.

```html
<html lang="en">
  <!-- Head and body go here -->
</html>
```

### `<head>`
Container for metadata, scripts, styles, etc.

```html
<head>
  <meta charset="UTF-8">
  <title>My Website</title>
</head>
```

### `<meta>`
Defines metadata like character set, viewport, etc.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

### `<title>`
Sets the page title (shown in the browser tab).

```html
<title>My Portfolio</title>
```

---

## 📚 **Text Content Elements**

### `<h1>` – `<h6>`
Headings from most to least important.

```html
<h1>Main Title</h1>
<h2>Section Title</h2>
```

### `<p>`
Paragraph element.

```html
<p>This is a paragraph of text.</p>
```

### `<a>`
Hyperlink to another page or resource.

```html
<a href="https://example.com">Visit Example</a>
```

### `<strong>`, `<em>`
Semantic emphasis.

```html
<strong>Important!</strong>
<em>This is emphasized.</em>
```

### `<br>`
Line break (no closing tag).

```html
Line 1<br>Line 2
```

---

## 📋 **List Elements**

### `<ul>`, `<ol>`, `<li>`
Unordered and ordered lists.

```html
<ul>
  <li>Apples</li>
  <li>Bananas</li>
</ul>

<ol>
  <li>Step 1</li>
  <li>Step 2</li>
</ol>
```

---

## 🎨 **Media Elements**

### `<img>`
Embeds an image.

```html
<img src="photo.jpg" alt="A scenic photo" width="300">
```

### `<audio>`, `<video>`
Embed media players.

```html
<audio controls>
  <source src="song.mp3" type="audio/mpeg">
</audio>

<video width="320" height="240" controls>
  <source src="movie.mp4" type="video/mp4">
</video>
```

---

## 📦 **Sectioning Elements**

### `<header>`, `<footer>`
Header and footer of a section or page.

```html
<header>
  <h1>My Blog</h1>
</header>

<footer>
  <p>&copy; 2025 My Blog</p>
</footer>
```

### `<nav>`
Navigation links.

```html
<nav>
  <a href="#home">Home</a>
  <a href="#about">About</a>
</nav>
```

### `<main>`, `<section>`, `<article>`, `<aside>`
Content layout.

```html
<main>
  <section>
    <h2>Introduction</h2>
  </section>
  <article>
    <h2>Blog Post</h2>
    <p>Content here.</p>
  </article>
</main>
```

---

## 📇 **Table Elements**

```html
<table>
  <thead>
    <tr>
      <th>Name</th><th>Age</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Jane</td><td>30</td>
    </tr>
  </tbody>
</table>
```

- `<table>` – wraps the whole table.
- `<thead>`, `<tbody>`, `<tfoot>` – table sections.
- `<tr>` – table row.
- `<td>` – table cell.
- `<th>` – table header cell.

---

## ✏️ **Form Elements**

```html
<form action="/submit" method="post">
  <label for="email">Email:</label>
  <input type="email" id="email" name="email" required>

  <textarea name="message"></textarea>

  <select name="options">
    <option value="1">Option 1</option>
  </select>

  <button type="submit">Send</button>
</form>
```

- `<form>` – form container.
- `<input>` – various types (`text`, `email`, `password`, etc.).
- `<label>` – label for inputs.
- `<textarea>` – multiline text input.
- `<select>`, `<option>` – dropdown menu.
- `<button>` – clickable button.

---

## 🧪 **Scripting & Embedded Content**

### `<script>`
Embed or reference JavaScript.

```html
<script>
  alert("Hello, world!");
</script>

<script src="main.js"></script>
```

### `<style>`
Add internal CSS.

```html
<style>
  body {
    font-family: sans-serif;
  }
</style>
```

---

## 🆕 **HTML5 Elements**

### `<canvas>`
For drawing graphics via JavaScript.

```html
<canvas id="myCanvas" width="200" height="100"></canvas>
```

### `<svg>`
Scalable Vector Graphics.

```html
<svg width="100" height="100">
  <circle cx="50" cy="50" r="40" stroke="black" fill="red" />
</svg>
```

### `<details>` and `<summary>`
Collapsible sections.

```html
<details>
  <summary>More info</summary>
  <p>This is hidden by default.</p>
</details>
```

---

## 🏷️ **Miscellaneous**

### `<div>` and `<span>`
Generic containers for layout/styling.

```html
<div class="container">
  <span class="highlight">Inline content</span>
</div>
```

### `<iframe>`
Embed another page within the page.

```html
<iframe src="https://example.com" width="300" height="200"></iframe>
```

---
