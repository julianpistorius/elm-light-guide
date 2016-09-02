## Refactoring

### **Ast Driven features**

![](/assets/ast-status.png)

In the bottom statusbar you'll notice an AST notification symbol\/marker. Behind the scenes the plugin parses all your projects Elm code to an AST representation. The parser is by no means perfect and may fail, but generally it's fairly lenient compared to the Elm compiler \(that's an understatement\). Anyways it parses on the fly as you type. That means that it will fail regurlarily as yo type. The icon\/symbol turns red and the text indicates a failure to parse. Not to worry... unless you have something that really is valid elm code \(as verified by using Elm Lint\).

If you find cases where it doesn't report success when it should please do submit a bug request to the plugin issue tracker \(with a reprodicuble case \(elm file or reference to one\).

> NOTE: You may experience cases where things have gotten out of sync with the editor buffer. I haven't tested this stuff that much yet, so I'm letting you be my betatesters \(: The ramicfications shouldn't be end-of-the-world scenarios because the key features like Linting and formatting should work just fine regardless. But please do help me make it nice and robust by letting me know when something odd occurs !

### **Expose\/Unexpose declaration**

![](/assets/expose.png)

A tiny marker in the editor gutter indicates that a function\/value is exposed publicly by the module.

To expose a function place the cursor on the function name \(or type name\) and select the command `Elm: Expose top level declaration` to unexpose it use the command `Elm: Unexpose top level declaration`

> NOTE: If your module declaration exposes all \(..\), then these commands have no effects. Pls also note that currently these commands are not formatting friendly \(you will loose comments, extra newlines you might have used etc\).

**More is coming here in the weeks and months to come. Feel free to help suggest ideas !**

