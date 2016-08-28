# number-lock.el
An Emacs package to exchange your number line with the mark above it.

For example, when you press `1`, `!` will be entered.
If `!` was binding to function other than `self-insert-command`, it will be
called.  But if Emacs have evil installed, it's only worked at insert-state.
Pressing `S+1` will enter `1`, etc.

It's a input method, so it's only worked on insert mode in current buffer,
so chords like `C-x 2` will act as normal, and the key won't be translated
in minibuffer.

中文说明： http://liu233w.github.io/blog/2016/08/21/programming-mode/

## Installation
Add `number-lock.el` to your load-path and then `(require 'number-lock)`.
Or just install it by melpa via `M-x package-install RET number-lock RET`.

## Usage
It will become one of your input method. Use `M-x set-input-method` to change to it
and `C-\` to enable it, then there will be a `&` in your modeline.

If you don't use other input methods, just put the code below into your config file:
``` emacs-lisp
(set-input-method 'number-lock)
```

If you use other input method, you can switch between it and number-lock by function
`number-lock-toggle-number-lock`.

## Alternative
[evil-swap-keys](https://github.com/wbolster/evil-swap-keys) use `key-translation-map` 
to swap keys. It support other key translations like `/?` `[{` and can be easily customized.
