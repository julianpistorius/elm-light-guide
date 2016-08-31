# Features

Whenever this chapter refers to command. That is a Light Table command which you may \(and probably should\) provide a custom keyboard shortcut to.

**To define a shortcut in Light Table:**

1. Open the command bar \(ctrl-space\)
2. Search and find `Settungs: User keymap` and select that
3. Define your short cuts as per the example below

`[:editor "alt-enter" :editor.linter.details]  ;; command to display details for a marked error or warning after linting`

To view all available commands and suggestions tips on how you might want to do more advanced configurations, check out the [Reference](/reference.md) chapter

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

> NOTE: When an linter message is open and a quick fix operation is available you will have buttons for each possible action. Pressing ```Enter``` will invoke the first action available \(which is typically the one you want\)



## Inline Docs

In an Elm editor you can view documentation for top level functions inline in the editor. Just position the cursor on something and press `ctrl+d`.If the symbol refers to a top level declaration that has documentation the docs will be displayed inline at your cursor. Press ctrl+d again to close the doc view.



Inline docs works for both top level declarations in 3rd party packages as well as you own module docs.  





