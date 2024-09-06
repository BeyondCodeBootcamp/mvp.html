# mvp.html

Boilerplate for simple demo apps, based on mvp.css

## DOM Secrets

### `classList`

`classList` is a set of CSS classes.

```js
document.body.classList.add("active");
document.body.classList.remove("active");
```

- <https://caniuse.com/classlist>
- <https://developer.mozilla.org/en-US/docs/Web/API/Element/classList>

### Native Combo Box

The built-in combo box can source from a static or dynamically-created list.

```html
<input type="text" name="fruit" list="fruit-list" />
<datalist id="fruit-list">
  <option value="apple">Apple</option>
  <option value="banana">Banana</option>
  <option value="orange">Orange</option>
</datalist>
```

- <https://caniuse.com/datalist>
- <https://developer.mozilla.org/en-US/docs/Web/HTML/Element/datalist>

### Native Collapsible Details

You can create collapsible menus or trees with details.

```html
<details>
  <summary>Debug Info</summary>
  This info is hidden until revealed by clicking the arrow.
</details>
```

```html
<details name="beefy" open>
  <summary>Ham</summary>
  Made from the pig.
</details>
<details name="beefy">
  <summary>Burger</summary>
  Made from the cow.
</details>
<details>
  <summary>Hotdog</summary>
  Made from... something.
</details>
```

- <https://caniuse.com/details>
- <https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details>

### Native Definition Lists

There are native dictionary-style definition lists.

```html
<dl>
  <dt>Hogwarts</dt>
  <dd>A school for wizards.</dd>

  <dt>Gryffindor</dt>
  <dd>
    A house for the brave ones. They get 10 points almost every time. Except for
    when they don't.
  </dd>

  <dt>Hufflepuff</dt>
  <dd>A house for the delicate ones.</dd>

  <dt>Ravenclaw</dt>
  <dd>A house for the smart ones.</dd>

  <dt>Slytherin</dt>
  <dd>A house for the cunning ones.</dd>
</dl>
```

- <https://caniuse.com/mdn-html_elements_dl>
- <https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dl>

### Native Hi-Resolution Images

You can use either `<picture>` or `srcset=` to load multiple images.

```html
<picture>
  <source srcset="logo-2x.png" media="(min-width: 800px)" />
  <source srcset="logo-1x.png" media="(max-width: 799px)" />
  <img src="logo-default.png" alt="The ACME Logo" />
</picture>
```

```html
<img
  srcset="logo-1x.png 1x, logo-2x.png 2x"
  sizes="(max-width: 600px) 100vw, 50vw"
  src="logo-default.png"
  alt="The ACME Logo"
/>
```

- <https://caniuse.com/picture>
- <https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture>

### Native Modal Dialogs

The browser has a built-in modal dialog.

```html
<dialog onclick="document.querySelector('dialog').close();">
  Woo-hoo! That tickles!
</dialog>
<button onclick="document.querySelector('dialog').show();">Click me</button>
```

- <https://caniuse.com/dialog>
- <https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog>

### Native Templates

You can use HTML Templates to efficiently rewrite or add contents in JavaScript.

```html
<div>
  <template>
    <div>A place for document fragments and shadow DOM</div>
  </template>
</div>
```

- <https://developer.mozilla.org/en-US/docs/Web/API/Node/cloneNode>
- <https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment>
- <https://developer.mozilla.org/en-US/docs/Web/HTML/Element/template>

### Native CSS Selection

The browser has a built-in, efficient css selector that can be used instead of
`getElementById()` and similar.

```js
let $dialog = document.querySelector(
  'section.active dialog[data-name="popup"]',
);
$dialog.show();
```

```js
let nodeList = document.querySelectorAll("dialog");
let $dialogs = Array.from(nodeList);
```

```js
document.querySelector("dialog").querySelector("button");
```

- <https://caniuse.com/mdn-api_element_queryselectorall>
- <https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelector>
- <https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelectorAll>

### Native Change Batching

Requesting to batch DOM manipulations in an animation frame via
`requestAnimationFrame(fn)` can prevent unwanted redraws and boost performance.

```js
requestAnimationFrame(function () {
  document.body.classList.add("ready");
});
```

- <https://caniuse.com/requestanimationframe>
- <https://developer.mozilla.org/en-US/docs/Web/API/Window/requestAnimationFrame>

### `insertAdjacentHTML()`

String-building HTML and inserting adjacent to an element can be very efficient.
\
(`beforebegin`, `afterbegin`, `beforeend`, 'afterend')

```html
<!-- beforebegin -->
<p>
  <!-- afterbegin -->
  foo
  <!-- beforeend -->
</p>
<!-- afterend -->
```

- <https://caniuse.com/insertadjacenthtml>
- <https://developer.mozilla.org/en-US/docs/Web/API/Element/insertAdjacentHTML>

### `textContent`

`textContent` is an efficient replacement for `innerText`.

```js
document.body.textContent = "Hello, World!";
```

- <https://caniuse.com/textcontent>
- <https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent>
