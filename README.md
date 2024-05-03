# neovim-for-termux
preparing neovim for termux

### update dan upgrade
```bash
pkg update && pkg upgrade
```

### install beberapa package:
```bash
pkg install luajit python nodejs-lts ruby openjdk-11 clang perl php
```

### install neovim
```bash
pkg install neovim
```

#### Membuat file init.lua
```bash
touch ~/.local/share/nvim/init.lua
```
### pindah ke folder di mana file "init.lua" di buat.
```bash
cd ~/.local/share/nvim/
```

#### buka teks editor neovim dengan perintah:
```bash
nvim
```
-perintah explore.( :Ex )


### salin kode ini untuk file "init.lua"
```bash
local lazypath = vim.fn.stdpath("data") .. "/lazy/lazy.nvim"
if not (vim.uv or vim.loop).fs_stat(lazypath) then
    vim.fn.system({
        "git",
        "clone",
        "--filter=blob:none",
        "https://github.com/folke/lazy.nvim.git",
        "--branch=stable", -- latest stable release
        lazypath,
    })
end

vim.opt.rtp:prepend(lazypath)
require("misc")
require("lazy").setup("plugins")
```
 
