# Tmux Cheatsheet

**Table of contents**

## Pre-requisites

- This cheatsheet specifically relies upon my own [configuration](https://github.com/dimaskh/dotfiles/blob/master/.tmux.conf).
- Some of the commands have versions based on the [aliases](https://github.com/dimaskh/dotfiles/blob/master/.aliases) that I use.
- I use <C-a> as a prefix.

**Abbreviations**

| Key | Description |
| --- | ----------- |
| C-x | ctrl+x      |
| M-x | alt+x       |

## Tmux commands

Start new unnamed session:

    t
    tmux

Start new named session:

    tns
    tmux new -s {name}

Attach to session:

    tmux attach

Attach to named session:

    ta {name}
    tmux a -t {name}

List sessions:

    tls
    tmux ls

Kill session:

    tmux kill-session -t {name}

Kill all the tmux sessions:

    tmux ls | grep : | cut -d. -f1 | awk '{print substr($1, 0, length($1)-1)}' | xargs kill

## Tmuxinator commands

Create or edit a project with the configuration file located in `~/.config/tmuxinator` directory:

    tx n {project}
    tx new {project}

Create or edit a local project with the configuration file stored in the current working directory:

    tx n --local {project}
    tx new --local {project}

Edit a configuration file:

    tx o {project}
    tx open {project}

Start a project, e.g. fire up tmux with all the tabs and panes configured:

    tx s {project}
    tx start {project}

Stop a project:

    tx stop {project}

List all the projects configured:

    tx l
    tx ls
    tx list

Remove a project:

    tx rm {project}
    tx delete {project}

Copy an existing project:

    tx c {existing} {new}
    tx cp {existing} {new}
    tx copy {existing} {new}

Remove all tmuxinator configs, aliases and scripts:

    tx i
    tx implode

Examine the environment and identify problems with the configuration:

    tx doctor

Show tmuxinator help:

    tx h
    tx help

Show the shell commands that get executed for a project:

    tx debug {project}

Show tmuxinator's version:

    tx version

## Shortcuts

The tmux shortcuts are intended to be used with prefix (C-a)

### General

| Key | Description |
| :-: | ----------- |
| `?` | Shows a list of all commands (`q` closes the list) |
| `:` | Enter a tmux command |

### Windows

| Key | Description |
| :-: | ----------- |
| `c` | Create a new window |
| `,` | Rename current window |
| `n` | Switch to next window |
| `w` | List windows |
| `{0..9}` | Go to the window {number} |
| `&` | Kill the current window |
| `f` | Find a window |

### Panes

| Key | Description |
| :-: | ----------- |
| `|` | Split window vertically |
| `-` | Split window horizontally |
| Arrow keys, `h, j, k, l` | Navigate panes |
| `q` | Show pane numbers |
| `o` | Switch to the next pane |
| `{` | Move the current pane left |
| `}` | Move the current pane right |
| `x` | Kill the current pane |
| `<Space>` | Toggle through different pane layouts |

### Sessions

| Key | Description |
| :-: | ----------- |
| `d` | Detach from session |
