# .config

My dotfiles based on configurations living in $XDG_CONFIG_HOME or ~/.config

## Management

As a means of easily separating what lives in my actual .config between my osx and linux systems, I choose to clone this repo to ~/github.com/hampgoodwin/.config and then create symlinks to $XDG_CONFIG_HOME or ~/.config. I understand there are home directory managers that can manage this for me, but I don't like them. The fs is good enough for me.

## Mac Install

Use the determinate systems pkg installer. This is found on the "get started" instructions for determinate systems. For some reason, the curl install.sh no longer works.

## Linux

Just use nixos. I should, at some point, add a node about enabling flakes. Theres some recent discourse around removing flakes from nix completely. I think this would create a schism. They should be support OOTB. 

## Dependencies

I strive to manage all dependencies in my nix configurations/flakes. I would prefer to stay away from managing various dependency mangement tools, or split between such. As such, I will try to _not_ manage anything directly via brew or mac install app. For NixOS Nix configuration _is_ the package manager.

---

## Configurations

Create a symlink from you $XDG_CONFIG_HOME/zsh/.zshenv to your $HOME/.zshenv . Unfortunately zsh will only look for this env file in the home directory. However, once it is in place, everything else should work well!

### git diff using delta

In order to get my diff displaying as desired, the below should be used in my global git config
I could probably add this to my .config with some instructs to cop to wherever I need to?

```sh
[core]
    pager = delta

[interactive]
    diffFilter = delta --color-only

[delta]
    navigate = true    # use n and N to move between diff sections
    side-by-side = true


    # delta detects terminal colors automatically; set one of these to disable auto-detection
    # dark = true
    # light = true

[merge]
    conflictstyle = diff3

[diff]
    colorMoved = default
```
