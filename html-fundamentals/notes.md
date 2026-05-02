
# 1.1 Metadata Elements (Head Section Mastery)

Think of the `<head>` as **the brain of your page**.
Users don’t see it directly, but browsers, search engines, and tools rely on it heavily.

---

## Core Metadata Tags

### 1. `<meta>` — Page Information

This tag gives **instructions and info about your page**.

### Example:

```html
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="Learn HTML fundamentals step by step">
<meta name="keywords" content="HTML, CSS, Web Development">
```

### Breakdown:

* `charset="UTF-8"`
  → Supports most characters (important for emojis, symbols, etc.)

* `viewport`
  → Controls responsive behavior on mobile

  ```html
  width=device-width → match screen width
  initial-scale=1.0 → no zoom
  ```

* `description`
  → Used by search engines (SEO)

* `keywords`
  → Mostly outdated for SEO, but still sometimes used

---

## 2. `<style>` — Internal CSS

Used when you want to write CSS inside your HTML.

```html
<style>
  body {
    background-color: #f4f4f4;
  }
</style>
```

Note:
Use this only for **small projects or quick demos**. Real projects → use external CSS.

---

## 3. `<link>` — External Resources

Most commonly used to link CSS files.

```html
<link rel="stylesheet" href="styles.css">
```

What’s happening:

* Browser fetches `styles.css`
* Applies styles to your page

---

## 4. `<script>` — JavaScript

Adds behavior to your page.

```html
<script src="app.js"></script>
```

OR inline:

```html
<script>
  console.log("Hello World");
</script>
```

Important detail:

* Scripts can **block rendering** if placed incorrectly

Best practice:

```html
<script src="app.js" defer></script>
```

* `defer` → runs after HTML loads (very important for performance)

---

## 5. `<noscript>` — Fallback

Used when JavaScript is disabled.

```html
<noscript>
  <p>Please enable JavaScript to use this app.</p>
</noscript>
```

Real-world use:

* Useful in apps that depend heavily on JS (like React apps)

---

# 1.2 Well-Formed HTML Structure

Now we move to the **skeleton of your page**.

---

## Basic HTML Template (You MUST memorize this)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>My Page</title>
</head>
<body>

  <h1>Hello, Quiel</h1>

</body>
</html>
```

---

## Breakdown (Step-by-step)

### 1. `<!DOCTYPE html>`

This tells the browser:

> “Use modern HTML5 rules”

If you forget this → browser may go into **quirks mode** (weird rendering bugs).

---

### 2. `<html>`

Root element of your page.

```html
<html lang="en">
```

* `lang="en"` → helps accessibility & SEO

---

### 3. `<head>`

Contains:

* metadata
* links
* scripts
* title

---

### 4. `<body>`

Everything visible goes here:

* text
* images
* buttons
* layout

---

# Proper Syntax Rules (VERY IMPORTANT)

These are beginner mistakes that cause bugs.

---

## Rule 1: Always Close Tags

```html
<p>This is correct</p>
```

Wrong:

```html
<p>This is wrong
```

---

## Rule 2: Proper Nesting

```html
<strong><em>Text</em></strong>
```

Wrong:

```html
<strong><em>Text</strong></em>
```

Think of it like stacking boxes.

---

## Rule 3: Use Quotes for Attributes

```html
<img src="image.jpg" alt="Profile">
```

---

## Rule 4: Self-closing Elements (Void Elements)

These don’t need closing tags:

```html
<img>
<br>
<hr>
<meta>
<link>
```

---

## Common Symbols You Must Know

These are called **HTML entities**.

```html
&lt;  → <
&gt;  → >
&amp; → &
&nbsp; → space
```

### Example:

```html
<p>5 &lt; 10</p>
```

---

# Real Example (Putting Everything Together)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="description" content="Basic HTML page">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>HTML Fundamentals</title>

  <link rel="stylesheet" href="styles.css">

  <style>
    h1 {
      color: blue;
    }
  </style>

  <script defer src="app.js"></script>
</head>

<body>

  <h1>Hello, Quiel</h1>
  <p>This is a well-structured HTML page.</p>

  <noscript>
    <p>JavaScript is required for full functionality.</p>
  </noscript>

</body>
</html>
```
