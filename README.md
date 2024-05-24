# Arturo - a language grammar for [highlight.js](https://highlightjs.org/)

![version](https://badgen.net/npm/v/highlightjs-arturo) ![license](https://badgen.net/badge/license/BSD3)
![install size](https://badgen.net/packagephobia/install/highlightjs-arturo) ![minified size](https://badgen.net/bundlephobia/min/highlightjs-arturo)

Arturo is a simple, expressive, and portable programming language for efficient scripting.

## Usage

Simply include the Highlight.js library in your webpage or Node app, then load this module.

### Static website or simple usage

Simply load the module after loading Highlight.js.
You'll use the minified version found in the `dist` directory.
This module is just a CDN build of the language, so it will register itself as the Javascript is loaded.

```html
<script type="text/javascript" src="/path/to/highlight.min.js"></script>
<script type="text/javascript" charset="UTF-8"
  src="/path/to/highlightjs-arturo/dist/arturo.min.js"></script>
<script type="text/javascript">
  hljs.highlightAll();
</script>
```

### Using directly from the UNPKG CDN

```html
<script type="text/javascript"
  src="https://unpkg.com/highlightjs-arturo/dist/arturo.min.js"></script>
```

- More info: <https://unpkg.com>

### With Node or another build system

If you're using Node / Webpack / Rollup / Browserify, etc, simply require the language module, then register it with Highlight.js.

```javascript
var hljs = require('highlightjs');
var hljsArturo = require('highlightjs-arturo');

hljs.registerLanguage("arturo", hljsArturo);
hljs.highlightAll();
```

### React

You need to import both Highlight.js and third-party language like Arturo:

```js
import React, {Component} from 'react'
import 'highlight.js/scss/darcula.scss' # your favourite theme
import arturo from './arturo'
import hljs from 'highlight.js'
hljs.registerLanguage('arturo', arturo);

class Highlighter extends Component
{
  constructor(props)
  {
    super(props);
    hljs.highlightAll();
  }

  render()
  {
    let {children} = this.props;
    return
    {
      <pre ref={(node) => this.node = node}>
        <code className="arturo">
          {children}
        </code>
      </pre>
    }
  }
}

export default Highlighter;
```

## License

Highlight.js is released under the BSD-3-Clause License.
See [LICENSE][1] file for details.

### Author

Yanis Zafirópulos

### Maintainer

Andras B Nagy <bnagyandras87@gmail.com>

## Links

- The official site for the Highlight.js library is <https://highlightjs.org/>.
- The Highlight.js GitHub project: <https://github.com/highlightjs/highlight.js>
- Learn more about Arturo: <https://arturo-lang.io/documentation/>

[1]: https://github.com/BNAndras/arturo-highlightjs/blob/master/LICENSE