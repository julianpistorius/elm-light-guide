## Docs

### Inline Docs

![](/assets/inline_doc.png)

In an Elm editor you can view documentation for top level functions inline in the editor. Just position the cursor on something and press `ctrl+d`.If the symbol refers to a top level declaration that has documentation the docs will be displayed inline at your cursor. Press `ctrl+d` again to close the doc view.

Inline docs works for both top level declarations in 3rd party packages as well as you own module docs.

### Language Docs

![](/assets/language_docs.png)

**With an .elm file open;**

* Select the command: `Docs: Search language docs (ctrl-shift-d)`
* Enter search criteria
* Behold the results

_To be improved !_



### Preview Package Docs for Module

![](/assets/packagedocs.png)

If you are writing a package to be deployed to http:\/\/package.elm-lang.org\/ you need to document all your exposed modules \(remember to add any modules for public usage to the `exposed-modules` entry in your `elm-package.json`\)

**You can preview the docs in Light Table**

* From an open elm editor \(an exposed module remember\)
* Select the command : `Elm: Preview doc for selected file`
* A preview window is opened \(you might want to move that to it's own tabset\)
* Write docs according to the instructions at http:\/\/package.elm-lang.org\/help\/documentation-format
* When you save your file the preview will be automatically updated

> NOTE: The doc preview only works for exposed modules

