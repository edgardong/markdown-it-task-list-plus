# markdown-it-task-list-plus

A [markdown-it](https://www.npmjs.com/package/markdown-it) plugin to create GitHub-style [task lists](https://github.com/blog/1825-task-lists-in-all-markdown-documents)

[![Greenkeeper badge](https://badges.greenkeeper.io/edgardong/markdown-it-task-list-plus.svg)](https://greenkeeper.io/)

## What it does

- Builds [task/todo lists](https://github.com/blog/1825-task-lists-in-all-markdown-documents) out of markdown lists with items starting with `[ ]` or `[x]`.
- Nothing else

### Why is this useful?

When you have markdown documentation with checklists, rendering HTML checkboxes
out of the list items looks nicer than the raw square brackets.

## Installation

```sh
npm install markdown-it-task-list-plus
```

## Usage

Use it the same as a normal markdown-it plugin:

```js
var md = require('markdown-it')
var taskListPlus = require('markdown-it-task-list-plus')

var parser = md().use(taskListPlus)

var result = parser.render(...) // markdown string containing task list items
```

The rendered checkboxes are disabled; to change this, pass a truthy value into
the `enabled` property of the plugin options:

```js
var parser = md().use(taskLists, {enabled: true})
```

If you'd like to wrap the rendered list items in a `<label>` element for UX
purposes, pass a truthy value to the `label` property of the plugin options:

```js
var parser = md().use(taskLists, {label: true})
```

To add the label after the checkbox pass a truthy value to `labelAfter` property:

```js
var parser = md().use(taskLists, {label: true, labelAfter: true})
```

**Note:** This option does require the `label` option to be truthy.

The options can be combined, of course.

### Browser Usage

If you use one of the versions of this module available in `dist/` directly in
a browser by including it with a `<script>` element, it will be available
globally in `window.markdownitTaskLists`.

## Tests

```sh
npm install
npm test
```

## License

MIT
