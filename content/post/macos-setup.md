---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "MacOS Setup"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2022-01-11T16:08:01-06:00
lastmod: 2022-01-12T17:25:13-06:00
featured: false
draft: false

---

I have recently moved between a few macOS machines and have had to repeat some common development configuration. I think it's best to document it here for both my future self and for others. Most of these are easy to install using [brew](https://brew.sh/).

## Editors
- `emacs`: `brew tap "d12frosted/emacs-plus" && brew install emacs-plus`
- `visual-studio-code`: all config is auto-synced using GitHub.
- `vim`: I just use [Tim Pope's sensible](https://github.com/tpope/vim-sensible) as I don't spend as much time on vim anymore

## Fonts
After `brew tap "homebrew/cask-fonts"`
- `font-mononoki` for Agda
- `font-fira-code` for everything else

## Packages
See https://github.com/k4rtik/shallow-backup/tree/master/packages (private link) for complete list. Here are some essentials:
- `brave-browser`
- [`brew cu`](https://github.com/buo/homebrew-cask-upgrade): `brew tap buo/cask-upgrade && brew cu pin brave-browser`
- `gh`
- `git`
- `hiddenbar`
- `htop`
- `hugo`
- `iterm2`
- `mailtrackerblocker`
- `rectangle`
- `rescuetime`
- `ticktick`
- `tree`
- [yt-dlp](https://github.com/yt-dlp/yt-dlp): `brew install yt-dlp/taps/yt-dlp`
- `zoom`

## Languages
- [Haskell](https://www.haskell.org/ghcup/)
- Agda (`brew install llvm@12`, add it to the PATH, and then `cabal install Agda`)
- [LaTeX](https://tug.org/texlive/acquire-netinstall.html)
- [OCaml](https://opam.ocaml.org/doc/Install.html) and Coq (`opam install coq`)
- Python3: `brew install python`
- [Rust](https://rustup.rs/)
  - `tealdeer`
  - `cargo-update`
  - `du-dust`
  - `ripgrep`

## Maintenance
I often issue the following command to keep most of the packages updated:
```shell
brewup && rustup update && cargo install-update -a && brew cu -a -y && tlmgr update --self --all && ghcup list -c available
```
where `brewup` is aliased to `brew update; brew upgrade; brew cleanup; brew doctor`

I tend to not auto-update opam packages as they can often break projects but I do maintain a `default` switch with the latest OCaml version and several [coq-platform](https://github.com/coq/platform/) releases, e.g.:
```shell
❯ opam switch
#  switch                                 compiler                    description
→  __coq-platform.2021.11.0~8.14~2021.11  ocaml-base-compiler.4.10.2  __coq-platform.2021.11.0~8.14~2021.11
   default                                ocaml.4.12.1                default
```
