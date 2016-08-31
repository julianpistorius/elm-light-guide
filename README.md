# Elm Light - The Elm plugin for Light Table

This plugin aims to provide you with 1st. class support for the [Elm](http://elm-lang.org) programming language and associated platform.

It's very much work in progress, but it's getting better by the day and will improve even more when the Elm platform gets more hooks for tooling. 

Some of the key features already supported are:

* **Linting** of your projects with inline errors and warnings. There are also some handy quickfixes available for various warning messages returned from the elm compiler
* **Syntax highlighting**: Syntax highlighting is provided throug a slightly customized CodeMirror mode \(Light Table uses CodeMirror behind the scenes\)
* **Package manager**: There is a handy package manager that lets you add\/remove packages to your project. It's a nice convenience feature to make it easier for you to manage your dependencies. There is also a cool dependency viewer to see how it all ties together with direct and transitive dependencies
* **Reactor integration: **When you connect to an Elm project the plugin will start an elm-reactor instance for you in the background. This allows you to quickly get started and you can use the inbuildt browser in Light Table to view your changes  by a quick combination of save and refresh.
* **Repl integration**: The elm-repl is an untapped resources that I suspect far to many beginners and even advanced Elm programmers use as much as they should. The plugin starts an elm-repl instance for you when you connect to an Elm project. You can perform code eval of individual expressions and view the results inline in your editor. This is really quite handy once you try it out. \(The elm-repl is unfortunately a bit limited, and doesn't handle view related stuff\). Writing a Json decoder ? Fire up an elm-repl, and start exploring your way with a tight feedback loop to a great solution !
* **Refactoring**: As of version 0.4.0 the plugin has set out on the quest to provide handy refactoring features. It's still very much early days, but things will get interesting going forward. The plugin now parses all your project code and the code for your dependencies once you connect to a project. Once connected it will listen for changes to all relevant files and reparse as necessary. The ASTs from this parsing will enable quite a few interesting features going forward !
* **Docs**: It's really handy to have documentation inline in your editor. The plugin supports display docs for modules from external packages as well as your own modules and top level declarations. You can also search for docs for any publicly exposed function within your project. Less context switching for you ! For package authors there is also a documentation preview which is really handy to use before you publish a package to the central package repository.
* **Navigation**: You can easily jump to back and forth between functions and modules. Both using the Module browser and through the use of quick navigation \(jump to\) in your editor buffers.




If you find any bugs or want to request features, don't hesitate to submit them to the [issue tracker](https://github.com/rundis/elm-light/issues) for plugin repo





> I hope and trust you will find the plugin a useful and enjoyable tool for developing your Elm project and packages.
> 
> _Magnus_

