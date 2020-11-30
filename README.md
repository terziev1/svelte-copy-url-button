# svelte-copy-url-button

Simple Svelte based button that copies the current url. 

## Installation

### Using npm

#### Sapper or Other Svelte Bundler

For Sapper you need to install the package as a dev module to so it gets compiled.  If you install it as a runtiome dependency you will 500 errors on the server side.  This is explained [here](https://github.com/sveltejs/sapper-template#using-external-components).

```bash
$ npm i -D svelte-copy-url
```

### PureJS

```bash
$ npm i --save svelte-copy-url
```


## Usage
Basic usage from svelte looks like this:

```html
<script>
import SvelteCopyUrl from 'svelte-copy-url-button';

</script>
<SvelteCopyUrl
  class="customClassName"
  size="14"
  defaultText="Copy url"
  copiedText="Copied!"
  icon="false"
  timeout="1000"
/>

```
