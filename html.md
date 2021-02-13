# Html

## Performance

Append links to #head with [[ERB]]

```javascript
<script>
  (function() {
      var cssMain = document.createElement('link');
      cssMain.href = '<%= absolute_url "styles/index.css" %>';
      cssMain.rel = 'stylesheet';
      cssMain.type = 'text/css';
      document.getElementsByTagName('head')[0].appendChild(cssMain);
      var cssFa = document.createElement('link');
      cssFa.href = '<%= absolute_url "styles/syntax.css" %>';
      cssFa.rel = 'stylesheet';
      cssFa.type = 'text/css';
      document.getElementsByTagName('head')[0].appendChild(cssFa);
  })();
</script>
```
