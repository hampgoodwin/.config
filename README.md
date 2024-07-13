# .config

my dot files

it's important to note that everything should live in $XDG_CONFIG_HOME.


## Dependencies

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

## To Do

Get a better local secrets management solution.. I tried enpass-cli, but that was a bit difficult since it prompts for a PW in all scenarios and chatgpt nvim plugin doesn't handle the prompt.
