# .config

My dotfiles based on configurations living in $XDG_CONFIG_HOME or ~/.config

## Dependencies

### nvim

NVIM is configured to use various language, language servers, formatters, and linters. Previously I used nvim-mason to manage these dependencies. However, that seems like it is not in the purview of an IDE/text-editor to manage. As such, everyone is expected to manage these installations on their own.

I am working on a nixos-config that will work on both linux and macos silicon such that nix-darwin and nix will provide the dependencies required.

---

In order to get my diff displaying as desired, the below should be used in my global git config
```
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


## Usage

Create a symlink from you $XDG_CONFIG_HOME/zsh/.zshenv to your $HOME/.zshenv . Unfortunately zsh will only look for this env file in the home directory. However, once it is in place, everything else should work well!

