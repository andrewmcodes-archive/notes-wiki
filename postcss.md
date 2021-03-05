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

export LANG=en_US.UTF-8
