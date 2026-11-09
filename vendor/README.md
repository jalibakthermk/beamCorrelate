# Vendored libraries

`plotly.min.js` is [Plotly.js](https://github.com/plotly/plotly.js) v2.35.2 (MIT License, © Plotly, Inc.), taken from the `dist/` folder of the v2.35.2 release. Raw control characters inside its string literals are written as `\uXXXX` / `\x1b` escapes; the code is otherwise unchanged.

`index.html` loads this copy first so the tool works offline and on networks that block public CDNs. If the file is missing it falls back to cdnjs, then jsDelivr.
