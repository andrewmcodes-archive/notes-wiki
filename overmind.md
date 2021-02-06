# Overmind

[Overmind](https://github.com/DarthSim/overmind) is a process manager for [[Procfile]]-based applications and [[tmux]]. Easily run multiple processes together like [[Rails]], Webpacker, and Sidekiq - no Foreman!

## Install

```bash
# Install tmux if needed
brew install tmux
# Install overmind via brew
brew install overmind
```

## Configuration

### `Procfile`

```bash
web: bin/rails server
worker: bundle exec sidekiq
webpack: bin/webpack-dev-server
```

### `.overmind.env`

```env
OVERMIND_PORT=3000
OVERMIND_DAEMONIZE=1
OVERMIND_PROCFILE=./Procfile.dev
```

## Commands

- Start: `overmind start`
- Use `Procfile.dev`: `overmind start -f path/to/your/Procfile.dev`
- Start in detached mode: `overmind start -D`
- Connect: `overmind connect [process_name]`
- Restart: `overmind restart [process_name]`
- Kill all: `overmind kill`
