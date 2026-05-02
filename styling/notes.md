# 5.1 Positioning Content (Layout Control)

This is how you control **where elements live on the page**.

---

## The Box Model

Every element is a box:

```css
/* visual layers */
content → padding → border → margin
```

```css id="box1"
div {
	width: 200px;
	padding: 20px;
	border: 5px solid black;
	margin: 10px;
}
```

### How it works:

- `content` → actual text/image
- `padding` → space inside
- `border` → outline
- `margin` → space outside

Note:
If your layout looks “off”, **90% of the time it’s box model issues.**

---

## Display (Block vs Inline)

```css id="display1"
div {
	display: block;
}
span {
	display: inline;
}
```

### Key difference:

| Type   | Behavior           |
| ------ | ------------------ |
| block  | full width         |
| inline | only content width |

---

## Position Property

---

### 1. `static` (default)

```css id="pos1"
div {
	position: static;
}
```

Normal flow (no control)

---

### 2. `relative`

```css id="pos2"
div {
	position: relative;
	top: 10px;
	left: 20px;
}
```

Moves **relative to itself**

---

### 3. `absolute`

```css id="pos3"
div {
	position: absolute;
	top: 0;
	right: 0;
}
```

Positioned relative to **nearest positioned parent**

Important:
Parent must have `position: relative`

---

### 4. `fixed`

```css id="pos4"
div {
	position: fixed;
	top: 0;
}
```

Stays fixed on screen (like navbars)

---

## Float (Old Layout System)

```css id="float1"
img {
	float: left;
}
```

👉 Text wraps around element

Note:
Avoid float for layout → use Flexbox/Grid instead

---

## Size & Overflow

```css id="size1"
div {
	width: 300px;
	height: 200px;
	max-width: 100%;
	overflow: hidden;
}
```

- `overflow: hidden | scroll | auto`

---

## Visibility

```css id="vis1"
div {
	visibility: hidden;
}
```

- `hidden` → invisible but takes space
- `display: none` → removed completely

---

# 5.2 Text Formatting

This is about **readability and design polish**.

---

## Fonts

```css id="font1"
p {
	font-family: Arial, sans-serif;
	font-size: 16px;
	font-weight: bold;
	font-style: italic;
}
```

---

## Colors & Text

```css id="text1"
p {
	color: #333;
	text-align: center;
	text-decoration: underline;
}
```

---

## Link Styling

```css id="link1"
a {
	color: blue;
}

a:hover {
	color: red;
}
```

---

## Spacing

```css id="text2"
p {
	line-height: 1.6;
	letter-spacing: 2px;
	text-indent: 20px;
}
```

---

## Wrapping Text

```css id="wrap1"
p {
	word-wrap: break-word;
}
```

Prevents overflow

---

Note:
Good typography = **professional UI instantly**

---

# 5.3 Backgrounds & Borders

---

## Borders

```css id="border1"
div {
	border: 2px solid black;
}
```

Breakdown:

```css
border-width: 2px;
border-style: solid;
border-color: black;
```

---

## Backgrounds

```css id="bg1"
div {
	background-color: lightblue;
}
```

---

## Background Image

```css id="bg2"
div {
	background-image: url("bg.jpg");
	background-size: cover;
	background-repeat: no-repeat;
	background-position: center;
}
```

---

Note:
`background-size: cover` is used in almost every modern UI

---

# 5.4 Responsive Layout (CRITICAL SKILL)

This is what makes your site work on **phones, tablets, desktops**.

---

## Units

---

### Absolute

```css
width: 300px;
```

Fixed size

---

### Relative

```css id="units1"
width: 50%;
font-size: 2em;
width: 100vw;
height: 100vh;
```

| Unit | Meaning               |
| ---- | --------------------- |
| %    | relative to parent    |
| em   | relative to font size |
| vw   | viewport width        |
| vh   | viewport height       |

---

Note:
Use `%`, `vw`, `vh` for responsive layouts

---

## Media Queries

```css id="media1"
@media (max-width: 768px) {
	body {
		background-color: lightgray;
	}
}
```

---

### How it works:

- Applies CSS when condition is true
- Used for breakpoints

---

## Breakpoints Example

```css id="media2"
/* Mobile */
@media (max-width: 600px) {
}

/* Tablet */
@media (max-width: 768px) {
}

/* Desktop */
@media (min-width: 1024px) {
}
```

---

## Simple Responsive Layout

```css id="layout1"
.container {
	display: flex;
	flex-wrap: wrap;
}

.box {
	width: 50%;
}

@media (max-width: 600px) {
	.box {
		width: 100%;
	}
}
```

---

### What happens:

- Desktop → 2 columns
- Mobile → 1 column

---

## Grid (Modern Layout)

```css id="grid1"
.container {
	display: grid;
	grid-template-columns: 1fr 1fr;
}
```

Note:
Learn Flexbox + Grid → you’ll rarely struggle with layout again

---

# Common Mistakes

Quiel, watch these carefully:

---

## Using px everywhere

Not responsive

---

## Overusing absolute positioning

Breaks layouts

---

## Forgetting box model

Causes overflow bugs

---

## Not testing on mobile

Huge beginner mistake
