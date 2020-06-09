# `build`

Builds a React Component located in `./src` and outputs `cjs`, `mjs`, and `css` into `dist`

## Options

| Flag | Type | Description |
| - | - | - |
| `--watch`, `-w` | Boolean | Watch for file changes and recompile. |
| `--ignore` | String | A minimatch to ignore |

## Custom Babel Config

To customize your babel configuration, create a .babelrc at the root of the project.

## Custom PostCSS Config

To customize your postcss configuration, create a postcss.config.js at your package or monorepo root.

It must use the base config for css modules to function properly.

```js
const defaultConfig = require('@design-systems/build/postcss.config');
const mixins = require('postcss-mixins');

module.exports = (ctx) => {
  const config = defaultConfig(ctx);

  return {
    ...config,
    plugins: [
      mixins({ mixinsFiles }),
      ...config.plugins
    ]
  }
});
```

