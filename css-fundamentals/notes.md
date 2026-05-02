# 2.1 CSS Styles (Inline, Internal, External)

Think of CSS as **layers of styling power**.
Where you write your CSS affects **priority, maintainability, and scalability**.

---

## 1. Inline Styles

Applied directly inside HTML elements.

```html id="inline1"
<p style="color: red; font-size: 18px;">Hello World</p>
```

### How it works:

* CSS is written inside the `style` attribute
* Applies **only to that element**

### When to use:

* Quick testing
* JavaScript dynamic styling

### Why it’s bad in real projects:

* Hard to maintain
* Repeated code everywhere

Note:
Avoid this unless you *really* need it.

---

## 2. Internal (Embedded) Styles

CSS written inside `<style>` in the `<head>`.

```html id="internal1"
<head>
  <style>
    p {
      color: blue;
    }
  </style>
</head>
```

### How it works:

* Affects the whole page
* Good for small projects

### When to use:

* Single-page apps (simple ones)
* Prototyping

---

## 3. External Stylesheets (BEST PRACTICE)

```html id="external1"
<link rel="stylesheet" href="styles.css">
```

**styles.css:**

```css id="external2"
p {
  color: green;
}
```

### How it works:

* CSS is in a separate file
* Can be reused across pages

### Why this is the best:

* Clean code
* Scalable
* Industry standard

Note:
You should **default to this 95% of the time**.

---

# CSS Precedence (Who Wins?)

When multiple styles target the same element:

### Priority Order:

1. Inline styles
2. Internal styles
3. External styles
4. Browser default

---

## Example:

```html id="precedence1"
<head>
  <style>
    p {
      color: blue;
    }
  </style>
</head>

<body>
  <p style="color: red;">Hello</p>
</body>
```

Result: **RED**

Because:

* Inline > Internal

---

## Browser Default Styles

Browsers automatically apply styles.

Example:

```html id="browser1"
<h1>Title</h1>
```

Browser adds:

* big font
* bold

That’s why CSS resets exist (like `normalize.css`)

---

# 2.2 CSS Rule Sets (Core Syntax)

Every CSS you write follows this structure:

```css id="ruleset1"
selector {
  property: value;
}
```

---

## Example:

```css id="ruleset2"
p {
  color: blue;
  font-size: 16px;
}
```

### Breakdown:

* `p` → selector
* `color` → property
* `blue` → value

---

# Selectors (VERY IMPORTANT)

Selectors decide **what gets styled**.

---

## 1. Element Selector

```css id="selector1"
p {
  color: red;
}
```

Targets all `<p>` tags

---

## 2. Class Selector (`.`)

```html id="selector2html"
<p class="text">Hello</p>
```

```css id="selector2css"
.text {
  color: blue;
}
```

Reusable → most common in real projects

---

## 3. ID Selector (`#`)

```html id="selector3html"
<p id="title">Hello</p>
```

```css id="selector3css"
#title {
  color: green;
}
```

Should be unique

Note:

* Avoid overusing IDs for styling
* Use classes instead (more flexible)

---

## 4. Descendant Selector (Space)

```css id="selector4"
div p {
  color: purple;
}
```

Targets:

* `<p>` inside `<div>`

---

## 5. Pseudo-class Selector (`:`)

Used for states.

```css id="selector5"
a:hover {
  color: orange;
}
```

When user hovers → color changes

---

# Combined Example

```html id="combined1"
<div class="container">
  <p class="text">Hello Quiel</p>
</div>
```

```css id="combined2"
.container p {
  color: blue;
}

.text:hover {
  color: red;
}
```

### What happens step-by-step:

1. `<p>` inside `.container` → blue
2. Hover → turns red

---

# Common Beginner Mistakes

Watch out for these:

---

## Missing semicolon

```css id="mistake1"
p {
  color: red
  font-size: 16px;
}
```

Breaks CSS parsing

---

## Wrong selector

```css id="mistake2"
#text { }  /* but HTML uses class="text" */
```

---

## Overusing inline styles

Leads to chaos in big projects