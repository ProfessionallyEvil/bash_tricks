# Week 09 ( nmap IP sanitizing )

- [Week 09 ( nmap IP sanitizing )](#week-09--nmap-ip-sanitizing-)
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

1. Automate grabbing IP ranges
2. Expand IP ranges to individual IP addresses
3. Validate IPs ranges will be in scope by excluding ranges provided

## Examples

```bash
alias ip_grep="grep -oP '\d+\.\d+\.\d+\.\d+(\/\d+|)'"
alias sort_ip_u="sort -ut '.' -k1,1n -k2,2n -k3,3n -k4,4n"
cd bash_tricks/weekly_lessons/09-nmap_ip_sanitizing
cat example_ips
ip_grep example_ips | sort_ip_u
set -x
ip_grep example_ips | sort_ip_u
set +x
ip_grep example_ips | sort_ip_u > example.ips
# enter docker container
pe-bash
alias sort_ip_u="sort -ut '.' -k1,1n -k2,2n -k3,3n -k4,4n"
alias get_nmap_results="grep report | awk '{print \$5}'"
alias together_now="get_nmap_results | sort_ip_u"
alias -p
apk add nmap --no-cache
cd weekly_lessons/09-nmap_ip_sanitizing/
## build up
nmap -iL example.ips -sL -n | head
nmap -iL example.ips -sL -n | tail
# trim off header and footer, only getting IPs
nmap -iL example.ips -sL -n | grep report
# get the 5th field
nmap -iL example.ips -sL -n | grep report | awk '{print $5}'
# optional to explore the data
nmap -iL example.ips -sL -n | grep report | awk '{print $5}' | less
##
nmap -iL example.ips -sL -n | get_nmap_results | sort_ip_u | head
nmap -iL example.ips -sL -n | together_now | tail
nmap -iL example.ips -sL -n | together_now | wc -l
# initial sanitizing
ls exclude_ips*
cat exclude_ips
nmap -iL example.ips -sL -n --excludefile exclude_ips | together_now | wc -l
echo $(( 512 - 495 ))
# remember it's exclusion is inclusive
nmap -sL -n -iL exclude_ips | together_now | wc -l
# will use last excludefile (show vs original number)
nmap -iL example.ips -sL -n --excludefile exclude_ips --excludefile exclude_ips01 | together_now | wc -l
# more than one input file ( not recommended regularly, normally just put them all in one file )
nmap -sL -n -iL <( cat exclude_* ) | together_now | wc -l
ls <( cat exclude_* )
cat <( cat exclude_* )
```

## Resources

- [aliases refresher](../04-aliases/README.md)
- [set/env refresher](../03-env/README.md)
- [stdin refresher](../07-stdin/README.md)
- [Grepping out IP addresses](https://elrey.casa/bash/ipgrep)
  - caveat: grep needs to support Perl regex `-P`, but [here](https://twitter.com/jstnkndy/status/1257388553748844544?s=20) is an alternative solutions if it doesn't
