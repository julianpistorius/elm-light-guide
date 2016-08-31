# Contributing

The elm-light plugin is developed primarily in ClojureScript. So if you are not familiar with ClojureScript contributing here might be a great way to learn yourself a Lisp ! Some parts of the plugin \(notably the client, which is a background process\) are developed in JavaScript. 



## Getting set up

1. Clone the [repo](https://github.com/rundis/elm-light) to the plugin folder for Light Table \(for OS\/X thats `~/Library/Application Support/LightTable/plugins`, you can find the location for your OS by selecting `LightTable-> About Light Table` from the menu\)

2. Restart Light Table

3. Open a ClojureScript file \(`.cljs`\) and save it. This will compile all sources. If you just wanted to try out the latest version of the plugin, you just need to restart Light Table again. The you will be running with the plugin with the latest code on master. \(with the caveats that might entail\)

4. If you are keen to try out something, make some changes to wherever and eval the code  \(ctrl-enter\). You need to have the cursor inside a top level form or right next to it. Light Table will start a repl connection and prompt you to select a client. You should select `Light Table UI`

5. You are now set to hack away using the repl and explore your way through the code or perhaps a cool pull request !



Please note that currently Light Table uses a pretty old version of ClojureScript so that's somewhat limiting. To familiarize your self with developing in Light Table, you should check out the [Light Table Wiki](https://github.com/LightTable/LightTable/wiki).There are also friendly people at the [Light Table gitter room](https://gitter.im/LightTable/LightTable) who are happy to help with Light Table related stuff.







> If you'd like to contribute pull requests are most welcome. But please don't include the transpiled files \(`_compiled`\) in teh PR.

