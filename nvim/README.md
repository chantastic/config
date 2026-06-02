# Chan's Neovim config

Personal Neovim config stored in the `chantastic/config` repo.

This config is based on [kickstart.nvim](https://github.com/nvim-lua/kickstart.nvim), a small, documented starting point for Neovim configuration. Kickstart-derived portions remain attributed to the kickstart.nvim project and are used under its MIT license.

## Shape

- `init.lua` is the main config entrypoint.
- `lua/custom/plugins/` is the place for personal plugin modules.
- `lua/kickstart/plugins/` contains optional Kickstart example modules that can be enabled later.
- `.stylua.toml` keeps Lua formatting consistent.

## Agent Notes

- Keep the config readable and close to Kickstart's teaching style.
- Prefer small, named plugin modules under `lua/custom/plugins/` once a change grows beyond a few lines.
- The custom plugin loader exists in `lua/custom/plugins/init.lua`, but `init.lua` currently leaves `require 'custom.plugins'` commented out. Uncomment that line before relying on files in `lua/custom/plugins/`.
- The `kickstart.plugins.*` example modules are intentionally kept as scaffolding. Enable them by uncommenting the matching `require` lines near the bottom of `init.lua`.
- Do not track generated files such as `doc/tags` or `nvim-pack-lock.json` unless we intentionally decide to pin plugin versions.

## Basic Use

Open Neovim normally:

```sh
nvim
```

Plugins are managed with Neovim's built-in `vim.pack`. Useful commands:

```vim
:lua vim.pack.update(nil, { offline = true })
:lua vim.pack.update()
```

