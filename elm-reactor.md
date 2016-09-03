## Elm Reactor

When you connect an elm project, elm-reactor is started in the background. To support multiple projects running in parallell each projects elm-reactor gets a port from the port-range \(3000 - 4000\)

Convenience commands has been added to view an elm file in the Light Table internal browser.

To use

* Select the command `Elm: View current elm file in browser (elm-reactor)`

> TIP: If you get a blank page \(and\/or an error in the console about the address not being available\), it might be because elm-reactor is running make in the background. You might need to be patient and refresh the browser \(\`cmd+r\` for mac\)
> 
> WARNING: On Mac the elm-reactor starts two processes. You may experience occurences when the plugin is unable to terminate both these subprocesses appropriately for now. To be improved.

You may close connections by using the command `Connect: Show connect bar` and click disconnect for your elm project

