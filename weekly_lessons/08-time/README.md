# Week 08 ( time )

- [Week 08 ( time )](#week-08--time-)
  - [Pre-reqs](#pre-reqs)
  - [Why](#why)
  - [Examples](#examples)
  - [Resources](#resources)

## Pre-reqs

- bash setup
  - video

    [![video pic](https://img.youtube.com/vi/mfP8R1yr80A/0.jpg)](https://youtu.be/mfP8R1yr80A)

  - [writen instruction](/install_methods/)
- programs (optional, but recommended)
  - nmap

## Why

1. Identify how long a task(s) has ran
2. "benchmarking" command execution time
3. Just cause 🙃

## Examples

```bash
help
help time
which time
type -t time
type -a time
time echo
time sleep 3
time echo hello world | tr ' ' '\n'
time echo hello world && echo not now
time ( echo hello world && echo not now )
```

## Resources

- [User CPU time vs System CPU time?](https://stackoverflow.com/questions/4310039/user-cpu-time-vs-system-cpu-time)
- Subshell warning ⬅️ placeholder
