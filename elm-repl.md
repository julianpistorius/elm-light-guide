## Elm REPL

![](/assets/repl.png)

Once connected to an elm-project in Light Table, a repl is started running in the background.This means you can evaluate statements from within any given elm editor.

**In an Elm file:**

* Position the cursor within the region of a top level expression and press ```cmd/ctrl+enter`.``
* You may also select a region that constitutes of one or more top level statements and press `cmd/ctrl+enter`

  **However** results are shown next to the first line of the selection, even though the actual result might be the related to the last statement \(or if an error, whatever line caused the error\)

* results are shown inline


You may reset the repl to start with a clean slate. Just select the command: \`Elm: Restart repl for current project\`

> NOTE: Results are currently only showed sensibly if you eval one top level statement at a time. Also the repl is shared between all elm editors for a given project.

**Anonymous repl**

You may also create a repl that isn't backed by a file

* Select the command `Elm repl: Open a elm repl`
* You may now eval code as for an Editor repl

> NOTE: You need a connected elm project for this to work

## 

