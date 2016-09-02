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
* **Missing type annotation**: Facility to add type annotation \(top level expressions only\)
* **Type mismatch**: Facility to fix a type annotation that doesn't match the implementation
* **Naming errors**: For some spelling errors the compiler will provide helpful suggestions. Feature to quickly apply one of those suggestions \(if any\)

> NOTE: When an linter message is open and a quick fix operation is available you will have buttons for each possible action. Pressing `Enter` will invoke the first action available \(which is typically the one you want\)

## 

