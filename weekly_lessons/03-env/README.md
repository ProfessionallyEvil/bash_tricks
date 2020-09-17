# Week 03 ( understanding your env )

- [Week 03 ( understanding your env )](#week-03--understanding-your-env-)
  - [Pre-reqs](#pre-reqs)
  - [Why](#why)
  - [Examples](#examples)
  - [Resources](#resources)
  - [Video](#video)

## Pre-reqs

- bash setup
  - video

    [![video pic](https://img.youtube.com/vi/mfP8R1yr80A/0.jpg)](https://youtu.be/mfP8R1yr80A)

  - [writen instruction](/install_methods/)

## Why

1. can affect how you terminal responds to commands
2. possibly used maliciously (i.e. EDITOR) ( Itzik Kotler )

    [![BACE YT image](https://i.ytimg.com/vi/vMxEKjx0UEk/hqdefault.jpg?sqp=-oaymwEZCPYBEIoBSFXyq4qpAwsIARUAAIhCGAFwAQ==&rs=AOn4CLCVgd230LQ4-q6BrZ2yPCRg_9-w_A)](https://youtu.be/oO2Df7Y6ywY)

3. know what your working with in a pentest
      - possibly contextual environment variables
      - possibly credentials if service account
      - context for privlege currently running under
      - possible attack paths for PATH variable
      - SSH key attack ( Hal Pomeranz )

        [![youtube preview pic](https://i.ytimg.com/vi/-jNkjuWMFrk/hqdefault.jpg?sqp=-oaymwEZCPYBEIoBSFXyq4qpAwsIARUAAIhCGAFwAQ==&rs=AOn4CLAB_c5Hehtcu85yasZg3BsgvISLMA)](https://youtu.be/-jNkjuWMFrk?t=1840)

## Examples

```bash
type env
env
type set
help set | less
set | less
testingz(){
  echo hello
}
set
exit
set
pe-bash
set | grep SHELL
sh
help
set
```

## Resources

- [cd man page](https://ss64.com/bash/cd.html)
- [modified hardend scripting env](https://elrey.casa/bash/scripting/harden)
  
## Video

[![video pic](https://img.youtube.com/vi/kd6VitblTwU/0.jpg)](https://youtu.be/kd6VitblTwU)
