# 6.1 Writing Clean, Professional HTML & CSS

This is about **discipline and standards**.

---

## Reusing Rules (Don’t Repeat Yourself)

### Bad:

```css id="bad1"
p { color: blue; }
h1 { color: blue; }
span { color: blue; }
```

### Good:

```css id="good1"
.text-blue {
  color: blue;
}
```

```html id="good2"
<p class="text-blue">Text</p>
<h1 class="text-blue">Title</h1>
```

---

Note:
If you repeat styles → you’re doing it wrong

---

## Commenting Code

```css id="comment1"
/* Main layout container */
.container {
  display: flex;
}
```

```html id="comment2"
<!-- Navigation section -->
<nav>...</nav>
```

Helps:

* teammates
* future you

---

## Web-safe Fonts

```css id="fontsafe1"
body {
  font-family: Arial, Helvetica, sans-serif;
}
```

Always include fallback fonts

---

## Cross-Platform Usability

Your site should work on:

* Chrome
* Firefox
* Edge
* Mobile browsers

Example issue:

```css id="cross1"
input {
  appearance: none;
}
```

Some browsers behave differently → test always

---

## Separation of Concerns

### Bad:

```html id="sepbad"
<p style="color: red;">Hello</p>
```

### Good:

```html id="sepgood1"
<p class="text-red">Hello</p>
```

```css id="sepgood2"
.text-red {
  color: red;
}
```

---

Note:
This is a **must** if you want to work on real projects

---

# 6.2 Accessibility (A11Y)

This is about making your app usable for **everyone**.

---

## Text Alternatives (alt)

```html id="a11y1"
<img src="logo.png" alt="Company logo">
```

Screen readers rely on this

---

## Color Contrast

### Bad:

```css id="contrast1"
p {
  color: lightgray;
  background: white;
}
```

Hard to read

---

### Good:

```css id="contrast2"
p {
  color: #222;
  background: white;
}
```

---

Rule:
Text must be clearly readable

---

## Typography Legibility

```css id="typo1"
p {
  font-size: 16px;
  line-height: 1.6;
}
```

Avoid:

* tiny fonts
* cramped lines

---

## Tab Order (Keyboard Navigation)

```html id="tab1"
<input type="text">
<button>Submit</button>
```

Users should navigate using **Tab key**

---

## Text Resizing

Your layout should not break when zoomed.

Test:

* Zoom browser to 200%
* Check layout

---

## Text Hierarchy

```html id="hierarchy1"
<h1>Main Title</h1>
<h2>Section</h2>
<p>Content</p>
```
 Helps:

* screen readers
* SEO
* readability

---

## Language / Translation

```html id="lang1"
<html lang="en">
```

Helps screen readers + translation tools

---

Note:
Accessibility is not optional anymore—companies care about this

---

# 6.3 Testing & Debugging (Structural Integrity)

This is where you **find and fix problems**.

---

## Syntax Errors

```html id="syntaxbad"
<p>Hello
```

Missing closing tag → can break layout

---

## Tag Mismatch

```html id="tagbad"
<div>
  <p>Text</div>
</p>
```

Incorrect nesting

---

## CSS Cascading Issues

```css id="cascade1"
p {
  color: blue;
}

.text {
  color: red;
}
```

```html id="cascade2"
<p class="text">Hello</p>
```

Result: **RED**

---

### Why?

* CSS follows:

  * specificity
  * order

---

## Debugging Tips (Real Dev Workflow)

---

### 1. Use Browser DevTools

* Inspect element
* Check styles
* See overridden CSS

---

### 2. Check Layout Visually

```css id="debug1"
* {
  outline: 1px solid red;
}
```

Shows all element boundaries

---

### 3. Isolate the Problem

Remove code step-by-step until bug disappears

---

### 4. Validate HTML

Use tools like:

* W3C Validator

---

# Common Mistakes

These are VERY common:

- No alt text

- Poor contrast

- Inline styles everywhere

- Broken nesting

- Ignoring mobile + zoom

