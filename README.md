# zsh-unique-id

#### Commit count

Don't worry about **low commit count**, this project is a derivative of
[zdharma-continuum/zconvey](https://github.com/zdharma-continuum/zconvey), which has ~190 commits and has been
maintained and used for 1.5 years now.

### Introduction

This plugin provides a **unique number** that identifies a **running** Zshell session, in its shell variable `$ZUID_ID`.
Besides this unique number, also a unique *codename* is provided, in shell variable `$ZUID_CODENAME`. Once you load this
plugin, the two parameters will be set, and their values will not be available to other Zshell sessions (being thus
*unique*).

`$ZUID_ID` is a progressing number starting from `1`. `$ZUID_CODENAME` is chosen from a list of predefined codenames,
see the default list below.

An example use case is to hold logs in files `.../mylog-${ZUID_CODENAME}.log`, so that two different Zshells will not
write to the same file at the same time.

Default codenames are:

- atlantis (for `ZUID_ID` == `1`)
- echelon (for `ZUID_ID` == `2`)
- quantum (etc.)
- ion
- proxima
- polaris
- solar
- momentum
- hyper
- gloom
- velocity
- future
- enigma
- andromeda
- saturn
- jupiter
- aslan
- commodore
- falcon
- persepolis
- dharma
- samsara
- prodigy
- ethereal
- epiphany
- aurora
- oblivion

Zstyle configuration allows to customize the codenames:

```zsh
zstyle :plugin:zuid codenames paper metal wood plastic # first 4 shells will have those codenames
```

# Installation

**The plugin is "standalone"**, which means that only sourcing it is needed (without using a plugin manager). So to
install, unpack `zsh-unique-id` somewhere and add:

```zsh
source {where-zsh-unique-id-is}/zsh-unique-id.plugin.zsh
```

to `zshrc`.

Sourcing is recommended, because it can be done early, at top of zshrc, without a plugin manager – to acquire the unique
identification as early as possible.

## [Zinit](https://github.com/zdharma-continuum/zinit)

Add `zinit load zdharma-continuum/zsh-unique-id` to your `.zshrc` file. Zinit will clone the plugin the next time you
start zsh. To update issue `zinit update zdharma-continuum/zsh-unique-id`.

## Antigen

Add `antigen bundle zdharma-continuum/zsh-unique-id` to your `.zshrc` file. Antigen will handle cloning the plugin for
you automatically the next time you start zsh.

## Oh-My-Zsh

1. `cd ~/.oh-my-zsh/custom/plugins`
1. `git clone https://github.com/zdharma-continuum/zsh-unique-id.git`
1. Add `zsh-unique-id` to your plugin list

## Zgen

Add `zgen load zdharma-continuum/zsh-unique-id` to your .zshrc file in the same place you're doing your other
`zgen load` calls in.
