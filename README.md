# Neovim Config

My personal Neovim setup, built on top of the [LazyVim](https://github.com/LazyVim/LazyVim) starter template. This file documents the changes I've made on top of the defaults so I can remember why things behave the way they do.

## Customisations

### Options (`lua/config/options.lua`)

- `vim.g.root_spec = { "cwd" }` — forces LazyVim's project root detection to always use the current working directory. This stops pickers and file ops from jumping into a parent repo or LSP root when I just want to scope things to where I launched Neovim.

### Keymaps (`lua/config/keymaps.lua`)

- `<leader>p` → `:put` — paste the unnamed register on a new line below the cursor.
- `<leader>P` → `:put!` — paste the unnamed register on a new line above the cursor.

### Colorscheme (`lua/plugins/colorscheme.lua`)

Tokyonight, configured as:

- `style = "storm"`, but explicitly loaded as `tokyonight-night`.
- `transparent = true` — lets the terminal background show through.
- Comments rendered without italics.

### Dashboard (`lua/plugins/dashboard.lua`)

Overrides the `snacks.nvim` dashboard preset with a custom ASCII-art header and a tweaked menu. The menu items are mostly the LazyVim defaults wired through `Snacks.dashboard.pick` so they use whichever picker LazyVim is currently configured with.

### Enabled LazyExtras (`lazyvim.json`)

- `lazyvim.plugins.extras.formatting.prettier`
- `lazyvim.plugins.extras.lang.dotnet`
- `lazyvim.plugins.extras.lang.tailwind`
- `lazyvim.plugins.extras.lang.typescript`
- `lazyvim.plugins.extras.lang.vue`

### Other notes

- `.neoconf.json` enables `neodev` library support and the `lua_ls` neoconf plugin so editing this config gets full Neovim API completion.

## Installation

Standard LazyVim install — see the [LazyVim docs](https://lazyvim.github.io/installation). To use this config directly:

```sh
git clone git@github.com:wturneymizen/nvim.git ~/.config/nvim
nvim
```

Lazy will bootstrap itself and install everything on first launch.
