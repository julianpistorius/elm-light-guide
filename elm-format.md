## Elm Format

In an effort to standardize how Elm code should be formatted, [elm-format](https://github.com/avh4/elm-format) was created. It is still in alpha, but I figured you might just as well start playing with it.

**Precondition**

You will need to install elm-format and make sure the executable is available in your path for it to work from the plugin.

**Format editor contents**

* With an elm file open, select the command `Elm: Format editor contents`

* If no errors the whole editor is formatted \(but any format changes aren't saved\)

* If there are any errors \(typically syntax errors\), a message is shown in the Statusbar and details can be found in the console


**Format top level expression**

If for some reason you find yourself wanting to just format a top level expression, this is the command for you.

* Place the cursor somewhere within the top level expression you wish to format

* Select the command `Elm: Format top level expression at point`


**Format a file**

With an elm file open, select the command `Elm: Format file`

> WARNING: Any unsaved changes will be lost when running this command. This command updates the file backing the editor in question.

**Adding keyboard shortcuts**

`````[:editor.elm.common "cmd-shift-l" :elm-format-expression]````[:editor.elm.common "cmd-ctrl-l" :elm-format-buffer]`````

**Configuring indent in Light Table**

`[:editor.elm.common :lt.objs.editor/tab-settings false 4 4] ;; or 2 2 if the war continues and things change back`

