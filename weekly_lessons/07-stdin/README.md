# Week 07 ( stdin )

- [Week 07 ( stdin )](#week-07--stdin-)
  - [Pre-reqs](#pre-reqs)
  - [Why](#why)
  - [Examples](#examples)
  - [Resources](#resources)

## Pre-reqs

- bash setup
  - [video](https://youtu.be/mfP8R1yr80A)
  - [writen instruction](/install_methods/)
- programs (optional, but recommended)
  - recon-ng

## Why

1. Level up your bash scripting
2. Really cool to see what is possible
3. Very helpful and useful for daily activities

## Examples

```bash
git clone https://github.com/lanmaster53/recon-ng && cd ${_##*/}
sed -i.orig 's/build-deps/& \&\& apk add --no-cache bash/' Dockerfile
# if you need to do it again run below command
#   cp Dockerfile.orig Dockerfile && sed -i.orig 's/build-deps/& \&\& apk add bash/' $_
docker build --rm -t recon-ng:latest .
# definitely something you don't want to do in production!!! ( -v flag )
#   https://blog.secureideas.com/2018/08/escaping-the-whale-things-you-probably-shouldnt-do-with-docker-part-2.html
#   specifically: https://github.com/ProfessionallyEvil/Pequod/blob/master/pres.md#bind-mounts
docker run --rm -it -v $(pwd):/recon-ng recon-ng bash
./recon-ng
exit
./recon-ng -r <(printf 'marketplace install all\nexit\n')

# file descriptors 0, 1, 2, 3, etc...

pe-bash

### difference between < << & <<<
## <
# read in from file
## <<
# is for the heredoc structure
## <<<
# read in from string
tr ' ' '\n' <<< "hello there"

# https://blog.elreydetoda.site/curl-bad/
#   command I tell them to run: curl -fsSL 'https://git.io/Jvpvi' | bash -xs '24' '192.168.22.0' '10.0.0.1'
curl -fsSL 'https://git.io/Jvpvi' | bash -s '24' '192.168.22.0' '10.0.0.1'

exit # get out of bash container
sort -u << 'EOF'
bison
cmake
cmake
cmake
gcc
gcc
gcc-mingw-w64
glib-2.0
gnutls
EOF

sort -u << 'EOF' | tr '\n' ' '
bison
cmake
cmake
cmake
gcc
gcc
gcc-mingw-w64
glib-2.0
gnutls
EOF

# https://blog.elreydetoda.site/cool-shell-tricks/#bashscriptinggrepheredocwipaddresses
grep -oP '\d+\.\d+\.\d+\.\d+(\/\d+|)' << 'EOF'
8.8.8.8-google's ip
1.1.1.1/8: cloudflare's ip
9.9.9.9 - quad-9's IP
EOF

mapfile -t array < <(printf 'hello\nthere\n')
echo "${array[0]}"
echo "${array[1]}"
```

## Resources

- [difference between << and <<<](https://askubuntu.com/questions/678915/whats-the-difference-between-and-in-bash#answer-678919)
- [https://explainshell.com/explain?cmd=curl+-fsSL+%27https%3A%2F%2Fgit.io%2FJvpvi%27+%7C+bash+-s+%2724%27+%27192.168.22.0%27+%2710.0.0.1%27](https://explainshell.com/explain?cmd=curl+-fsSL+%27https%3A%2F%2Fgit.io%2FJvpvi%27+%7C+bash+-s+%2724%27+%27192.168.22.0%27+%2710.0.0.1%27)
- references in code:
  - [https://blog.secureideas.com/2018/08/escaping-the-whale-things-you-probably-shouldnt-do-with-docker-part-2.html](https://blog.secureideas.com/2018/08/escaping-the-whale-things-you-probably-shouldnt-do-with-docker-part-2.html)
    - specifically: [https://github.com/ProfessionallyEvil/Pequod/blob/master/pres.md#bind-mounts](https://github.com/ProfessionallyEvil/Pequod/blob/master/pres.md#bind-mounts)
  - [https://blog.elreydetoda.site/curl-bad/](https://blog.elreydetoda.site/curl-bad/)
  - [https://blog.elreydetoda.site/cool-shell-tricks/#bashscriptinggrepheredocwipaddresses](https://blog.elreydetoda.site/cool-shell-tricks/#bashscriptinggrepheredocwipaddresses)
- tool(s) used during recording:
  - [recon-ng](https://github.com/lanmaster53/recon-ng)
