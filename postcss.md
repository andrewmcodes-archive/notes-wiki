---
modified: 2021-03-10T20:49:22-05:00
---

# Postcss

## Config

`postcss.config.json`

`postcss-import` + [[Stylelint]]

```js
const stylelintConfig = require('./stylelint.config');

module.exports = {
  plugins: [
    require('postcss-import')({
      plugins: [
        require('stylelint')({
          config: stylelintConfig,
        }),
      ],
    }),
  ],
};
```

Other example plugins:

```js
require('postcss-easy-import'),
require('postcss-nested'),
require('postcss-dir-pseudo-class'),
require('postcss-logical'),
require('postcss-preset-env'),
require('postcss-retina-bg-img')({
  retinaSuffix: '@2x',
  logMissingImages: false,
}),
require('cssnano'),
require('postcss-reporter')({ clearReportedMessages: true }),
```


## Errors

`RangeError: Maximum call stack size exceeded`

Add `export LANG=en_US.UTF-8` to zshrc.

```

const isProd = process.env.NODE_ENV === "production";

module.exports = {
  plugins: [
    isProd &&
      require("postcss-import")({
        resolve: (id, basedir, importOptions) => {
          return "assets/styles/" + id;
        },
      }),
    isProd && require("autoprefixer"),
    require("tailwindcss"),
    isProd && require("cssnano"),
  ].filter((plugin) => !!plugin),
};
```