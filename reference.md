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
| Eval: Eval a form in editor | For use in repl to eval an expression \(must be valid in elm-repl\) | \[:editor "pmeta-enter" :eval-editor-form\] |
|  |  |  |
| Docs: Toggle documentation at cursor | Show documentation inline for a top level declaration \(reference\) | \[:editor "ctrl-d" :editor.doc.toggle\] |
| Docs: Search language docs | Open search bar to search for docs in all your projects modules \(including 3rd party packages\) | \[:app "ctrl-shift-d" :docs.search.show\] |



