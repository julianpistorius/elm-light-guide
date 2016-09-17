## Auto completer

The autocompleter kicks in only once you have a connection to your elm project \(connect explicitly or just invoke the lint command, inline doc command etc\).

> The autocompleter currently only suggests applicable top level definitions \(functions, values, types, type aliases etc\). The plan is to make it much more advanced going forward.

It's on by default. If you wish to turn it off you need to do as follows:

* Open commands pane \(ctrl+space\)
* Search for and select `Settings: User behaviors`
* Add the following to your user.behaviors file to disable the auto-completer

`[:editor.elm :-lt.plugins.elm-light.hinter/elm-hints]; Turn off the auto completer`

### Context awareness

| ![](/assets/ac_module_decl.png) | ![](/assets/ac_import_module.png) |
| --- | --- |
| ![](/assets/ac_import_exposing.png) | ![](/assets/hints_typealias.png) |

The autocompleter tries to be clever about what completions to provide depending on the context of where you are. It's not quite "Intellisense", but gradually it will hopefully become a lot smarter. The current implementation supports context aware hints as follows:

* **Module Declaration**: When inside the exposing parenthesis of your module declaration, only function names from your module will be suggested \(and only the ones you haven't already exposed**\)**
* **Import Declaration**:

  * After writing `import` and whitespace,  only importable modules \(that you  haven't already imported\) will be suggested
  * When inside the exposing parenthesis of an import declaration, only functions exposed from that module are suggested \(and only the ones you have already included already\)

* **Type Alias Params**: If you have provided an annotation for a function or value and use a named param for that in your function definition, you will get completions for type alias params in the expression body of your function. Note that shadowing might give unwanted results, but then again shadowing is rarely a good idea anyways !
* For the first token of a file, only relevant top-level keywords are suggested

* For all other cases it will currently fall back to display all available top level definitions \(types, values, functions etc\) that are defined in the module and\/or are imported per default or explicitly imported by your module.


