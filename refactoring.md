## Refactoring

### **Ast Driven features**

![](/assets/ast-status.png)

In the bottom statusbar you'll notice an AST notification symbol\/marker. Behind the scenes the plugin parses all your projects Elm code to an AST representation. The parser is by no means perfect and may fail, but generally it's fairly lenient compared to the Elm compiler \(that's an understatement\). Anyways it parses on the fly as you type. That means that it will fail regurlarily as you type. The icon\/symbol turns red and the text indicates a failure to parse. Not to worry... unless you have something that really is valid elm code \(as verified by using Elm Lint\).

If you find cases where it doesn't report success when it should please do submit a bug request to the plugin issue tracker \(with a reproducible case \(Elm file or reference to one\).

> NOTE: You may experience cases where things have gotten out of sync with the editor buffer. I haven't tested this stuff that much yet, so I'm letting you be my betatesters \(: The ramicfications shouldn't be end-of-the-world scenarios because the key features like Linting and formatting should work just fine regardless. But please do help me make it nice and robust by letting me know when something odd occurs !

**\*\*NONE OF THE FOLLOWING FEATURES ARE CURRENTLY PARTICULARILY WHITESPACE FRIENDLY. NEWLINES, EXTRA INDENTS, COMMENTS ETC MAY BE LOST DURING REFACTORING\*\***

### Sort imports

If your list of imports becomes long and unwieldy you might want to sort them. This feature currently allows you to sort imports as follows;

* Firstly Project modules alphabetically
* Secondly \(if any\) external modules alphabetically

Usage:

* In an open Elm editor in your project
* Select the command `Elm: Sort imports`

### Autoimport Module

| ![](/assets/autoimport.png) | ![](/assets/autoimport2.png) |
| --- | --- |

When you are in the middle of writing a function you suddenly realize that you need access to a function from another module. The autoimport feature can help you add the import without switching context.

**Usage**

* Write an aliased ref to a function \(or Type, port, whatever top level declaration\) as if the module was already imported. It needs to be in the format `<UpperedId>.<someexposedtopleveldecl>`
* Select the command: `Elm: Autoimport module`
* If it's a singular hit it will add an import for that module with the alias you suggested
* If it's multiple hits, a select box will appear prompting you to select which Module it should import for you
* After successfully selecting, the module is added as an import and then the whole list of imports is sorted as specified in [Sort imports](#sort-imports)

> NOTE: Nothing will happen if:
> 
> * The format of the symbol at hand is not in the format described above. So `Html.App.map` will not work because `Html.App` is not a valid alias
> * No function with the suggested name you provided exists or alternatively exists but isn't exposed by any module
> * You already have an import for that module with a different alias
> 
> If you already have an import for that module, but haven't given it an alias, it will update the import declaration with the alias you provided

### **Expose\/Unexpose declaration**

![](/assets/expose.png)

A tiny marker in the editor gutter indicates that a function\/value is exposed publicly by the module.

To expose a function place the cursor inside the range of a function or type\/type alias and select the command `Elm: Expose top level declaration` to unexpose it use the command `Elm: Unexpose top level declaration`

> NOTE: If your module declaration exposes all \(..\), then these commands have no effects. Pls also note that currently these commands are not formatting friendly \(you will loose comments, extra newlines you might have used etc\).

**More is coming here in the weeks and months to come. Feel free to help and suggest ideas !**

