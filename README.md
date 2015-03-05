# autoresize-textarea

A [jQuery] plugin can automatically resize the textarea's height.

## Usage

HTML:

```html
<textarea id="description"></textarea>
```

CSS:

```css
#description {
  padding: 3px;
  height: 24px;
  font-size: 16px;
  line-height: 24px;
  overflow: hidden;
  resize: none;
}
```

In most cases, it will be as a jQuery plugin.

```js
$('#description').autoResize();
```

But, if there isn't the jQuery object on global object, it will expose an `autoResize()` method to global object.

```js
autoResize( document.getElementById('description') );
```

And, this plugin can be used as a CommonJS/AMD module. You can see the demos in `example` folder for more details.

## Package

You can use [npm](https://docs.npmjs.com) or [bower](http://bower.io) to install it.

**NPM:**

```bash
npm install autoresize-textarea
```

**Bower:**

```bash
bower install autoresize-textarea
```

## Options

You can pass an configurable object as the first parameter. If you passed a function as the first parameter, it will be treated as `callback` option.

- **maxHeight**

  Type: `Number` Default: `undefined`

  When the height of textarea is greater than `maxHeight`, the `maxHeight` will be as the height, and the `overflow-y` will be set to `auto`.

- **callback**

  Type: `Function` Default: `undefined`

  In callback function, `this` refer to the textarea element and the first argument is the current height of the textarea.

## Events

When the input event is fired, a named `autoresize:height` event will be triggered on textarea element and the current height of textarea will be passed as the second parameter of the event listener. This is valid as a jQuery plugin.

## Compatibility

Tested in IE6+ (including compatibility mode) and other modern browsers.

**Bugs:**

In IE7 (including compatibility mode), the content will jump up and down when you press enter key.

## Thanks to

- The [dottoro](help.dottoro.com) reference helps me get some key details about `scrollHeight` and `oninput`/`onpropertychange`/`onpaste` events.

- A Ben Alpert's article - [A near-perfect oninput shim for IE 8 and 9](http://benalpert.com/2013/06/18/a-near-perfect-oninput-shim-for-ie-8-and-9.html), makes me understand how to use the `onselectionchange` event.

- The [AutoResize](https://github.com/azoff/AutoResize) plugin commited in 2011 provides another solution. I refer to the part.

## License

Under the MIT license.
