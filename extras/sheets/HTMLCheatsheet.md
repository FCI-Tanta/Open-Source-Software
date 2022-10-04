# HTML boilerplate

A simple HTML document should start by something like that: -

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>Page Title</title>
</head>

<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>

<script src="script.js"></script>

</body>

</html>
```

- The `<!DOCTYPE html>` declaration defines that this document is an HTML5 document
- The `<html>` element is the root element of an HTML page
- The `<head>` element contains metadata about the HTML page, such as title, name, description, ...
- The `<title>` element specifies a title for the HTML page (which is shown in the browser's title bar or in the page's
  tab)
- The `<body>` element defines the document's body, and is a container for all the visible contents, such as headings,
  paragraphs, images, hyperlinks, tables, lists, etc.
- The `<h1>` element defines a large heading
- The `<p>` element defines a paragraph
- The `<script>` element specifies some JavaScript code that must be implemented once the element is rendered

## HTML basics

- HTML elements:

```html 
<tagname></tagname>
<tagname>[content]</tagname>
<tagname attribute="value">[content]</tagname>
<tagname attribute1="value" attribute2="value2">[content]</tagname>
```

- HTML self-closing elements:

```html
<tagname />
```
