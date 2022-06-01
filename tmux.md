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

## Commands

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


## Shortcuts
