# Learning HTML / HTML5:

Just one of the things I'm learning. <https://github.com/hchiam/learning>

<https://app.memrise.com/course/700032/learn-html>

## HTML tags you might not know about

<https://www.youtube.com/shorts/nIcxzmiVFJg>

<https://www.w3schools.com/tags/att_a_download.asp>

```html
<!-- the download attribute makes it download instead, and you an set the custom file name with download="custom.name" -->
<a href="some/path/to/some/filename.whatever" download>
```

<https://www.w3schools.com/html/tryit.asp?filename=tryhtml_elem_datalist>

```html
<input list="browsers"> <!-- input will autocomplete suggestions from the datalist options (not forced) -->
<datalist id="browsers">
  <option value="Internet Explorer">
  <option value="Firefox">
  <option value="Chrome">
  <option value="Opera">
  <option value="Safari">
</datalist>
```

<https://www.w3schools.com/tags/tryit.asp?filename=tryhtml_areamap>

<https://www.w3schools.com/tags/tryit.asp?filename=tryhtml_abbr_test>

<https://www.w3schools.com/tags/tryit.asp?filename=tryhtml5_template2>

<https://www.w3schools.com/tags/tryit.asp?filename=tryhtml5_template3>

## not-well-known HTML attributes

<https://www.smashingmagazine.com/2022/03/html-attributes-you-never-use>

## Miscellaneous notes

- stuff you can do without JS-heavy web frameworks: https://codepen.io/hchiam/pen/ExbmjEP

- difference between attributes and properties: https://stackoverflow.com/questions/6003819/what-is-the-difference-between-properties-and-attributes-in-html/6004028#6004028

- <https://www.youtube.com/watch?v=X_ek1wSe66o>
  - HTML5 can do things you might not expect!
  - HTML can do "poor man's" one-way data binding with attributes + CSS + JS
    - model values = `data-*` attributes
    - read values = `attr()` (only returns strings though! so can't set color etc.)
    - `:before`/`:after` can generate markup
    - <https://codepen.io/hchiam/pen/VwKMddY>
  - HTML can also do one-way binding with `<datalist>` for things like auto-complete
    - <https://codepen.io/hchiam/pen/VwKMddY>
  - HTML can access filesystem
    - `window.requestFileSystem()`
    - security: sandbox per origin = can't read/write someone else's app/device
    - benefit: web apps can access files like native apps = more dynamic storage!
    - <https://github.com/ebidel/filer.js>
    - support "all" browsers w/ shim: <https://github.com/ebidel/idb.filesystem.js>
  - HTML can do client-side downloading
    - `<a download="filename.png">`
      - instead of Content-Disposition: attachment; filename="myfile.png" to navigate to a file and trick the browser to download the file (this only works if you app involves a server to begin with)
  - more: <https://github.com/ebidel/html5can>
- <https://3perf.com/blog/link-rels/>
  - preload, prefetch, etc. in `<link>` tags:
    - [preload](https://3perf.com/blog/link-rels/#preload) – when need resource ASAP, in a few seconds
      - `<link rel="preload" href="/style.css" as="style" />`
    - [prefetch](https://3perf.com/blog/link-rels/#prefetch) – when need resource for next page
      - `<link rel="prefetch" href="/style.css" as="style" />`
    - [preconnect](https://3perf.com/blog/link-rels/#preconnect) – when need resource soon, but don’t know full url yet
      - `<link rel="preconnect" href="https://example.com" />`
      - (or [dns-prefetch](https://3perf.com/blog/link-rels/#dns-prefetch) for older browsers): `<link rel="dns-prefetch" href="https://example.com" />`
    - [prerender](https://3perf.com/blog/link-rels/#prerender) – when most users navigate to specific page, and you want speed up
      - `<link rel="prerender" href="https://example.com/about.html" />`
    - [modulepreload](https://3perf.com/blog/link-rels/#modulepreload) – when need ES module script ASAP
      - `<link rel="modulepreload" href="/script.js" />`
- <https://www.linkedin.com/learning/html-essential-training-4/debugging-html>
  - debugging HTML? open browser developer tools!
- <https://www.linkedin.com/learning/html-essential-training-4/aria-roles>
  - <https://cdpn.io/jensimmons/debug/wvwjxJa>
  - Firefox dev tools > Accessibility tab > (expand to see things in the accessibility tree)
