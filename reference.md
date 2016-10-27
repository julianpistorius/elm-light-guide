# Reference

## Commands

| Command | Description | Mappable command \(user.keymap\) |
| --- | --- | --- |
| Elm: Lint selected file | Lint the current elm file and display results inline | \[:editor.elm "&lt;keychord&gt;" :elm.lint\] |
| Elm: Format file | Runs Elm format on the currently \(saved\) fie | \[:editor.elm "&lt;keychord&gt;" :elm-format\] |
| Elm: Format editor contents | Runs Elm format on the current editors content | \[:editor.elm "&lt;keychord&gt;" :elm-format-buffer\] |
| Elm: Format top level expression | Run elm format for current top level expression | \[:editor.elm "&lt;keychord&gt;" :elm-format-expression\] |
| Elm: View current file in browser \(elm-reactor\) | Opens current elm file in inline browser served by Elm reactor | \[:editor.elm "&lt;keychord&gt;" :elm-browse\] |
| Elm: Show module browser | Display listing of project modules in the right hand bar | \[:editor.elm "&lt;keychord&gt;" :show-modulebrowser\] |
| Elm: Make selected file | Make current elm file to a js file with the same name | \[:editor.elm "&lt;keychord&gt;" :elm-make\] |
| Elm: Preview doc for selected file | For an exposed package module, run this command to get a preview tab. The tab is updated as you type | \[:editor.elm "&lt;keychord&gt;" :elm.docpreview\] |
| Elm repl: Open elm repl | Open an anyonymous elm repl \(not file backed\) for the current elm project \(need to be in an elm editor when invoking\) | \[:editor.elm "&lt;keychord&gt;" :elmrepl\] |
| Elm: Restart repl for current project | Restart the repl to clear out any history | \[:editor.elm "&lt;keychord&gt;" :elm.restart-repl\] |
| Elm: Select top level expression from current cursor position | Select top level expression | \[:editor.elm "&lt;keychord&gt;" :elm.select.top.level\] |
| Elm: Show project packages | Show the package manager to manage your projects packages | \[:editor.elm "&lt;keychord&gt;" :show-project-packages\] |
| Elm: Show dependency graph | Show dependency graph for your projects packages | \[:editor.elm "&lt;keychord&gt;" :show-elm-dep-graph\] |
| Elm: Reload AST | Reload the project AST \(all files including 3rd party packages\). Shouldn't need to use, but if things come really out of sync, maybe because of outside events etc. It might be worth a try to see if things come back on track | \[:editor.elm "&lt;keychord&gt;" :elm.reload.ast\] |
| Elm: Expose top level declaration | Expose a top level declaration \(cursor placed on name\) from your module | \[:editor.elm "&lt;keychord&gt;" :elm.expose-top-level\] |
| Elm: Unexpose top level declaration | Reverse of the above | \[:editor.elm "&lt;keychord&gt;" :elm.unexpose-top-level\] |
|  |  |  |
| Linter: Move to next result | If the linter has more than one message, lets you jump to the next linter result \(using the keyboard!\) | \[:editor.elm "&lt;keychord&gt;" :editor.next.lint-result\] |
| Linter: Move to previous result | Same as above, but moves backwards | \[:editor.elm "&lt;keychord&gt;" :editor.prev.lint.result\] |
| Linter: Show details at cursor | Place the cursor at something marked as an error or warning \(red or yellow squiggly line\) and invoke this command to view the details | \[:editor.elm "&lt;keychord&gt;" :editor.linter.details\] |
|  |  |  |
| Editor: Jump to defintion at cursor | Default Light Table command. Jumps to the definition of a given top level declaration reference | \[:editor "ctrl-j" :editor.jump-to-definition-at-cursor\] |
| Editor: Jump back to where you jumped from | Jump back to where you came from | \[:editor "ctrl-j-b" :editor.unjump\] |
| Editor: Fold code at cursor | Fold code at cursor. A small symbol indicates folded code. Invoke again to unfold | \[:editor "ctrl-=" :editor.fold-code\] |
|  |  |  |
|  |  |  |
| Eval: Eval a form in editor | For use in repl to eval an expression \(must be valid in elm-repl\) | \[:editor "pmeta-enter" :eval-editor-form\] |
|  |  |  |
| Docs: Toggle documentation at cursor | Show documentation inline for a top level declaration \(reference\) | \[:editor "ctrl-d" :editor.doc.toggle\] |
| Docs: Search language docs | Open search bar to search for docs in all your projects modules \(including 3rd party packages\) | \[:app "ctrl-shift-d" :docs.search.show\] |

> It's also possible to have a keyboard short-cut execute several commands in order. You can see an example of that in the next chapter where we set up a cusotm shortcut for saving, formatting the file and finally linting the file.

## Useful configurations {#useful-configurations}

**Enable autoclose brackets in Light Table**

When you type for example `(` Light Table will automatically add `)` and place the cursor inside the parens. Works for \[ `(`, `[`, `"`, `'`, `{`\]

`[:editor :lt.objs.editor/autoclose-brackets] ; This behavior enables auto close brackets`

**Lint and format on save**

Add this to your user keymap \(Ctrl-Space -&gt; "Settings: User keymap"\)

`[:editor.elm "cmd-s" :save :elm-format :elm.lint]`

**Clear inline results**

Wipe out lint messages, inline results from repling and the console. To enable add the following \(Ctrl-Space -&gt; "Settings: User behaviours"

`[:app "cmd-shift-e" :clear-console :clear-inline-results :editor.linter.remove-all]`

## First time Light Table User ?

If you have just started using Light Table you'll probably find that you are missing keyboard short-cuts for navigating between editors, tabs etc. In this chapter some samples for the most commonly used shortcuts you might want to add to your keyboard mapping.

### Modifying your keymapping

* Open command bar \(ctrl-space\)
* Find and select : `Settings: User keymap`
* Copy\/paste\/modify from the examples below
* Save the file 
* Try them out !

### Some default shortcuts worth mentioning

* New file: `File: New File` -&gt; `cmd-n`
* Open\/search for file \(in your workspace\) : `cmd-o`
* Open file in filesystem : `File : Open File` -&gt; `cmd-shift-o`

### Navigation related keyboard shortcuts

```clojure

 ;; Add a new tab with the in-buildt chromium browser that is shipped with LT
 [:app "cmd-shift-b" :add-browser-tab]

 ;; Create a new tabset (container for tabs)
 [:app "ctrl-shift-t" :tabset.new]

 ;; Move to the next/previous tabset (if more than one)
 [:app "cmd-alt-right" :tabset.next]
 [:app "cmd-alt-left" :tabset.prev]

 ;; Move to next/prev Tab (within a given tabset)
 [:app "ctrl-shift-right" :tabs.next]
 [:app "ctrl-shift-left" :tabs.prev]

 ;; Move a given tab to the next/previous tabset
 [:app "cmd-ctrl-right" :tabs.move-next-tabset]
 [:app "cmd-ctrl-left" :tabs.move-prev-tabset]

 ;; Move a given TAB to a new tabset to the right of the current tabset
 [:app "cmd-ctrl-n" :tabset.new :tabs.move-next-tabset]

 ;; Clear console, any inline results and linter markers
 [:app "cmd-shift-e" :clear-console :clear-inline-results :editor.linter.remove-all]


 ;; Toggle display of the console 
 [:app "cmd-shift-t" :toggle-console]

 ;; Toggle display of the workspace tree
 [:app "cmd-shift-w" :workspace.show]
```

### Some handy generic editor shortcuts

```clojure
 ;; Show find bar in current editor
 [:editor "cmd-f" :find.show]

 ;; Scroll page up/down
 [:editor "alt-d" :editor.page-down]
 [:editor "alt-u" :editor.page-up]

 ;; Custom keybinding for zoom in/out
 [:editor "ctrl-z-i" :window.zoom-in]
 [:editor "ctrl-z-o" :window.zoom-out]

 ;; Jump/unjump to definition (for language plugins that support it... like the elm-light plugin)
 [:editor "ctrl-j" :editor.jump-to-definition-at-cursor]
 [:editor "ctrl-shift-j" :editor.unjump]

 ;; Sublime style line kill
 [:editor "ctrl-k" :editor.kill-line]

 ;; Duplicate line
 [:editor "cmd-d" :editor.sublime.duplicateLine]

 ;; Move to the beginning of a line (bar tabs/spaces)
 [:editor "ctrl-left" :editor.line-start-smart]

 ;; Multiple cursors. First time selects word, next invocation selects next occurence of selection in Editor
 [:editor "ctrl-g" :editor.sublime.selectNextOccurrence]

 ;; Select between brackets
 [:editor "alt-s" :editor.sublime.selectBetweenBrackets]

```

