# 3.1 Structuring Content & Organizing Data

This is about **layout + meaning using basic tags**.

---

## Headings (`h1` → `h6`)

```html
<h1>Main Title</h1>
<h2>Section Title</h2>
<h3>Subsection</h3>
```

### Key idea:

* `h1` = most important
* `h6` = least important

Note:
Use **only ONE `<h1>` per page** for SEO + structure.

---

## Paragraph, Line Break, Horizontal Line

```html
<p>This is a paragraph.</p>
<br>
<hr>
```

* `<p>` → text block
* `<br>` → line break (no closing tag)
* `<hr>` → horizontal divider

---

## div vs span (VERY IMPORTANT)

```html
<div>This is block</div>
<span>This is inline</span>
```

### Difference:

| Tag    | Behavior                 |
| ------ | ------------------------ |
| `div`  | Block (takes full width) |
| `span` | Inline (fits content)    |

Note:

* Use `div` for layout
* Use `span` for small text styling

---

## Lists

### Unordered List

```html
<ul>
  <li>Apple</li>
  <li>Banana</li>
</ul>
```

### Ordered List

```html
<ol>
  <li>Step 1</li>
  <li>Step 2</li>
</ol>
```

---

## Tables (Structured Data)

```html
<table border="1">
  <tr>
    <th>Name</th>
    <th>Age</th>
  </tr>
  <tr>
    <td>Quiel</td>
    <td>20</td>
  </tr>
</table>
```

### Breakdown:

* `<table>` → container
* `<tr>` → row
* `<th>` → header cell
* `<td>` → data cell

Note:
Tables are ONLY for data, not layout (old-school mistake)

---

# 3.2 HTML5 Semantic Elements

Now we move from **generic (`div`) → meaningful structure**.

---

## Semantic Layout Example

```html
<header>
  <h1>My Website</h1>
</header>

<nav>
  <a href="#">Home</a>
  <a href="#">About</a>
</nav>

<section>
  <article>
    <h2>Blog Title</h2>
    <p>Content here...</p>
  </article>
</section>

<aside>
  <p>Sidebar content</p>
</aside>

<footer>
  <p>© 2026</p>
</footer>
```

---

## Key Tags Explained

* `<header>` → top section
* `<nav>` → navigation links
* `<section>` → grouping content
* `<article>` → independent content (blog, post)
* `<aside>` → sidebar
* `<footer>` → bottom section

---

## Extra Semantic Tags

```html
<figure>
  <img src="image.jpg">
  <figcaption>Profile picture</figcaption>
</figure>
```

```html
<details>
  <summary>Click me</summary>
  <p>Hidden content</p>
</details>
```

Note:
Semantic HTML = **better SEO + accessibility + cleaner code**

---

# 3.3 Navigation (Links & Routing Basics)

This is how users move through your app.

---

## Anchor Tag

```html
<a href="about.html">Go to About</a>
```

---

## Target Attribute

```html
<a href="https://google.com" target="_blank">Open Google</a>
```

* `_blank` → new tab
* `_self` → same tab (default)

---

## Bookmark (Jump Links)

```html
<a href="#section1">Go to Section</a>

<h2 id="section1">Section 1</h2>
```

Works like scrolling navigation

---

## Relative vs Absolute Links

### Absolute

```html
<a href="https://example.com">Visit</a>
```

### Relative

```html
<a href="about.html">About</a>
<a href="../index.html">Back</a>
```

### Folder Example:

```
project/
 ├── index.html
 └── pages/
     └── about.html
```

From `about.html` → go to index:

```html
<a href="../index.html">Home</a>
```

---

## Image Map (Clickable Areas)

```html
<img src="map.jpg" usemap="#map">

<map name="map">
  <area shape="rect" coords="0,0,100,100" href="page.html">
</map>
```

Note:
Rarely used today, but still part of fundamentals

---

# 3.4 Forms (User Input System)

This is HUGE in real apps (login, signup, checkout).

---

## Basic Form Structure

```html
<form action="/submit" method="POST">
  <input type="text" name="username">
  <button type="submit">Submit</button>
</form>
```

---

## Form Attributes

* `action` → where data is sent
* `method` → how data is sent

### Methods:

| Method | Use        |
| ------ | ---------- |
| GET    | Fetch data |
| POST   | Send data  |

---

## Input Types

```html
<input type="text">
<input type="email">
<input type="password">
<input type="number">
<input type="date">
```

---

## Input Restrictions

```html
<input type="text" required minlength="3" maxlength="10">
<input type="number" min="1" max="100">
```

---

## Other Form Elements

### Select Dropdown

```html
<select>
  <option value="1">Option 1</option>
  <option value="2">Option 2</option>
</select>
```

---

### Textarea

```html
<textarea rows="4" cols="30"></textarea>
```

---

### Label (IMPORTANT)

```html
<label for="username">Username:</label>
<input id="username" type="text">
```

### Why label matters:

* Accessibility
* Clicking label focuses input

---

## Full Example (Realistic Form)

```html
<form action="/register" method="POST">

  <label for="name">Name:</label>
  <input id="name" type="text" required>

  <label for="email">Email:</label>
  <input id="email" type="email" required>

  <label for="role">Role:</label>
  <select id="role">
    <option>User</option>
    <option>Admin</option>
  </select>

  <textarea placeholder="Your message"></textarea>

  <button type="submit">Register</button>

</form>
```

---

# Common Mistakes (Watch these, Quiel)

* Using `<div>` everywhere instead of semantic tags
* Using tables for layout
* Forgetting `label` in forms
* Wrong relative paths (`../` mistakes)
* Not using `name` attribute (important for backend)

