# Advanced Install Method

## Info

Doesn't matter how you get it, but no matter what you need >= bash 4.4, because of [`mapfile`](https://unix.stackexchange.com/questions/482358/does-readarray-allow-to-specify-line-delimiter#answer-482366)

note: I will be using the latest version of the [docker bash container](https://hub.docker.com/_/bash)

You can either use a *nix machine/environment, a vagrant box you declare ([mine](/Vagrantfile) will work as well, since it is ubuntu 20.04), or the aformentioned docker container.

## Warning

If you choose this install method I will **NOT** support it, because there is too many things that can vary between different *nix environments.

### Caveat

<!-- TODO: issue #5: add link for the advanced type of issue that they can submit once templates are created -->
If there is something that should work based on what you can deduce and there is a problem (maybe with what is supported in your current bash version), feel free to submit an issue but it will be marked wontfix, unless I decide to investigate more and change the label because it is interesting to me. 😁
