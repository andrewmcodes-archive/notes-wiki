# Log4brains

[Log4brains](https://github.com/thomvaill/log4brains) is a docs-as-code knowledge base for your development and infrastructure projects. Basically a [[Documentation]]

## Install

```bash
npm install -g log4brains
log4brains init
```

Or use via `npx`.

## Configuration

### `.log4brains.yml`

```yaml
project:
  name: Foo Bar # The name that should be displayed in the UI
  tz: America/New_York # The timezone that you use for the dates in your ADR files
  adrFolder: ./src/adr # The location of your ADR files
```

## Commands

- Preview locally: `npx log4brains preview`
- Create new ADR: `npx log4brains adr new`
- Build for production: `npx log4brains build`

## Resources

- [CI/CD Setup](https://github.com/thomvaill/log4brains#-cicd-configuration-examples)
- [Architecture Decision Record](https://adr.github.io/)
- [Screencast](https://www.youtube.com/watch?v=HDEwOCn9T0w)
