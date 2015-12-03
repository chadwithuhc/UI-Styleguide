# Base CSS

We use a `reset.css` file with a few additions of our own. Please copy this into all new projects:

```css
html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, embed, 
figure, figcaption, footer, header, hgroup, 
menu, nav, output, ruby, section, summary,
time, mark, audio, video {
    margin:0;
    padding:0;
    border:0;
    outline:0;
    font-size:100%;
    vertical-align:baseline;
    background:transparent;
}

/* HTML5 display-role reset for older browsers */
article, aside, details, figcaption, figure, 
footer, header, hgroup, menu, nav, section {
    display: block;
}

ul {
    list-style:none;
    margin:0;
    padding:0;
}

li {
    margin:0;
    padding:0;
}

blockquote, q {
    quotes:none;
}

blockquote:before, blockquote:after,
q:before, q:after {
    content:'';
    content:none;
}

table {
    border-collapse:collapse;
    border-spacing:0;
}

abbr[title], dfn[title] {
    border-bottom:1px dotted;
    cursor:help;
}

hr {
    display:block;
    height:1px;
    border:0;
    border-top:1px solid #eee;
    margin:1em 0;
    padding:0;
    clear:both;
}

input, select {
    vertical-align:middle;
}

*, *:before, *:after {
    -moz-box-sizing: border-box;
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
}

.clearfix:after, .clearfix:before {
    clear: both;
    float: none;
    visibility: hidden;
    display: table;
    font-size: 0;
    content:" ";
    clear: both;
    height: 0;
}

.clearfix {
    zoom: 1;
}
```

## Benefits & Changes

- Resets all common elements to only block or inline styling
- Everything is set to use `border-box` instead
- Adds `clearfix` for use in project
- `ul` and `li` lose their list style and margin / padding (`ol` keeps numbers)
- `blockquote` and `q` remove quotes
- `abbr` or `dfn` are only styled when a `title` attribute is included
- `input` and `select` are vertically aligned in the middle
- Reset `hr` to be consistent
