# dotfiles

I am migrating all my scripts, system init scripts, and conf files into this repo. Everything will be added slowly.

It will be a long process, since I don't have much stimulation to migrate when my system is running fine :p.
Most of these files are added during my OS reinstalls.

## Try

You can use Docker to try out these dotfiles in a container without installing them into your system. Note that it is expected to be some display issues with the prompt when running in the container.

```bash
# We need our dotfiles to build the container
git clone --recurse-submodules --shallow-submodules https://github.com/charlie0129/dotfiles
cd dotfiles
# Build the container. Just install some packages, bootstap dotfiles, and that's it.
docker build -t dotfiles .
# Run it!
docker run -it --rm dotfiles /bin/zsh
```

## Install

```bash
# Clone this repo with submodules to anywhere you want.
# `~/dotfiles` is recommended, which is used in this example.
git clone --recurse-submodules --shallow-submodules https://github.com/charlie0129/dotfiles ~/dotfiles
cd ~/dotfiles
# Install the dotfiles. Remember to keep an eye on the output for conflicts.
# If necessary, add a -f option to *overwrite* any existing configuration.
./bootstrap.sh
```

You can put custom commands and bin in `alias/custom.sh`, `bin/custom/`, and `env/custom.sh`, which will not be tracked by git. (TODO: write some documentations.)

## Overview

- `alias`: shell aliases
- `bin`: scripts
- `conf`: system configurations
- `cron`: cron jobs
- `env`: environment variables, like PATH

Note: `conf` will not be installed during bootstrap.