# Simple javascript helper functions

Lightweight javascript helper functions to make life easier.

## Functions

### `getSetCookie('name', 99, days || null)`

Sets cookie, returns `string`.

To get, define key only, like `getSetCookie('name')`. Optional `days` should be type int.

### `createEl('div', 'foo' || '.foo' || '#foo')`

Returns `Node` element.

No `propName` is passed, defaults to element without class/id, like `<div class="foo"></div>`.

If `propName` is passed, defaults to  . `className` like `<div class="foo"></div>`

### `appendChild(parentEl, child || [child, child])`

Appends using `parent.appendChild()`

### `getEl('.foo', true)`

Returns `Node` element, array of `Node` elements, or `null`.

Get element matching selector, or get all elements matching selector.

### `getParent(referenceEl, '.foo' || '#foo', isTagName)`

Returns `Node` element.

Get first parent from `referenceEl`.

If `isTagName`, use tag name string, for second argument, like `getParent(referenceEl, 'li', true)`

### `getChild('.foo', true)`

Returns `Node` element.

Get child element matching selector, or get all child elements matching selector.

### `innerHtml(el, html)`

Sets `html`, returns `html`.

To get, define `el` only.

### `textContent(el, str)`

Sets `string`, returns `string`.

To get, define `el` only.

### `classHelper(el, 'a', 'active')`

Sets `className` using `classList`. Returns `boolean`.

Options are 'a' for `add`, 'c' for `contains`, 'r' for `remove`.

Accepts array of elements like `classHelper([el, el2], 'a', 'active')`.

### `imageSize(src, max)`

Update url to Shopify like `_900x900`.

### `priceTrim(price, options)`

Trim price for thousands and/or decimals.

Options are `divide100` and `trim`, which will trim decimals if whole integer, like `30.00` becomes `30`.

### `debounce(callback, wait)`

Debounce for event listeners like `scroll` or `resize`. This debounce function kills calls within the `wait` interval, instead of delaying and queuing.

### `getKV(k)`

Returns url querystring params as `object`.

Pass `k` to filter by field, like `getKV('test')` to return `string`.

### `pageActivityWatchFn(fn, options)`

Pass a function to `pageActivityWatchFn(fn)`, like:

```
function foo () { 
  console.log('bar') 
}

pageActivityWatchFn(foo, { pages: 1, clicks: 2 })
```

If !options, your function will fire on each page activity `['pages', 'scrolls', 'touches', 'clicks']`. If options, your function will fire if number of activities is greater than your number in options `options = { pages: 1, scrolls: 0, touches: 0, clicks: 2 }` 

For example, this can be helpful for loading a script tag based on real page activity, to help with page speed.
