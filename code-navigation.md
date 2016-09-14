## Code Navigation

### Jump to definition \(and back\)

In an Elm file, place the cursor on a symbol and select the command `Editor: Jump to definition at cursor`. To jump back just use the command `Editor: Jump back to where you jumped from`

> NOTE: The jump to feature only works for top level definitions. AND it's not fool proof, as it doesn't currently parse and infer stuff within expression bodies \(so for example if you shadow names and stuff, it will be confused\).

## 

### Find usages

![](/assets/find-usages.png)

You can use the find usages command to quickly find all usages of a given symbol. Currently it will only give hits for top-level definitions \(functions, values, types, aliases etc\).

* Place the cursor on a symbol
* Invoke the command `Elm: Find usages of symbol at cursor`
* Hits are grouped per module
* You can click on a hit-row to goto the file and location of the given symbol usage 

> **Limitations**: The implementation does not guarantee that you will only get correct the results. I.e you may end up getting more hits than you should. Things like name shadowing, record\/type-alias fields etc makes this a complicated thing to get right. We will get there eventually, but hopefully you will still find the feature useful. I guess it's better to think of the current implementation as a scoped or more intelligent full text search.

### Module Browser

![](/assets/modulebrowser.png)

**To view your project modules:**

* From an open elm editor
* Select the command : `Elm: Show module-browser`
* Use the arrow keys to move the selection up or down
* The list of modules is filtered by `"starts-with"` \(case insensitive\) from what you enter in the input text field
* To open a module press \`Enter\`
* To close the module browser, press `Esc`

