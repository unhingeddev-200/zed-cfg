# Zed Keybindings Quick Reference

This is a quick reference for your custom keybindings that match your Neovim config.

## Essential Keybindings

### Terminal
| Key | Action |
|-----|--------|
| `Ctrl+X` | Toggle terminal (same as nvim!) |

### Core Navigation
| Key | Action |
|-----|--------|
| `Ctrl+C` | Escape (all modes) |
| `Ctrl+L` | Enter/Newline |
| `Ctrl+M` | Clear marks |
| `Space E` | Toggle file explorer |
| `Space Space` | Command palette |

### File Operations
| Key | Action |
|-----|--------|
| `Ctrl+P` | File finder |
| `Space F F` | File finder (alternate) |
| `Space /` | Search in project |
| `Ctrl+Shift+F` | Search in project (alternate) |
| `Space C P` | Copy file path |

### LSP & Code Navigation
| Key | Action |
|-----|--------|
| `G D` | Go to definition |
| `G Shift+D` | Go to declaration |
| `G I` | Go to implementation |
| `G R` | Find references |
| `G Y` | Go to type definition |
| `Shift+K` | Hover documentation |
| `Space C A` | Code actions |
| `Space C R` | Rename symbol |
| `Space C D` | Show diagnostics |
| `]D` | Next diagnostic |
| `[D` | Previous diagnostic |
| `Space C L I` | LSP info |
| `Space C L R` | Restart LSP |

### Insert Mode Helpers
| Key | Inserts |
|-----|---------|
| `Ctrl+E A` | `_` (underscore) |
| `Ctrl+E D` | `<>` |
| `Ctrl+E L` | `=` |
| `Ctrl+E J` | `!=` |
| `Ctrl+E H` | `==` |
| `Ctrl+E N` | `{}` |
| `Ctrl+E B` | `{{}}` |
| `Ctrl+E M` | `[]` |
| `Ctrl+O` | Enter (newline) |
| `Ctrl+B` | Paste |

### Completion
| Key | Action |
|-----|--------|
| `Ctrl+J` | Next completion |
| `Ctrl+K` | Previous completion |

### Buffer Management
| Key | Action |
|-----|--------|
| `Ctrl+Tab` | Next tab |
| `Ctrl+Shift+Tab` | Previous tab |
| `Space B D` | Close buffer |
| `Space B Shift+D` | Close other buffers |

### Search
| Key | Action |
|-----|--------|
| `Ctrl+E E` | Search in buffer |
| `/` | Search (vim native) |

### Debugging
| Key | Action |
|-----|--------|
| `Space D B` | Toggle breakpoint |

### Miscellaneous
| Key | Action |
|-----|--------|
| `Space O` | Insert blank line |
| `Space H J` | Paste (in normal mode) |
| `Ctrl+Shift+O` | Symbol outline |

## Vim Mode Commands

Standard vim commands work as expected:
- `i`, `a`, `o`, `O` - Insert modes
- `v`, `V`, `Ctrl+V` - Visual modes
- `d`, `y`, `c`, `p` - Delete, yank, change, paste
- `u`, `Ctrl+R` - Undo, redo
- `:w`, `:q`, `:wq` - Write, quit, write & quit
- And many more!

## Tips

1. **Auto-save is enabled** - Files save automatically on focus change and after 1 second of inactivity (like your nvim config)
2. **Format on save is enabled** - Code will auto-format when you save
3. **Relative line numbers** - Use `5j`, `10k`, etc. to jump lines
4. **System clipboard** - Yank/paste works with system clipboard automatically
5. **Inlay hints** - Type hints appear inline (like your gopls config)

## Command Palette

Press `Ctrl+Shift+P` or `Space Space` to open command palette and type:
- `file finder` - Find files
- `theme selector` - Change theme
- `lsp` - LSP-related commands
- `terminal` - Terminal commands
- `format` - Format document
- `outline` - Show symbol outline
- `diagnostics` - Show diagnostics

## Differences from Neovim

Some things work differently:
1. **No which-key** - Use command palette instead
2. **Limited debugging** - DAP UI not as feature-rich
3. **Different plugin system** - Zed extensions instead of lazy.nvim
4. **No DBUI** - Database UI not available
5. **Simpler terminal** - Not as integrated as snacks.terminal

## Getting Help

- Command palette: `Ctrl+Shift+P`
- Zed docs: https://zed.dev/docs
- Settings: `zed: open settings`
- Keymap: `zed: open keymap`
- Default settings: `zed: open default settings`
