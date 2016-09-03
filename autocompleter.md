## Auto completer

![](/assets/autocompleter.png)

The autocompleter kicks in only once you have a connection to your elm project \(connect explicitly or just invoke the lint command, inline doc command etc\).

> The autocompleter currently only suggests applicable top level definitions \(functions and values\). The plan is to make it much more advanced going forward.

It's on by default. If you wish to turn it off you need to do as follows:

* Open commands pane \(ctrl+space\)
* Search for and select `Settings: User behaviors`
* Add the following to your user.behaviors file to disable the autocompleter

`[:editor.elm :-lt.plugins.elm-light.hinter/elm-hints]; Turn off the autocompleter`

