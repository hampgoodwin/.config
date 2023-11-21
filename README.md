# .config

my dot files

it's important to note that everything should live in $XDG_CONFIG_HOME.


## Dependencies

Install NVM to manage node versions, then install a global node version. This will allow our mason.nvim to install tsserver, eslint_d and prettier_d.
Install Go.
Install Rust.
Install Ollama for local llm running and code suggestions/ai chat.

## Usage

Create a symlink from you $XDG_CONFIG_HOME/zsh/.zshenv to your $HOME/.zshenv . Unfortunately zsh will only look for this env file in the home directory. However, once it is in place, everything else should work well!

## To Do

Get a better local secrets management solution.. I tried enpass-cli, but that was a bit difficult since it prompts for a PW in all scenarios and chatgpt nvim plugin doesn't handle the prompt.
