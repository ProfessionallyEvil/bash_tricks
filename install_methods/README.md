# Install Methods

## Methods

These are a few ways you can follow along with this video series.

- [First method](./00/) - this is probably the easiest for people that are new
- [Second method](./01/) - this is still decently easy, just involves a bit of cli work
- [Third method](./02/) - this is only if you are fairly aquainted with docker and/or vagrant

## Note

If you choose either the first or second method you will get some additional niceties that I have baked into the virtual machine's (vm's) setup through bash aliases.

### Niceties

I have created a few bash aliases to help aid in running docker.

1. `pe-bash` - this will the main location we will be playing around with things.
    - what is this: it is a bash alias that handles connecting to docker and mounting things you will need access to do all the bash tricks.
2. `pe-cleanup` - this is used to remove the previously created container in case you are having issues with your environment. You can then run the `pe-bash` command afterwards to re-setup your environment.
