# Elm Client Overview

For pretty much any operation this plugin you support you need an elm client connection. An elm client connection

is a small node process that the plugin typically will spawn automatically for any action that requires a elm client.

When the elm-client starts it;

* Opens an elm-repl
* Starts \(and listens\) to elm-reactor
* Downloads packages if necessary and parses all relevant Elm code to AST representations
* Starts a listener process for changes to Elm files and packages
* Listens for commands from light table \(eval, docs, autocompletions etc\)

You may also manually connect to an elm project using the connect bar in Light Table

* Invoke the command: `Connect: Add Connection`

* Select `Elm` from the list of client types

* If all goes well you will get a confirmation in the status bar that the project is connected

* To disconnect

  * Invoke the command `Connect: Show connect bar`

  * Find the project in the list and click disconnect



The client connections are named after the the directory containing the elm-package.json

![](/assets/connection.png)

## Elm Project

In the future the plugin might add support for geting started with just a simple .elm file, but you very quickly

end up having to add some config especially a elm-package.json. So as mentioned in the preconditions, you will need one.

**How does elm-light determine the project ?**

Say you have a project with the following structure

`````/home/myuser/projects/hello-elm/elm-package.json````/home/myuser/projects/hello-elm/hello.elm````/home/myuser/projects/hello-elm/src/util.elm`````

* If you start of with evaluating hello.elm, the plugin will start looking for a elm-package.json in the same directory

  as the hello.elm file resides. So the elm client will use \`\/home\/myuser\/projects\/hello-elm\` as root path and the project assumed to be \`hello-elm\`

* If you start of with evaluating util.elm, it will start looking for a \`elm-package.json\` in the \`src\` folder, since not finding one it will try the parent directory \(and recurse until one found or none can be found\).

* Hence the root path and project name will be the same

* If you \(with the elm-client still running\) later add a .elm file anywhere below \`\/home\/myuser\/projects\/hello-elm\` and eval or lint \(or whatever\) on it, the plugin will assume it belongs to the same elm-client and use that.


