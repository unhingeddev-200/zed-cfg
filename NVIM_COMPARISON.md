# Neovim to Zed Configuration Comparison

This document shows how your Neovim configuration maps to Zed.

## Configuration Files Analyzed

Your nvim config that was replicated:
- `~/.config/nvim/init.lua` - Main config with LSP setups
- `~/.config/nvim/lua/config/options.lua` - Editor options
- `~/.config/nvim/lua/config/keymaps.lua` - Custom keymaps
- `~/.config/nvim/lua/config/autocmds.lua` - Autocmds (auto-save, etc.)
- `~/.config/nvim/lua/plugins/*.lua` - Plugin configurations

## Editor Settings Comparison

| Feature | Neovim | Zed | Status |
|---------|--------|-----|--------|
| Vim mode | ✅ | ✅ | ✅ Replicated |
| Relative line numbers | ✅ | ✅ | ✅ Replicated |
| Auto-save on InsertLeave/TextChanged | ✅ | ✅ | ✅ Replicated (via autosave) |
| Format on save | ✅ | ✅ | ✅ Replicated |
| ttimeoutlen = 100 | ✅ | N/A | ⚠️ Zed doesn't expose this |
| Cursor blink | Off | Off | ✅ Replicated |
| System clipboard | ✅ | ✅ | ✅ Replicated |

## LSP Configuration Comparison

### ✅ Fully Replicated LSPs

| Language | Neovim LSP | Zed LSP | Notes |
|----------|-----------|---------|-------|
| Go | gopls | gopls | All settings replicated (gofumpt, hints, codelenses) |
| Rust | rust_analyzer | rust_analyzer | Diagnostics disabled as configured |
| Zig | zls | zls | ✅ Configured |
| Elixir | elixir-ls | elixir-ls | Custom path replicated |
| JavaScript/TypeScript | Deno preferred | Deno preferred | ts_ls disabled, Deno enabled |
| HTML | html | html | ✅ |
| CSS | cssls | cssls | ✅ |
| Tailwind | tailwindcss | tailwindcss | ✅ |
| YAML | yamlls | yaml-language-server | ✅ |
| JSON | jsonls | json-language-server | ✅ (built-in) |
| Python | pyright | pyright | ✅ |
| C/C++ | clangd | clangd | ✅ |

### ⚠️ Partially Supported / Needs Manual Setup

| Language | Neovim LSP | Zed Status |
|----------|-----------|-----------|
| AutoHotkey | autohotkey_lsp | ❌ Not available in Zed |
| Fish shell | fish-lsp | ❌ Not available in Zed |
| Helm | helm_ls | ❌ Not available in Zed |
| Protocol Buffers | protols | ❌ Not available in Zed |
| Docker | dockerls | ⚠️ May need extension |
| Cue | cue | ⚠️ May need extension |
| Dart | dartls | ⚠️ Available via Flutter extension |
| SQL (sqls) | sqls + .sqls.yaml | ❌ Not directly supported |

## Keybindings Comparison

### ✅ Fully Replicated

| Neovim Binding | Zed Binding | Action |
|----------------|-------------|--------|
| `<C-x>` | `Ctrl+X` | Toggle terminal |
| `<C-c>` | `Ctrl+C` | Escape (all modes) |
| `<C-l>` | `Ctrl+L` | Enter/newline |
| `<C-m>` | `Ctrl+M` | Clear marks |
| `<leader>e` | `Space E` | Toggle file explorer |
| `<leader>o` | `Space O` | Insert blank line |
| `<C-e>a` | `Ctrl+E A` | Insert `_` |
| `<C-e>d` | `Ctrl+E D` | Insert `<>` |
| `<C-e>l` | `Ctrl+E L` | Insert `=` |
| `<C-e>j` | `Ctrl+E J` | Insert `!=` |
| `<C-e>h` | `Ctrl+E H` | Insert `==` |
| `<C-e>n` | `Ctrl+E N` | Insert `{}` |
| `<C-e>b` | `Ctrl+E B` | Insert `{{}}` |
| `<C-e>m` | `Ctrl+E M` | Insert `[]` |
| `<C-e>e` | `Ctrl+E E` | Search in buffer |
| `<C-o>` (insert) | `Ctrl+O` | Enter/newline |
| `<C-b>` (insert) | `Ctrl+B` | Paste |
| `<C-k>` (blink.cmp) | `Ctrl+K` | Previous completion |
| `<C-j>` (blink.cmp) | `Ctrl+J` | Next completion |
| `<leader>cli` | `Space C L I` | LSP info |
| `<leader>clr` | `Space C L R` | Restart LSP |
| `<leader>cp` | `Space C P` | Copy file path |
| `gd` | `G D` | Go to definition |
| `gD` | `G Shift+D` | Go to declaration |
| `gI` | `G I` | Go to implementation |
| `gr` | `G R` | Find references |
| `gy` | `G Y` | Go to type definition |
| `K` | `Shift+K` | Hover |
| `<leader>ca` | `Space C A` | Code actions |
| `<leader>cr` | `Space C R` | Rename |
| `<leader>hj` | `Space H J` | Paste |

### ⚠️ Partially Replicated / Different

| Neovim | Zed Equivalent | Notes |
|--------|----------------|-------|
| `<leader>D` (DBUI) | N/A | Database UI not available |
| `<leader>S` (Execute Query) | N/A | Database features not available |
| DAP keybindings (`<leader>db`, etc.) | `Space D B` | Limited debug support |
| `<leader>m` (MarkdownPreview) | Built-in preview | Zed has built-in markdown preview |
| `<leader>tg` (templ generate) | Terminal | Run in terminal instead |
| Snippet editing (`<leader>hk`) | N/A | Different snippet system |

### 🔧 Language-Specific Insert Mode Mappings

Your autocmds for language-specific mappings:
- **Go**: `<C-e>k` → `:=`
- **Elixir**: `<C-e>k` → `->`

❌ **Not directly replicable** - Zed's keymap system doesn't support filetype-specific insert mode mappings in the same way. **Workaround**: Use snippets or type manually.

## Plugin Ecosystem Comparison

### Neovim Plugins → Zed Equivalents

| Neovim Plugin | Zed Equivalent | Status |
|---------------|----------------|--------|
| lazy.nvim | Zed extensions | Different system |
| LazyVim | Built-in | Zed has batteries included |
| blink.cmp | Built-in completion | ✅ Similar functionality |
| snacks.picker | Built-in file finder | ✅ Similar with `Ctrl+P` |
| neo-tree | Built-in project panel | ✅ `Space E` |
| which-key | Command palette | ⚠️ Different UX |
| trouble.nvim | Diagnostics panel | ⚠️ Less feature-rich |
| todo-comments | Extension available | ⚠️ Check extension marketplace |
| nvim-treesitter | Built-in syntax | ✅ Zed uses tree-sitter |
| LuaSnip | Built-in snippets | ⚠️ Different syntax |
| nvim-dap / dapui | Limited debug support | ❌ Much less mature |
| persistence.nvim | Session restore | ⚠️ Zed auto-restores |
| activitywatch.nvim | N/A | ❌ Not available |
| ts-comments | Built-in | ✅ |

### Themes

Your nvim themes:
- bamboo, catppuccin, everforest, flexoki, gruvbox, kanagawa, matteblack, monokai-pro, nord, rose-pine, tokyonight, dracula, aether/demon

Zed themes:
- Tokyo Night (set as default) ✅
- Check extension marketplace for others
- Different theme system

## Autocmd Replication

| Neovim Autocmd | Zed Equivalent | Status |
|----------------|----------------|--------|
| VimEnter keymaps | keymap.json | ✅ |
| TermEnter keymaps | Terminal context in keymap | ✅ |
| BufEnter (Go/Elixir insert maps) | N/A | ❌ Not directly possible |
| InsertLeave, TextChanged (auto-save) | autosave settings | ✅ |
| BufEnter (sqls config) | N/A | ❌ SQL LSP not supported |
| BufEnter (fish-lsp) | N/A | ❌ fish-lsp not available |

## Features Present in Neovim but Not Zed

1. **Custom snippet loading** from `~/.config/luasnip`
2. **Comfy line numbers** with custom labels (1, 2, 3, 5, 11, 12, etc.)
3. **Database UI** (DBUI plugin)
4. **Advanced debugging** (nvim-dap with full UI)
5. **ActivityWatch** integration
6. **Which-key** style keybinding hints
7. **Trouble.nvim** style diagnostics viewer
8. **Custom theme hot-reloading**
9. **SQL query execution** within editor
10. **Filetype-specific insert mode** keymaps via autocmd

## Features in Zed but Not Your Neovim Config

1. **Collaborative editing** (built-in)
2. **AI assistant** (Claude integration)
3. **Native UI** (GPU-accelerated)
4. **Faster startup** (no plugin loading delay)
5. **Built-in git integration** (inline blame, etc.)
6. **Instant grep** (very fast project search)
7. **Language-aware git diffs**
8. **Project-wide symbol search**

## Recommendations

### Immediate Next Steps
1. ✅ **Configuration is complete** - settings.json and keymap.json are ready
2. 🔧 **Install LSP servers** - Run the install commands from README.md
3. 🎨 **Try the theme** - Tokyo Night is set, explore others via `Ctrl+Shift+P` → "theme"
4. ⚡ **Test your workflow** - Open a project and try your keybindings

### Adjustments You May Need
1. **SQL work** - Use a separate SQL client (no DBUI equivalent)
2. **Debugging** - Consider keeping nvim for complex debugging sessions
3. **Custom snippets** - Port your LuaSnip snippets to Zed's format if needed
4. **Language-specific insert mappings** - Create Zed snippets for `:=` and `->`
5. **ActivityWatch** - May need to track time differently

### Things That "Just Work"
- ✅ Basic vim motions and commands
- ✅ LSP (go to definition, hover, rename, etc.)
- ✅ File finding and project search
- ✅ Terminal integration
- ✅ Git integration
- ✅ Auto-save and format on save
- ✅ Multi-cursor editing
- ✅ Code folding

## Performance Comparison

| Aspect | Neovim | Zed |
|--------|--------|-----|
| Startup time | ~100-500ms (with plugins) | ~50-100ms |
| File indexing | Via plugins | Built-in, very fast |
| Large file handling | Excellent | Excellent |
| Project search | Fast (with rg) | Very fast (built-in) |
| LSP responsiveness | Good | Excellent |
| Memory usage | Low-Medium | Medium |

## Philosophy Differences

**Neovim**: Extremely customizable, modal editing, plugin ecosystem, configuration in Lua/Vimscript
**Zed**: Batteries included, modern UI, minimal configuration, built-in collaboration, Rust-based performance

## Summary

Your Zed configuration now mirrors your Neovim setup in these key areas:
- ✅ **80-90% of daily workflow** should feel familiar
- ✅ **Core keybindings** are replicated
- ✅ **LSP functionality** matches (for supported languages)
- ✅ **Editor behavior** (auto-save, format, etc.) is similar
- ⚠️ **Some advanced features** (DBUI, complex debugging) are not available
- ⚠️ **Plugin ecosystem** is different

**Bottom line**: Zed should feel like a faster, more modern version of your Neovim setup for most coding tasks, but you may want to keep Neovim around for specialized workflows like database work or complex debugging.
