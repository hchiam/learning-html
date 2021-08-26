# Learning HTML / HTML5:

Just one of the things I'm learning. <https://github.com/hchiam/learning>

## HTML tags you might not know about

<https://www.w3schools.com/tags/tryit.asp?filename=tryhtml_areamap>

<https://www.w3schools.com/tags/tryit.asp?filename=tryhtml_abbr_test>

<https://www.w3schools.com/tags/tryit.asp?filename=tryhtml5_template2>

<https://www.w3schools.com/tags/tryit.asp?filename=tryhtml5_template3>

## Miscellaneous notes

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
