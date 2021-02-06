# Lintstaged

## Config

`.lintstagedrc`

```json
{
	"*.{png,jpeg,jpg,gif,svg}": ["imagemin-lint-staged"],
	"*.js": ["eslint --fix"],
	"*.css": ["stylelint"]
}
```

This example uses [[eslint]], [[stylelint]], [[imagemin]]
