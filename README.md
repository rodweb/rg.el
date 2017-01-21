# rg.el

[![License GPL 3](https://img.shields.io/badge/license-GPL_3-green.svg?style=flat)](LICENSE)
[![MELPA](http://melpa.org/packages/rg-badge.svg)](http://melpa.org/#/rg)
[![Build Status](https://travis-ci.org/dajva/rg.el.svg?branch=master)](https://travis-ci.org/dajva/rg.el)

Use [ripgrep](https://github.com/BurntSushi/ripgrep) in Emacs.

Ripgrep is a replacement for both grep like (search one file) and ag
like (search many files) tools. It's fast and versatile and written in
Rust. For some introduction and benchmarks, see
[ripgrep is faster than {grep, ag, git grep, ucg, pt, sift}](http://blog.burntsushi.net/ripgrep/).

This package let you run `ripgrep` like `grep` from within Emacs.

## Installation

This package is available on [MELPA](http://melpa.org/#/rg). Install
by doing `M-x package-install` <kbd>RET</kbd> `rg` from within emacs.

If you want to install manually just put `rg.el` somewhere in your
load path and add this to `init.el`

``` el
(require 'rg)
(global-set-key (kbd "M-s") 'rg)
```

`rg` is an autoloaded symbol so it's also possible to defer loading if
you have autoloading setup.

## Usage

Invoke by <kbd>M-x rg</kbd>. This works the same way as <kbd>M-x rgrep</kbd>,
i.e. you get an interactive prompt to enter search details. Universal
argument can be used as for `rgrep`.

[ripgrep](https://github.com/BurntSushi/ripgrep) has its own built in
mappings from type names to file name patterns that can be selected
from rg.el on invocation of `rg`. It's also possible to specify a
custom file name pattern in the files prompt.

### Mappings with special meaning

| Name | Meaning |
|-----|--------|
| all | all defined types including `rg-custom-type-aliases` |
| everything | all files, i.e. running rg without `--type` flag |
| custom | used internally in rg.el for mapping custom globs. Do not use this in `rg-custom-type-aliases` |


## Customize

Custom type patterns as for rgrep are supported via customizing of
`rg-custom-type-aliases`.

```el
(setq rg-custom-type-aliases
  '(("foo" .    "*.foo *.bar")
    ("baz" .    "*.baz *.qux")))
```

## License

See [LICENSE](LICENSE).