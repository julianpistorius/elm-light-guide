## Misc

**Select top-level statements**

If you wish to select a top level statement just invoke the command `Elm: Select top level expression from current expression`

> NOTE: The selection algorithm is sort of naive, so there might be cases when the selection doesn't work out quite as you'd hope. In most cases it should work sensibly though.

**To enable as keyboard shortcut in both elm editors and anonymous elm repl**

`[:editor.elm.common "alt-shift-s" :elm.select.top.level] ; modify keybinding to your liking !`

**Code folding**

You can fold code by invoking the editor command \``Editor: Fold code at cursor`\`. It will fold the code based on the given indentation level your cursor is at.

