# Browserslist

Browserslist can be configured via `.btowserslistrc`:

```
# Browsers that we support

defaults
not IE 11
maintained node versions
```

or inside of `package.json`:

```
{
  "browserslist": [
    "defaults",
    "not IE 11",
    "maintained node versions"
  ]
}
```
