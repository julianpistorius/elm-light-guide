# Getting started

## Installation

Install the plugin from the Light Table Plugin Manager.

1. In Light Table open the commands tab \(default ctrl+space or use the menu View-&gt;Commands\)
2. In the commands tab search field enter something like "_plugin manager_" and select the item `Plugins: Show plugin manager`
3. In the search field for plugins type `elm` and press enter
4. You should have an item named `elm-light` Click the install button to the right

When there are updates of the plugin an update button will be shown for `elm-light plugin` in the plugin manager

> If you want to try out the latest stuff on master or feel the urge to contribute, check out the [Contributing](/contributing.md) chapter.

## Preconditions

* **LIghtTable 0.8-alpha or higher is required**

* You will need to have the [elm-platform](http://elm-lang.org/install) \(there is also a npm installer out there\) installed and the following should be in your path:

  * [elm-reactor](https://github.com/elm-lang/elm-reactor)

  * [elm-make](/ https://github.com/elm-lang/elm-make)

  * [elm-package](https://github.com/elm-lang/elm-package)

  * [elm-repl](https://github.com/elm-lang/elm-repl)



* For all commands\/features you will need to have a project folder with an `elm-package.json` file

> **To get nice and consistent formatting you should also install \*\***[elm-format](https://github.com/avh4/elm-format)\*\*
> 
> Once elm-format reaches release it will most likely become mandatory in elm-light, so you might as well start using it already to get familiar with it ! Also some of the refactoring features will depend on it for nicer output.

### Some really useful things to consider if you can't be bothered to read the entire guide

* **Autoclose brackets**: If you haven't already, **DO** enable autoclose brackets in Light Table. How ? See  [Useful configurations](/Reference#useful-configurations)
* **Auto-completions** only starts working once you have [connected](/elm-client-overview.md) to an Elm project. You can force "suto.connection", through various commands \(Lint, toggle docs etc\). So if you hit "ctrl-d" on a symbol when you aren't connected, it will connect for you. Another option is to add the Lint command to the save operation in Light Table. Again see [Useful configurations](/Reference#useful-configurations)

