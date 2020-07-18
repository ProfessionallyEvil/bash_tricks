# Week 05 ( keyboard shortcuts )

- [Week 05 ( keyboard shortcuts )](#week-05--keyboard-shortcuts-)
  - [Pre-reqs](#pre-reqs)
  - [Why](#why)
  - [Examples](#examples)
  - [Resources](#resources)
  - [Video](#video)

## Pre-reqs

- bash setup
  - [video](https://youtu.be/mfP8R1yr80A)
  - [writen instruction](/install_methods/)

## Why

1. Compounding on things we learned
2. Efficient exerience = more fun experience
3. Cumbersome, but rewarding

## Examples

```bash
help set
set
set -o
set -o | grep -E '^(emacs|vi)'
## emacs mode
Ctrl+u # delete everything from the cursor to the beginning of the line
Ctrl+w # delete the previous work on the command line before the cursor
Ctrl+l # clear the terminal window
Ctrl+a # jump to the beginning of the command line
Ctrl+e # move your cursor to the end of the command line
Ctrl+r # search command history in reverse, continue pressing key sequence to continue backwards search. Esc when done or command found
Ctrl-S # Search forward through your history
## vi mode
set -o vi
```

## Resources

- [Hash Crack (Password Cracking Manual)](https://www.netmux.com/#books) ([amazon link](https://www.amazon.com/gp/product/1793458618) (from authors website & affiliate free))
  - Main Chapter(s): Cheat Sheets
    - Sub Section: TERMINAL COMMAND CHEAT SHEET
- [Emacs Keybindings in Bash](https://blog.pythian.com/emacs-keybindings-in-bash/)
  - **note:** not the best format, but appears to not collide with possible terminal key sequences (at least on urxvt)
- [How to Navigate Linux Command Line Using Keybinding (Linux Ctrl Command Examples)](https://www.thegeekstuff.com/2014/05/linux-keybindings/)
  - **note:** really nice format, but appears to collide with possible terminal key sequences (at least on urxvt)
- [enable Ctrl+L to clear screen when 'set -o vi' is set](https://unix.stackexchange.com/questions/104094/is-there-any-way-to-enable-ctrll-to-clear-screen-when-set-o-vi-is-set#answer-104101)
- [How to be productive with Vim environment and stay mouseless](https://nosarthur.github.io/coding/2020/06/27/vim-productivity.html#--bash-in-vim-mode)
- tool(s) used during recording:
  - [screenkey](https://www.linuxuprising.com/2020/05/screenkey-is-tool-that-shows-pressed.html)

## Video

[![video pic](https://img.youtube.com/vi/I7QMLSmibLw/0.jpg)](https://youtu.be/I7QMLSmibLw)
