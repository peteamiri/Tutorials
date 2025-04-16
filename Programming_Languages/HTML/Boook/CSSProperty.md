Sure! Here's a **comprehensive CSS Property Reference** with detailed examples and explanations. This guide covers commonly used properties, grouped by category, with real code snippets to help you understand how they work in practice.

---

# 🎨 **CSS Property Reference with Examples**

---

## 📐 **Box Model Properties**

### `width` / `height`
Set the size of an element.

```css
.box {
  width: 200px;
  height: 100px;
}
```

### `padding`
Space between content and border.

```css
.box {
  padding: 20px; /* applies to all sides */
  padding: 10px 15px; /* top-bottom, left-right */
}
```

### `margin`
Space outside the border.

```css
.box {
  margin: 10px;
  margin: 10px 20px 30px 40px; /* top, right, bottom, left */
}
```

### `border`
Defines the border around an element.

```css
.box {
  border: 2px solid black;
  border-radius: 8px; /* rounded corners */
}
```

### `box-sizing`
Controls how padding and border affect width/height.

```css
.box {
  box-sizing: border-box; /* includes padding and border in width/height */
}
```

---

## 🎨 **Color & Background**

### `color`
Text color.

```css
p {
  color: #333333;
}
```

### `background-color`
Background fill color.

```css
div {
  background-color: lightblue;
}
```

### `background-image`
Add a background image.

```css
div {
  background-image: url('bg.jpg');
  background-size: cover;
  background-position: center;
}
```

### `opacity`
Transparency of the element.

```css
.overlay {
  opacity: 0.5;
}
```

---

## ✍️ **Typography**

### `font-family`
Set the font type.

```css
body {
  font-family: 'Segoe UI', Tahoma, Geneva, sans-serif;
}
```

### `font-size`
Set the size of the font.

```css
h1 {
  font-size: 32px;
}
```

### `font-weight`
Set the thickness of the font.

```css
strong {
  font-weight: bold;
}
```

### `text-align`
Align text horizontally.

```css
p {
  text-align: center;
}
```

### `line-height`
Controls line spacing.

```css
p {
  line-height: 1.6;
}
```

### `text-decoration`
Modify text appearance (underline, etc.).

```css
a {
  text-decoration: none;
}
```

---

## 🧱 **Layout & Positioning**

### `display`
Defines how an element is displayed.

```css
div {
  display: block;
}
span {
  display: inline;
}
.container {
  display: flex;
}
```

### `position`
Controls element positioning.

```css
.element {
  position: relative;
  top: 10px;
  left: 20px;
}
```

- `static`, `relative`, `absolute`, `fixed`, `sticky`

### `top`, `right`, `bottom`, `left`
Used with `position` to move elements.

```css
.fixed-box {
  position: fixed;
  top: 0;
  right: 0;
}
```

### `z-index`
Stacking order of elements.

```css
.modal {
  position: absolute;
  z-index: 1000;
}
```

---

## 🧭 **Flexbox**

### `display: flex`
Enable flex container.

```css
.container {
  display: flex;
}
```

### `justify-content`
Align items horizontally.

```css
.container {
  justify-content: space-between; /* or center, space-around, etc. */
}
```

### `align-items`
Align items vertically.

```css
.container {
  align-items: center;
}
```

### `flex-direction`
Direction of main axis.

```css
.container {
  flex-direction: row; /* or column */
}
```

### `flex`
Child element flexibility.

```css
.item {
  flex: 1;
}
```

---

## 🧮 **Grid Layout**

### `display: grid`
Enable grid container.

```css
.grid {
  display: grid;
  grid-template-columns: 1fr 2fr;
  grid-gap: 10px;
}
```

### `grid-template-rows`, `grid-template-areas`
Define row sizes or layout areas.

```css
.grid {
  grid-template-areas:
    "header header"
    "sidebar content";
}
```

---

## 🔄 **Transitions & Animations**

### `transition`
Animate changes to properties.

```css
button {
  transition: background-color 0.3s ease;
}
button:hover {
  background-color: darkblue;
}
```

### `animation`
Create complex animations.

```css
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

.box {
  animation: fadeIn 1s ease-in-out;
}
```

---

## 📱 **Responsive Design**

### `media queries`
Apply styles based on screen size.

```css
@media (max-width: 600px) {
  body {
    font-size: 14px;
  }
}
```

---

## 🧩 **Miscellaneous**

### `overflow`
Handles content that overflows the container.

```css
.box {
  overflow: scroll;
}
```

### `cursor`
Changes mouse cursor on hover.

```css
a {
  cursor: pointer;
}
```

### `visibility` and `display`
Control visibility and layout presence.

```css
.hidden {
  visibility: hidden; /* hides but keeps space */
}
.none {
  display: none; /* hides and removes from flow */
}
```

### `pointer-events`
Control interaction with elements.

```css
.disabled {
  pointer-events: none;
}
```

---

## ✅ CSS Shorthand Properties

| Shorthand       | Expands To                                      |
|-----------------|--------------------------------------------------|
| `margin`        | `margin-top`, `margin-right`, etc.              |
| `padding`       | `padding-top`, `padding-right`, etc.            |
| `border`        | `border-width`, `border-style`, `border-color` |
| `font`          | `font-size`, `font-family`, etc.                |
| `background`    | `background-color`, `background-image`, etc.   |
| `transition`    | `transition-property`, `duration`, etc.         |

---
