# Zed Configuration - Neovim Mimic

This Zed configuration has been set up to closely mimic your Neovim (LazyVim) configuration.

## Overview

Your Zed editor is now configured with:
- **Vim mode enabled** with system clipboard integration
- **Relative line numbers** (like your nvim setup)
- **Auto-save** functionality (mimicking your InsertLeave/TextChanged autocmd)
- **LSP servers** configured to match your nvim setup
- **Custom keybindings** that mirror your nvim keymaps
- **Tokyo Night theme** (similar to your nvim theme collection)

## Key Features Replicated

### 1. Editor Settings
- ✅ Relative line numbers
- ✅ Auto-save on focus change and after 1 second delay
- ✅ Format on save
- ✅ Remove trailing whitespace on save
- ✅ Comfortable line height
- ✅ No cursor blink

### 2. LSP Configuration

All your LSP servers have been configured:

#### Go (gopls)
- Gofumpt formatting enabled
- All inlay hints enabled (parameter names, types, etc.)
- Code lenses for tests, generate, etc.
- Analysis tools configured (unusedparams, nilness, etc.)
- Hard tabs and tab_size: 4

#### Rust (rust_analyzer)
- Diagnostics disabled (matching your config)

#### Other LSPs
- ✅ Zig (zls)
- ✅ Elixir (elixir-ls) - using your custom path
- ✅ Deno (preferred over TypeScript)
- ✅ TypeScript (disabled in favor of Deno)
- ✅ YAML (yaml-language-server)
- ✅ Tailwind CSS
- ✅ HTML, CSS
- ✅ Python (Pyright)
- ✅ C/C++ (clangd)

**Note**: Some LSPs from your nvim config (like autohotkey_lsp, fish-lsp, helm_ls, protols, dockerls, cue) may need to be installed separately or may not be directly supported in Zed yet.

### 3. Keybindings

Your custom keybindings have been replicated:

#### Terminal
- `Ctrl+X` - Toggle terminal (matches your nvim binding exactly)

#### Core Vim Mappings
- `Ctrl+C` - Escape (in all modes)
- `Ctrl+L` - Enter/Newline (in normal and insert modes)
- `Ctrl+M` - Clear marks (like your `:delm!`)
- `Ctrl+E E` - Search in buffer (like `/`)

#### Leader Key Mappings (Space)
- `Space E` - Toggle file explorer (like your NeoTree)
- `Space O` - Insert blank line (matching your custom mapping)
- `Space C L I` - LSP Info/Hover
- `Space C L R` - Restart LSP
- `Space C P` - Copy file path
- `Space F F` - File finder
- `Space /` - Search in project
- `Space Space` - Command palette

#### Insert Mode Special Characters
All your `Ctrl+E` insert mode mappings:
- `Ctrl+E A` - Insert `_`
- `Ctrl+E D` - Insert `<>`
- `Ctrl+E L` - Insert `=`
- `Ctrl+E J` - Insert `!=`
- `Ctrl+E H` - Insert `==`
- `Ctrl+E N` - Insert `{}`
- `Ctrl+E B` - Insert `{{}}`
- `Ctrl+E M` - Insert `[]`

#### Completion (mimicking blink.cmp)
- `Ctrl+J` - Next completion item
- `Ctrl+K` - Previous completion item
- `Ctrl+B` - Paste in insert mode

#### LSP Navigation
- `G D` - Go to definition
- `G Shift+D` - Go to declaration
- `G I` - Go to implementation
- `G R` - Find all references
- `G Y` - Go to type definition
- `Shift+K` - Hover documentation
- `Space C A` - Code actions
- `Space C R` - Rename symbol
- `Space C D` - Show diagnostics
- `]D` - Next diagnostic
- `[D` - Previous diagnostic

#### Buffer Management
- `Ctrl+Tab` - Next tab/buffer
- `Ctrl+Shift+Tab` - Previous tab/buffer
- `Space B D` - Close current buffer
- `Space B Shift+D` - Close other buffers

#### Debugging (Limited Support)
- `Space D B` - Toggle breakpoint

**Note**: Your DAP (Debug Adapter Protocol) keybindings from nvim are partially mapped, but Zed's debugging support is still limited compared to nvim-dap.

### 4. Language-Specific Settings

Configured for all your languages:
- **Go**: Hard tabs, 4-space tab size, organize imports on save
- **Rust**: 4-space tabs, format on save
- **JavaScript/TypeScript/TSX**: 2-space tabs, format on save
- **Elixir**: 2-space tabs, format on save
- **Python**: 4-space tabs, format on save
- **C/C++**: 2-space tabs, format on save
- **HTML/CSS/JSON/YAML**: 2-space tabs, format on save

### 5. Features Configured
- ✅ Inlay hints (matching your gopls hints)
- ✅ Git inline blame
- ✅ Auto-close brackets
- ✅ Completions on input
- ✅ Format on save
- ✅ Terminal with bash shell

## What's Different from Neovim

Some features from your nvim config that work differently or aren't available in Zed:

1. **Plugins**: Zed doesn't have the same plugin ecosystem. Features like:
   - ActivityWatch integration
   - Custom snippet loading from `~/.config/luasnip`
   - Comfy line numbers with custom labels
   - DAP UI (debugging UI is more limited)
   - Database UI (DBUI)
   - Snacks.nvim features
   - Which-key
   - Trouble.nvim

2. **Language-specific insert mode mappings**: Your `BufEnter` autocmds for Go (`:=`) and Elixir (`->`) via `Ctrl+E K` aren't directly replicable in Zed's keymap system per-filetype in insert mode. You may need to use snippets for this.

3. **LSP Servers**: Some specialized LSPs from your config may need manual installation:
   - AutoHotkey LSP
   - Fish LSP
   - Helm LS
   - Protols
   - Docker LS
   - Cue

4. **Themes**: Your extensive theme collection (bamboo, catppuccin, everforest, flexoki, gruvbox, kanagawa, etc.) isn't directly available. Zed has its own theme system. Tokyo Night is set as the default to match your dark theme preference.

## Installation Requirements

To use all configured LSP servers, ensure you have these installed:

```bash
# Go
go install golang.org/x/tools/gopls@latest

# Rust
rustup component add rust-analyzer

# Zig
# Install via your package manager or from zigtools.org

# Deno
curl -fsSL https://deno.land/install.sh | sh

# YAML
npm install -g yaml-language-server

# Tailwind CSS
npm install -g @tailwindcss/language-server

# Python
pip install pyright

# Elixir
# Already using your custom path: /home/havok/bin/lsp/elixir-ls/language_server.sh
```

## Tips for Using Zed with Vim Mode

1. **Command Palette**: `Ctrl+Shift+P` or `Space Space` (opens command palette, similar to which-key)
2. **File Finder**: `Ctrl+P` or `Space F F` (like snacks.picker)
3. **Project Search**: `Ctrl+Shift+F` or `Space /` (like telescope grep)
4. **Terminal**: `Ctrl+X` (exactly like your nvim config!)
5. **Vim commands**: Most standard vim commands work in vim mode
6. **Settings**: Press `Ctrl+Shift+P` and type "zed: open settings" to modify settings.json
7. **Keymaps**: Press `Ctrl+Shift+P` and type "zed: open keymap" to modify keymap.json

## Next Steps

1. **Install missing LSP servers** if needed
2. **Test your workflow** - some adjustments might be needed
3. **Customize themes** - explore Zed's built-in themes or install extensions
4. **Add snippets** - Zed has its own snippet system if you need your custom snippets
5. **Explore Zed extensions** - Check the extension marketplace for additional functionality

## Configuration Files

- `~/.config/zed/settings.json` - Main settings file
- `~/.config/zed/keymap.json` - Custom keybindings
- `~/.config/zed/README.md` - This file

## Troubleshooting

If something doesn't work as expected:

1. Check LSP status in the status bar
2. Open command palette and search for "lsp: log"
3. Verify LSP servers are installed and in PATH
4. Check the Zed documentation: https://zed.dev/docs
5. Join Zed Discord for community support

---

**Note**: This configuration aims to replicate your Neovim workflow as closely as possible, but Zed and Neovim are fundamentally different editors. Some adjustments to your workflow may be necessary, but the core functionality should feel familiar.
