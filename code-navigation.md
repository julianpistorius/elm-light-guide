## Code Navigation

### Jump to definition \(and back\)

In an Elm file, place the cursor on a symbol and select the command `Editor: Jump to definition at cursor` . To jump back jus use the command `Editor: Jump back to where you jumped from`

> NOTE: The jump to feature only works for top level definitions. AND it's not fool proof, as it doesn't currently parse and infer stuff within expression bodies \(so for example if you shadow names and stuff, it will be confused\).

## 

### Module Browser

![](/assets/modulebrowser.png)

**To view your project modules:**

* From an open elm editor
* Select the command : `Elm: Show module-browser`
* Use the arrow keys to move the selection up or down
* The list of modules is filtered by `"starts-with"` \(case insensitive\) from what you enter in the input text field
* To open a module press \`Enter\`
* To close the module browser, press `Esc`

