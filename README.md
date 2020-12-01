# svelte-copy-url-button

Simple Svelte based button that copies the current url. 

[![version](https://img.shields.io/npm/v/svelte-copy-url-button.svg?style=flat-square)](http://npm.im/svelte-copy-url-button)

## Installation

### Using npm

#### Sapper or Other Svelte Bundler

For Sapper you need to install the package as a dev module to so it gets compiled.  If you install it as a runtime dependency you will 500 errors on the server side.  This is explained [here](https://github.com/sveltejs/sapper-template#using-external-components).

```bash
$ npm i -D svelte-copy-url-button
```

### PureJS

```bash
$ npm i --save svelte-copy-url-button
```


## Usage
Basic usage from svelte looks like this:

```html
<script>
import SvelteCopyUrlButton from 'svelte-copy-url-button';
// If url is not passed it will copy the url of the current page
let url = "https://svelte-copy-url-button.netlify.app/"
</script>

<SvelteCopyUrlButton
  class="customClassName"
  size="14"
  defaultText="Copy url"
  copiedText="Copied!"
  icon="{false}"
  timeout="1000"
  url="{url}"
/>

```
## Demo
Demo with some of the options can be viewed [here](https://svelte-copy-url-button.netlify.app/)


