# Bash

- [Bash](#bash)
  - [fzf](#fzf)
  - [sync bash history & unlimited history](#sync-bash-history--unlimited-history)

## fzf

- install: https://github.com/junegunn/fzf
- fuzzy search: `CTRL+r` to search in the bash history

## sync bash history & unlimited history

- `history -a` appends history in the current session to `~/.bash_history`
- `history -n` reads history in `~/.bash_history` into current session
- enable unlimited history records: set `HISTSIZE=-1` and `HISTFILESIZE=-1` in `~/.bashrc`
