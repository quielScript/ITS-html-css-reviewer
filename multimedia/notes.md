# 4.1 Displaying Images (img & picture)

Images are simple on the surface, but **a lot is happening under the hood**.

---

## 1. `<img>` — The Basics

```html id="img1"
<img src="profile.jpg" alt="Profile picture">
```

---

## Core Attributes

```html id="img2"
<img 
  src="profile.jpg" 
  alt="Profile picture of Quiel" 
  width="200" 
  height="200"
>
```

### What each does:

* `src` → image path
* `alt` → **VERY IMPORTANT**

  * used for accessibility
  * shown if image fails to load
* `width` / `height` → controls size

---

## Why `alt` Matters

```html id="img3"
<img src="logo.png" alt="Company logo">
```

Without `alt`:

* Screen readers fail
* SEO is worse
* Accessibility score drops

Note:
Treat `alt` as required, not optional

---

## How the Browser Loads Images (Important)

1. Parses HTML
2. Finds `<img>`
3. Requests file from server
4. Renders when loaded

This is why images can **slow your page**

---

## 2. `<picture>` — Responsive Images

Used when you want **different images for different screens**

```html id="pic1"
<picture>
  <source media="(max-width: 600px)" srcset="small.jpg">
  <source media="(max-width: 1200px)" srcset="medium.jpg">
  <img src="large.jpg" alt="Responsive image">
</picture>
```

---

## How it works:

* Browser checks conditions
* Picks the best image
* Falls back to `<img>` if needed

---

Note:
Use `<picture>` for:

* performance optimization
* responsive design
* modern apps

---

# 4.2 Video & Audio

Now we move to **media playback**.

---

## 1. `<video>`

```html id="video1"
<video src="video.mp4" controls></video>
```

---

## Important Attributes

```html id="video2"
<video width="400" controls autoplay muted loop>
  <source src="video.mp4" type="video/mp4">
</video>
```

### What these do:

* `controls` → play/pause UI
* `autoplay` → starts automatically
* `muted` → required for autoplay in browsers
* `loop` → repeats video

---

## Multiple Formats (Best Practice)

```html id="video3"
<video controls>
  <source src="video.mp4" type="video/mp4">
  <source src="video.webm" type="video/webm">
</video>
```

Browser chooses supported format

---

## 2. `<audio>`

```html id="audio1"
<audio controls>
  <source src="audio.mp3" type="audio/mpeg">
</audio>
```

---

### Same idea as video:

* supports multiple formats
* uses `controls`

---

## 3. `<track>` — Subtitles / Captions

```html id="track1"
<video controls>
  <source src="video.mp4" type="video/mp4">
  <track src="subtitles.vtt" kind="subtitles" srclang="en" label="English">
</video>
```

---

### Why this matters:

* Accessibility (hearing impaired)
* Better UX
* Professional apps REQUIRE this

---

## 4. `<iframe>` — Embedding External Content

Used to embed content from other websites (like YouTube)

```html id="iframe1"
<iframe 
  width="560" 
  height="315" 
  src="https://www.youtube.com/embed/VIDEO_ID"
  allowfullscreen>
</iframe>
```

---

## How it works:

* Loads another webpage inside your page
* Common for:

  * YouTube videos
  * Google Maps
  * external widgets

---

Note:
Prefer `<iframe>` for platforms like YouTube
Don’t host large videos yourself unless needed (performance cost)

---

# Real Combined Example

```html id="combinedMedia1"
<h2>My Portfolio</h2>

<img src="profile.jpg" alt="Profile picture of Quiel" width="150">

<picture>
  <source media="(max-width: 600px)" srcset="mobile.jpg">
  <img src="desktop.jpg" alt="Banner image">
</picture>

<video controls width="400">
  <source src="intro.mp4" type="video/mp4">
</video>

<audio controls>
  <source src="music.mp3" type="audio/mpeg">
</audio>

<iframe 
  width="400" 
  height="250"
  src="https://www.youtube.com/embed/VIDEO_ID">
</iframe>
```

---

# Common Beginner Mistakes

Avoid these:

---

## Missing alt

```html
<img src="image.jpg">
```

---

## Using huge images (performance killer)

Always optimize images

---

## Autoplay without muted

```html
<video autoplay></video> <!-- may not work -->
```

---

## Not using multiple formats

Some browsers won’t play certain formats
