# Atom Clojure - Suggested Setup

>####TODO::To Review
> https://gist.github.com/jasongilman/d1f70507bed021b48625


This is one suggested way to setup Atom for an ideal Clojure development workflow.

This fixes indentation on newlines, handles parentheses, etc. The keybinding settings for enter (in keymap.cson) are important to get proper newlines with indentation at the right level. There are other helpers in init.coffee and keymap.cson that are useful for cutting, copying, pasting, deleting, and indenting Lisp expressions.


The [Atom documentation](https://atom.io/docs) is excellent. It's highly worth reading the flight manual.

## Pre-requisites

* [Atom](https://atom.io/)
* [Java 8 or greater](http://www.oracle.com/technetwork/java/javase/downloads/index.html)
* [Leiningen](http://leiningen.org/)

You can also use Protorepl with [Boot]() instead of Leiningen.

## Install Atom Packages

Required packages

* [ink]() - Proto REPL dependency used for inline display and the REPL output.
* [proto-repl](https://github.com/jasongilman/proto-repl) - Clojure REPL, autocompletion, etc.


Recommended packages

* lisp-paredit - Used only for proper indentation on newline and indenting blocks of code. (Hopefully Parinfer will handle all of these in the future)

* [proton]() - Spacemacs style menu and keybindings to make Atom easier to use (included Vim / Emacs keybinding support)
* [proto-repl-charts](https://github.com/jasongilman/proto-repl-charts) - Graphs and Charts
* tool-bar - Proto REPL uses this to display a tool bar with options.
* highlight-selected - highlights selected keywords throughout an editor.
* set-syntax - Easily change syntax with the command palette.


## Package Settings

### language-clojure

This is the built in package that comes with Atom for the Clojure Grammar. I find the default settings bad for the way that I work. I recommend changing them to the following.

* Auto Indent: unchecked
* Auto Indent On Paste: unchecked
* Non Word Characters: \()"':,;~@#$%^&{}[]`
* Scroll Past End: checked
* Tab Length: 1

Everything else is left at the default.

### bracket-matcher

Change autocomplete characters to `(), [], {}, "", “”, ‘’, «», ‹›` This disables closing of single quotes and back ticks.

### Proto REPL

Enabled Checkboxes: auto pretty print, auto scroll, display executed code, enable completions, prefer lein, all the refresh check boxes, show inline results, use clojure syntax.

### lisp-paredit

* Enabled: checked
* Strict: unchecked
* Indentation Forms: `try, catch, finally, /^let/, are, /^def/, fn, cond, condp, /^if.*/, /.*\/for/, for, for-all, /^when.*/, testing, doseq, dotimes, ns, routes, GET, POST, PUT, DELETE, extend-protocol, loop, do, case, with-bindings, checking, with-open`
* Keybindings Enable: unchecked

## Atom Settings

These are main Atom Settings related to Clojure that are different than the default.

* Auto Indent On Paste: unchecked
* Scroll Past End: checked
  * Due to [this autocomplete issue](https://github.com/atom/autocomplete-plus/issues/680) there is a lot of flashing from the autocomplete window that pops up. Scrolling down farther usually resolves the issue.

## styles.less

Atom has a place for custom styles. Place the following in your styles.less. This disables unbalanced lisp-paredit parentheses indicators in the REPL.

```Less
.proto-repl-repl::shadow .lisp-syntax-error .region {
  background-color: rgba(0, 0, 0, 0) !important;
}
```

## init.coffee and keymap.cson

The files included in this gist init.coffee and keymap.cson contain additional settings for Atom. You can paste their contents in the files after opening them in Atom.
