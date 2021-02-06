# Husky

## Config

`.huskyrc`

```json
{
	"hooks": {
		"pre-commit": "lint-staged",
		"commit-msg": "commitlint -E HUSKY_GIT_PARAMS"
	}
}
```

This example uses [[lintstaged]] and [[commitlint]]
