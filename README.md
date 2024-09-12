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
- `<wbr>` tag: word break / line break opportunity https://developer.mozilla.org/en-US/docs/Web/HTML/Element/wbr
  - `&shy;` is like `<wbr>` except it shows a hyphen when needed
- SVG commands M, L, and A (Q is harder to intuit): https://codepen.io/hchiam/pen/dywwRQE?editors=1000
- SVG `<animateMotion>`: https://codepen.io/hchiam/pen/QWoqqze
- `<base>` tag:
  - `<base href="https://some.base.url.to.shorten.the.rest/" target="_blank">`
  - `<base target="_blank">` to make all open in new tab https://www.w3schools.com/tags/tag_base.asp
  - `data:` or `javascript:` URLs aren't supposed to be allowed in base, but Firefox doesn't support this https://developer.mozilla.org/en-US/docs/Web/HTML/Element/base#browser_compatibility

- when to use `loading="lazy"` vs `fetchpriority="low"` vs `fetchpriority="high"`
  - `loading` = **_when_** to fetch (whether to wait until **_above the fold_**)
  - `fetchpriority` = **_how_** to fetch (whether to (de-)**_prioritize_** load)
  - https://www.youtube.com/watch?v=3rAf_Yx7R_g
    - use `fetchpriority="high"` for one important image on page load, for example.
    - use `loading="lazy"` to load offscreen images or offscreen iframes only if/when they're in the viewport (above the fold).
    - use `fetchpriority="low"` for images that are technically in the viewport (above the fold) but are visually hidden from the user, like most of the images in a carousel that's already above the fold, for example.
  - aside:
    - `loading` has good support https://caniuse.com/?search=loading
    - `fetchpriority` has not as good support https://caniuse.com/?search=fetchpriority

- `<video>`
  - https://web.dev/patterns/web-vitals-patterns/video/video?hl=en#html
    - ```html
      <!-- poster is like youtube video thumbnail image: -->
      <video controls width="960" height="540" poster="flower-960-poster.png">
        <source src="flower-960.mp4" type="video/mp4">
      </video>
      ```
  - https://web.dev/patterns/web-vitals-patterns/video/video-gif?hl=en
    - ```html
      <!-- loop makes the mp4 video behave like a gif: -->
      <video controls autoplay loop muted playsinline width="320" height="240">
        <source src="dog.mp4" type="video/mp4">
      </video>
      ```

- space characters: `' '` and `&nbsp;` but did you know about `&puncsp;` (`'\u2008'`) which takes up space but is able to wrap? there's even more Unicode characters: https://stackoverflow.com/questions/8515365/are-there-other-whitespace-codes-like-nbsp-for-half-spaces-em-spaces-en-space

- HTML symbols / HTML entities: `&harr;` (↔) vs `&hArr;` (⇔) - capitalization matters! https://codepen.io/hchiam/pen/XWLyYZX
  - https://www.w3schools.com/html/html_entities.asp
  - https://www.w3schools.com/html/html_symbols.asp

- SVG arrows: https://codepen.io/hchiam/pen/vYqQWdM?editors=1000

- to make a date input have a placeholder text (when not filled completely): https://codepen.io/hchiam/pen/dyBLWao
