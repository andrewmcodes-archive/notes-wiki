# Docker

## Development Tools

### Captain

Captain searches for docker-compose projects in your `$HOME` folder and allows you to start and stop those projects by matching the project's directory name.

#### Installation

```bash
curl -L https://github.com/jenssegers/captain/releases/download/0.3.3/captain-osx > /usr/local/bin/captain && chmod +x /usr/local/bin/captain
```

#### Usage

To see a list of available projects, use the `ls` command:

```bash
captain ls
```

This will outpt all available projects regardless of where you are in relation to that project.
Start a project with the `start project-name` and stop with `stop project-name`.
