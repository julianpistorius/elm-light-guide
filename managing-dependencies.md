## Managing Dependencies

### Package Manager

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


> NOTE: The feedback from elm-package install is not always the most helpful when there are problems. Sometimes it even reports success when nothing has been done. Check out the github repo for elm-package for follow up on issues related to this. Be adviced that when a package is listed with the \`exact\` column empty, means something didn't go well, eventhough elm-package might have reported success.

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
* A LT browser tab is opened \(or focused if one already exists\) and the package doc for the selected package is displayed

### Dependency Graph

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

