# Bash

- [Bash](#bash)
  - [fzf](#fzf)
  - [sync bash history & unlimited history](#sync-bash-history--unlimited-history)
  - [add git branch to bash prompt](#add-git-branch-to-bash-prompt)
  - [add conda env to bash prompt](#add-conda-env-to-bash-prompt)

## fzf

- install: https://github.com/junegunn/fzf
- fuzzy search cmd history: `CTRL+R` to search in the bash history
- fuzzy search files: `fzf`

## sync bash history & unlimited history

- `history -a` appends history in the current session to `~/.bash_history`
- `history -n` reads history in `~/.bash_history` into current session
- enable unlimited history records: set `HISTSIZE=-1` and `HISTFILESIZE=-1` in `~/.bashrc`

## add git branch to bash prompt

Here's my favorite prompt theme: [link](https://gist.github.com/justintv/168835#gistcomment-1717504).

## add conda env to bash prompt

Add the following lines to `~/.bashrc`:

```
PS1=""

# Add conda environment to prompt
if [ ! -z "$CONDA_DEFAULT_ENV" ]
then
    PS1+="($CONDA_DEFAULT_ENV) "
fi
```
