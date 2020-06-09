# `storybook`

Create a storybook for your component

## Commands

  - **build** - Build the storybook for deployment
  - **start** - Start the storybook development server

## `build`

Build the storybook for deployment

### Options

| Flag | Type | Description |
| - | - | - |
| `--sketch` | Boolean | Generate sketch assets for the storybook |

### Examples

```sh
ds storybook build
```

## `start`

Start the storybook development server

### Options

| Flag | Type | Description |
| - | - | - |
| `--ci` | Boolean | Start the storybook server in CI mode |
| `--findPort` | Boolean | Automatically assign a port if the default (6006) is occupied |

### Examples

```sh
ds storybook dev
```

## Custom Storybook Configuration

You can supply your own storybook settings by adding a `.storybook` directory at the root of the project.

It supports the following files:

1. addons.js - configure addon loading. It acts exactly how a config.js works in storybook. Overrides the default addons.js
2. config.js - configure extra addons and load your stories. It acts exactly how a config.js works in storybook, just with all our default decorators and parameters. If using this you MUST load your stories or add this line "require('@design-systems/storybook/.storybook/defaultConfig');"
3. middleware.js - provide express middleware to be used by storybook
4. presets.js - configure storybook presets. It acts exactly how a presets.js works in storybook
5. webpack.config.js - configure extra webpack settings, works exactly like it does in storybook (ex: ({ config }) => config)
6. dark-logo.png - Logo for the storybook when it's in dark mode
7. light-logo.png - Logo for the storybook when it's in light mode

