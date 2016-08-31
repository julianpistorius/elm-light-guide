# Features

Whenever this chapter refers to command. That is a Light Table command which you may \(and probably should\) provide a custom keyboard shortcut to.

**To define a shortcut in Light Table:**

1. Open the command bar \(ctrl-space\)
2. Search and find `Settungs: User keymap` and select that
3. Define your short cuts as per the example below

`[:editor "alt-enter" :editor.linter.details]  ;; command to display details for a marked error or warning after linting`

To view all available commands and suggestions tips on how you might want to do more advanced configurations, check out the [Reference chapter](/reference.md)

## Linting

![](/assets/lint.png)

To lint an elm file use the command: `Elm: Lint selected file`

* Errors are marked with red underline, warnings with yellow underline
* Errors\/warnings in dependent files are shown in the console

**Details and navigation**

* To view details about an error or warning place your cursor inside an underline range and select the command `Linter: Show details at cursor`

* To move to next lint result select command `Linter: Move to next result`

* To move to previous lint result select command `Linter: Move to previous result`


> NOTE: Rember to save. Linting works on saved files !

You can also configure the plugin to automatically Lint on Save. See the [Reference](/reference.md) section for details

**Quickfixes**

For some warnings and errors there are shortcut operations to do fixes in your code.

* **Unused import**: Allows you to quickly remove an unused import
* **Missing type annotation**:  Facility to add type annotation \(top level expressions only\)
* **Type mismatch**: Facility to fix a type annotation that doesn't match the implementation
* **Naming errors**: For some spelling errors the compiler will provide helpful suggestions. Feature to quickly apply one of those suggestions \(if any\)

> NOTE: When an linter message is open and a quick fix operation is available you will have buttons for each possible action. Pressing `Enter` will invoke the first action available \(which is typically the one you want\)

## Inline Docs

![](/assets/inline_doc.png)

In an Elm editor you can view documentation for top level functions inline in the editor. Just position the cursor on something and press `ctrl+d`.If the symbol refers to a top level declaration that has documentation the docs will be displayed inline at your cursor. Press ctrl+d again to close the doc view.

Inline docs works for both top level declarations in 3rd party packages as well as you own module docs.

## Auto completer

The autocompleter kicks in only once you have a connection to your elm project \(connect explicitly or just invoke the lint command, inline doc command etc\).

The autocompleter currently only suggests applicable top level definitions \(functions and values\). The plan is to make it much more advanced going forward.

It's on by default. If you wish to turn it off you need to do as follows:

* Open commands pane \(ctrl+space\)
* Search for and select `Settings: User behaviors`
* Add the following to your user.behaviors file to disable the autocompleter

\[:editor.elm :lt.plugins.elm-light.hinter\/elm-hints\]`; Turn off the autocompleter`

## Jump to definition \(and back\)

In an Elm file, place the cursor on a symbol and select the command `Editor: Jump to definition at cursor` . To jump back jus use the command `Editor: Jump back to where you jumped from`

> NOTE: The jump to feature only works for top level definitions. AND it's not fool proof, as it doesn't currently parse and infer stuff within expression bodies \(so for example if you shadow names and stuff, it will be confused\).

## Refactoring

**Ast Driven featueres**

![](/assets/ast-status.png)

In the bottom statusbar you'll notice an AST notification symbol\/marker. Behind the scenes the plugin parses all your projects Elm code to an AST representation. The parser is by no means perfect and may fail, but generally it's fairly lenient compared to the Elm compiler \(that's an understatement\). Anyways it parses on the fly as you type. That means that it will fail regurlarily as yo type. The icon\/symbol turns red and the text indicates a failure to parse. Not to worry... unless you have something that really is valid elm code \(as verified by using Elm Lint\).

If you find cases where it doesn't report success when it should please do submit a bug request to the plugin issue tracker \(with a reprodicuble case  \(elm file or reference to one\).

> NOTE: You may experience cases where things have gotten out of sync with the editor buffer. I haven't tested this stuff that much yet, so I'm letting you be my betatesters \(: The ramicfications shouldn't be end-of-the-world scenarios because the key features like Linting and formatting should work just fine regardless. But please do help me make it nice and robust by letting me know when something odd occurs !

**Expose\/Unexpose declaration**

![](/assets/expose.png)

A tiny marker in the editor gutter indicates that a function\/value is exposed publicly by the module.

To expose a function place the cursor on the function name \(or type name\) and select the command `Elm: Expose top level declaration` to unexpose it use the command `Elm: Unexpose top level declaration`

> NOTE: If your module declaration exposes all \(..\), then these commands have no effects. Pls also note that currently these commands are not formatting friendly \(you will loose comments, extra newlines you might have used etc\).

**More is coming here in the weeks and months to come. Feel free to help suggest ideas !**

## Language Docs

![](/assets/language_docs.png)

**With an .elm file open;**

* Select the command: `Docs: Search language docs (ctrl-shift-d)`
* Enter search criteria
* Behold the results

_To be improved !_

## Elm Repl

Once connected to an elm-project in Light Table, a repl is started running in the background.This means you can evaluate statements from within any given elm editor.

**In an elm file:**

* Position the cursor within the region of a top level expression and press ```cmd/ctrl+enter`.``
* You may also select a region that constitutes of one or more top level statements and press `cmd/ctrl+enter`

  **However** results are shown next to the first line of the selection, even though the actual result might be the related to the last statement \(or if an error, whatever line caused the error\)

* results are shown inline


You may reset the repl to start with a clean slate. Just select the command: \`Elm: Restart repl for current project\`

> NOTE: Results are currently only showed sensibly if you eval one top level statement at a time. Also the repl is shared
> 
> between all elm editors for a given project.

**Anonymous repl**

You may also create a repl that isn't backed by a file

* Select the command `Elm repl: Open a elm repl` 
* You may now eval code as for an Editor repl

> NOTE: You need a connected elm project for this to work

## Elm Reactor

When you connect an elm project, elm-reactor is started in the background. To support multiple projects running in parallell each projects elm-reactor gets a port from the port-range \(3000 - 4000\)

Convenience commands has been added to view an elm file in the Light Table internal browser.

To use

* Select the command `Elm: View current elm file in browser (elm-reactor)`

TIP: If you get a blank page \(and\/or an error in the console about the address not being available\), it might be

because elm-reactor is running make in the background. You might need to be patient and refresh the browser \(\`cmd+r\` for mac\)

WARNING: On Mac the elm-reactor starts two processes. You may experience occurences when the plugin is unable

to terminate both these subprocesses appropriately for now. To be improved.

You may close connections by using the command \`Connect: Show connect bar\` and click disconnect for your elm project

## Package Manager

The plugin has an interface for doing some handy package related task. It's basically a thin wrapper over the elm-package command with a UI to give you a better overview.

![](/assets/elm-light-pkgs.png)

**Open package manager**

From an editor with any file under your project, select the command ```Elm: Show project packages``\`

NOTE: You need to have a working network connection, as it retrieves package info from the central elm package repository

**Add a new package**

* Search for a given package in the section for adding packages

* Use up\/down arrows to navigate the dropdown

* Use enter to select the package you wish to add

* Select the version of the package you wish to install

* Click `Add package`

* Check the status bar\/console log for feedback on progress and success\/failure

* If all goes well the view of packages gets updated \(as will you elm-package.json file in the background as well\)


> NOTE: The feedback from elm-package install is not always the most helpful when there are problems. Sometimes
> 
> it even reports success when nothing has been done. Check out the github repo for elm-package for follow up on issues
> 
> related to this. Be adviced that when a package is listed with the \`exact\` column empty, means something didn't go well
> 
> , eventhough elm-package might have reported success.

**Remove package**

You can remove packages that are specified in your elm-package.json.

* Click on the \`remove\` button next to the package in the listing.
* Your elm-package.json file will get updated
* elm-package install invoked to clean up
* The listing will be updated \(with potential transitive deps removed too\)

**Handling other cases**

Sometimes you need to edit your `elm-package.json` file directly for elm-package to know what to do.

There might also be the case you have defined a \`elm-package.json\` but haven't yet invoked any elm command

that resulted in package install. For such cases the `Refresh packages` button comes in handy !

**Package docs**

For any packages installed \(with an exact version\) you may view the online docs:

* In the list click on the package name
* A LT browser tab is opened \(or focused if one already exists\) and the package doc for the selected package

  is displayed


## Dependency Graph

![](/assets/elm-dep-graph.png)

You may view an inline dependency graph of you project dependencies.

* From any file under your project root invoke the command \``Elm: Show dependency graph`\`
* Alternatively click the `Show dependency graph` button from the package viewer

**Additional info**

* Dashed arrows reprensents transitive dependencies
* If you hover of a dependency you will see a short package summary
* Dependencies found in elm-package.json that \`elm-package\` failed to install will be shown with a red color
* When you update packages in the package viewer, the graph is automatically refreshed

> NOTE: You will need an internet connection for this to work \(uses package.elm.lang.org\)

## Elm Format

In an effort to standardize how Elm code should be formatted, [elm-format](https://github.com/avh4/elm-format) wascreated. It is still in alpha, but I figured you might just as well start playing with it.

**Precondition**

You will need to install elm-format and make sure the executable is available in your path for it to work from

the plugin.

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

WARNING: Any unsaved changes will be lost when running this command. This command updates the file backing the editor

in question.

**Adding keyboard shortcuts**

`````[:editor.elm.common "cmd-shift-l" :elm-format-expression]````[:editor.elm.common "cmd-ctrl-l" :elm-format-buffer]`````

**Configuring indent in Light Table**

`[:editor.elm.common :lt.objs.editor/tab-settings false 4 4] ;; or 2 2 if the war continues and things change back`

## Module Browser

![](/assets/modulebrowser.png)

**To view your project modules:**

* From an open elm editor
* Select the command : `Elm: Show module-browser`
* Use the arrow keys to move the selection up or down
* The list of modules is filtered by `"starts-with"` \(case insensitive\) from what you enter in the input text field
* To open a module press \`Enter\`
* To close the module browser, press `Esc`

## Preview Package Docs for Module

![](/assets/packagedocs.png)

If you are writing a package to be deployed to http:\/\/package.elm-lang.org\/ you need to document all your exposed modules \(remember to add any modules for public usage to the `exposed-modules` entry in your `elm-package.json`\)

**You can preview the docs in Light Table**

* From an open elm editor \(an exposed module remember\)
* Select the command : `Elm: Preview doc for selected file`
* A preview window is opened \(you might want to move that to it's own tabset\)
* Write docs according to the instructions at http:\/\/package.elm-lang.org\/help\/documentation-format
* When you save your file the preview will be automatically updated

> NOTE: The doc preview only works for exposed modules

## Misc

**Select top-level statements**

If you wish to select a top level statement just invoke the command `Elm: Select top level expression from current expression`

> NOTE: The selection algorithm is sort of naive, so there might be cases when the selection doesn't work out quite as you'd hope. In most cases it should work sensibly though.

**To enable as keyboard shortcut in both elm editors and anonymous elm repl**

`[:editor.elm.common "alt-shift-s" :elm.select.top.level] ; modify keybinding to your liking !`

**Code folding**

You can fold code by invoking the editor command \``Editor: Fold code at cursor`\`. It will fold the code based on the given indentation level your cursor is at.

