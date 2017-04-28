# Interface `Browser`

## Methods

* [`pageTitle`](#method-pagetitle)
* [`pageUrl`](#method-pageurl)
* [`windowX`](#method-windowx)
* [`windowY`](#method-windowy)
* [`windowWidth`](#method-windowwidth)
* [`windowHeight`](#method-windowheight)
* [`scriptResult`](#method-scriptresult)
* [`executeScript`](#method-executescript)
* [`loadPage`](#method-loadpage)
* [`maximizeWindow`](#method-maximizewindow)
* [`navigateBack`](#method-navigateback)
* [`navigateForward`](#method-navigateforward)
* [`reloadPage`](#method-reloadpage)
* [`setWindowPosition`](#method-setwindowposition)
* [`setWindowSize`](#method-setwindowsize)
* [`sleep`](#method-sleep)
* [`takeScreenshot`](#method-takescreenshot)

### Method `pageTitle`

Type definition:

* **`pageTitle: Accessor<string>`**

Example TAP output: `ok 1 - page title should contain 'bar' (attempt 1 of 5)`

Example usage:

```js
const {browser, it, test} = require('cybernaut');

test('foo', async t => {
  await t.assert(browser.pageTitle, it.should.contain('bar'));
});
```

### Method `pageUrl`

Type definition:

* **`pageUrl: Accessor<string>`**

Example TAP output: `ok 1 - page url should contain 'http://bar.baz' (attempt 1 of 5)`

Example usage:

```js
const {browser, it, test} = require('cybernaut');

test('foo', async t => {
  await t.assert(browser.pageUrl, it.should.contain('http://bar.baz'));
});
```

### Method `windowX`

Type definition:

* **`windowX: Accessor<number>`**

Example TAP output: `ok 1 - window x-position should equal 123 (attempt 1 of 5)`

Example usage:

```js
const {browser, it, test} = require('cybernaut');

test('foo', async t => {
  await t.assert(browser.windowX, it.should.equal(123));
});
```

### Method `windowY`

Type definition:

* **`windowY: Accessor<number>`**

Example TAP output: `ok 1 - window y-position should equal 123 (attempt 1 of 5)`

Example usage:

```js
const {browser, it, test} = require('cybernaut');

test('foo', async t => {
  await t.assert(browser.windowY, it.should.equal(123));
});
```

### Method `windowWidth`

Type definition:

* **`windowWidth: Accessor<number>`**

Example TAP output: `ok 1 - window width should equal 123 (attempt 1 of 5)`

Example usage:

```js
const {browser, it, test} = require('cybernaut');

test('foo', async t => {
  await t.assert(browser.windowWidth, it.should.equal(123));
});
```

### Method `windowHeight`

Type definition:

* **`windowHeight: Accessor<number>`**

Example TAP output: `ok 1 - window height should equal 123 (attempt 1 of 5)`

Example usage:

```js
const {browser, it, test} = require('cybernaut');

test('foo', async t => {
  await t.assert(browser.windowHeight, it.should.equal(123));
});
```

### Method `scriptResult`

Type definition:

* **`scriptResult(scriptName: string, script: Script): Accessor<any>`**
* `Script = (callback: (result?: any) => void) => void`

Example TAP output: `ok 1 - result of script 'bar' should equal 'baz' (attempt 1 of 5)`

Example usage:

```js
const {browser, it, test} = require('cybernaut');

test('foo', async t => {
  await t.assert(browser.scriptResult('bar', callback => {
    // This function will be executed in browser context,
    // so any references to outer scope won't work

    // ...

    callback('baz');
  }), it.should.equal('baz'));
});
```

### Method `executeScript`

Type definition:

* **`executeScript(scriptName: string, script: Script): Action`**
* `Script = (callback: (result?: any) => void) => void`

Example TAP output: `ok 1 - execute script 'bar' (attempt 1 of 5)`

Example usage:

```js
const {browser, test} = require('cybernaut');

test('foo', async t => {
  await t.perform(browser.executeScript('bar', callback => {
    // This function will be executed in browser context,
    // so any references to outer scope won't work

    // ...

    callback();
  }));
});
```

### Method `loadPage`

Type definition:

* **`loadPage(url: string): Action`**

Example TAP output: `ok 1 - load page 'http://bar.baz' (attempt 1 of 5)`

Example usage:

```js
const {browser, test} = require('cybernaut');

test('foo', async t => {
  await t.perform(browser.loadPage('http://bar.baz'));
});
```

### Method `maximizeWindow`

Type definition:

* **`maximizeWindow(): Action`**

Example TAP output: `ok 1 - maximize window (attempt 1 of 5)`

Example usage:

```js
const {browser, test} = require('cybernaut');

test('foo', async t => {
  await t.perform(browser.maximizeWindow());
});
```

### Method `navigateBack`

Type definition:

* **`navigateBack(): Action`**

Example TAP output: `ok 1 - navigate back (attempt 1 of 5)`

Example usage:

```js
const {browser, test} = require('cybernaut');

test('foo', async t => {
  await t.perform(browser.navigateBack());
});
```

### Method `navigateForward`

Type definition:

* **`navigateForward(): Action`**

Example TAP output: `ok 1 - navigate forward (attempt 1 of 5)`

Example usage:

```js
const {browser, test} = require('cybernaut');

test('foo', async t => {
  await t.perform(browser.navigateForward());
});
```

### Method `reloadPage`

Type definition:

* **`reloadPage(): Action`**

Example TAP output: `ok 1 - reload page (attempt 1 of 5)`

Example usage:

```js
const {browser, test} = require('cybernaut');

test('foo', async t => {
  await t.perform(browser.reloadPage());
});
```

### Method `setWindowPosition`

Type definition:

* **`setWindowPosition(x: number, y: number): Action`**

Example TAP output: `ok 1 - set window position to 123,456 (attempt 1 of 5)`

Example usage:

```js
const {browser, test} = require('cybernaut');

test('foo', async t => {
  await t.perform(browser.setWindowPosition(123, 456));
});
```

### Method `setWindowSize`

Type definition:

* **`setWindowSize(width: number, height: number): Action`**

Example TAP output: `ok 1 - set window size to 123x456 (attempt 1 of 5)`

Example usage:

```js
const {browser, test} = require('cybernaut');

test('foo', async t => {
  await t.perform(browser.setWindowSize(123, 456));
});
```

### Method `sleep`

Type definition:

* **`sleep(duration: number): Action`**

Example TAP output: `ok 1 - sleep for 123 ms (attempt 1 of 5)`

Example usage:

```js
const {browser, test} = require('cybernaut');

test('foo', async t => {
  await t.perform(browser.sleep(123));
});
```

### Method `takeScreenshot`

Type definition:

* **`takeScreenshot(): Action`**

Example TAP output: `ok 1 - take screenshot 'screenshots/07cc9369-ab10-4221-9bc9-18ad12b87c7c.png' (attempt 1 of 5)`

Example usage:

```js
const {browser, test} = require('cybernaut');

test('foo', async t => {
  await t.perform(browser.takeScreenshot());
});
```