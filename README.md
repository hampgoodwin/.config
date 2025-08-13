# .config

My dotfiles based on configurations living in $XDG_CONFIG_HOME or ~/.config

## Management

As a means of easily separating what lives in my actual .config between my osx and linux systems, I choose to clone this repo to ~/github.com/hampgoodwin/.config and then create symlinks to $XDG_CONFIG_HOME or ~/.config. I understand there are home directory managers that can manage this for me, but I don't like them. The fs is good enough for me.

## Mac Install

Navigate to the determinate systems [nix-installer](https://github.com/DeterminateSystems/nix-installer) and then use the [macos package installer](https://install.determinate.systems/determinate-pkg/stable/Universal) to install nix on MacOS. The link as of 20250729 was in a "tips" section on the nix-installer readme.

### Download outside Nix

- enpass
- wireguard
- discord

## Linux

I would just recommend using nixos, however if this is is not possible, using the [nix-installer](https://github.com/DeterminateSystems/nix-installer) should be sufficient!

## Dependencies

I strive to manage all dependencies in my nix configurations/flakes. I would prefer to stay away from managing various dependency mangement tools, or split between such. As such, I will try to _not_ manage anything directly via brew or mac install app. For NixOS Nix configuration _is_ the package manager.

---

## Configurations

Create a symlink from you $XDG_CONFIG_HOME/zsh/.zshenv to your $HOME/.zshenv . Unfortunately zsh will only look for this env file in the home directory. However, once it is in place, everything else should work well!

### bat

After symlinking the bat configuration directory to $XDG_CONFIG_HOME/bat, we need to instruct bat to rebuild it's cache which will bring in the theme: `bat cache --build`

### kitty

kitty is configured to automatically pick between a light, dark, and no preference themes based on the [OS's light/dark themeing](https://sw.kovidgoyal.net/kitty/kittens/themes/#change-color-themes-automatically-when-the-os-switches-between-light-and-dark). For MacoS this means you need to configure Night Shift.

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
    conflictstyle = zdiff3

[diff]
    colorMoved = default
```

### nvim

We use some lsp configurations and toolings in nvim which nvim doesn't provide. As such the package manager for the system should provide these things. Some examples of things we want can be found in the nixos-config flake files. Worst case, nvim will give a diagnostic error when starting up indicating what is missing.
