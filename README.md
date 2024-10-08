[![npm version](https://img.shields.io/npm/v/solid-textarea-autosize.svg)](https://www.npmjs.com/package/solid-textarea-autosize)
[![npm](https://img.shields.io/npm/dm/solid-textarea-autosize.svg)](https://www.npmjs.com/package/solid-textarea-autosize)

# solid-textarea-autosize

A port of [react-textarea-autosize](https://github.com/Andarist/react-textarea-autosize)

Drop-in replacement for the textarea component which automatically resizes
textarea as content changes. A native solid version of the popular
[jQuery Autosize](http://www.jacklmoore.com/autosize/)! Weighs
around <span class="weight">1.3KB</span> (minified & gzipped).

This module supports IE9 and above.

```javascript
import TextareaAutosize from "solid-textarea-autosize";

// If you use CommonJS syntax:
// var TextareaAutosize = require('solid-textarea-autosize').default;

render(
  () => (
    <div>
      <TextareaAutosize />
    </div>
  ),
  document.getElementById("element"),
);
```

## Install

`npm install solid-textarea-autosize`

## Demo

https://bigmistqke.github.io/solid-textarea-autosize/

## Props

### Special props:

| prop                | type      | description                                                                                                                                                                                                                                        |
| ------------------- | --------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `maxRows`           | `number`  | Maximum number of rows up to which the textarea can grow                                                                                                                                                                                           |
| `minRows`           | `number`  | Minimum number of rows to show for textarea                                                                                                                                                                                                        |
| `onHeightChange`    | `func`    | Function invoked on textarea height change, with height as first argument. The second function argument is an object containing additional information that might be useful for custom behaviors. Current options include `{ rowHeight: number }`. |
| `cacheMeasurements` | `boolean` | Reuse previously computed measurements when computing height of textarea. Default: `false`                                                                                                                                                         |

Apart from these, the component accepts all props that are accepted by `<textarea/>`, like `style`, `onChange`, `value`, etc, with the exception of textarea's `row`-attribute and the style-properties `height`, `min-height` and `max-height`.

## FAQ

### How to focus

Get a ref to inner textarea:

```js
<TextareaAutosize ref={(tag) => (textarea = tag)} />
```

And then call a focus on that ref:

```js
this.textarea.focus();
```

To autofocus:

```js
<TextareaAutosize autoFocus />
```

(all HTML attributes are passed to inner textarea)
