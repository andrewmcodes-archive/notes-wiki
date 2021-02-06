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
