# Week 06 ( runtime keyboard shortcuts )

- [Week 06 ( runtime keyboard shortcuts )](#week-05--runtime-keyboard-shortcuts-)
  - [Pre-reqs](#pre-reqs)
  - [Why](#why)
  - [Examples](#examples)
  - [Resources](#resources)

## Pre-reqs

- bash setup
  - [video](https://youtu.be/mfP8R1yr80A)
  - [writen instruction](/install_methods/)
- programs (optional, but recommended)
  - nmap

## Why

1. Give better feedback
2. Don't know what you want when launched
3. Very helpful and useful for debugging

## Examples

```bash
apk add nmap
nmap -Pn -n -p- scanme.nmap.org
?
v
V
d
D
p
P
Ctrl+Z
fg
Ctrl+C # kill nmap scan
~?
~.
```

## Resources

- Bash Interactive Keyboard Shortcuts
  - [The Best Keyboard Shortcuts for Bash (aka the Linux and macOS Terminal)](https://www.howtogeek.com/howto/ubuntu/keyboard-shortcuts-for-bash-command-shell-for-ubuntu-debian-suse-redhat-linux-etc/)
  - [The List Of Useful Bash Keyboard Shortcuts](https://ostechnix.com/list-useful-bash-keyboard-shortcuts/)
- [SSH Interactive Keyboard Shortcuts](https://www.pixelbeat.org/lkdb/ssh.html)
- [Nmap Interactive Keyboard Shortcuts](https://nmap.org/book/man-runtime-interaction.html)
- [(FreeBSD) The Power Of CTRL+T](https://blog.danielisz.org/2018/06/21/the-power-of-ctrlt/)
- tool(s) used during recording:
  - [nmap](https://nmap.org/)
