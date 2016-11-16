# Testing

![](/assets/test.png)

> Elm-light as of version 0.5.0 comes with integrated support for [elm-test](https://github.com/elm-community/elm-test). The only requirement for getting started with testing your Elm code in Light Table is that you have Elm version **0.18.0** or higher \(and that your project under test is on that version\).

## Getting started

You will need a 0.18 \(or higher\) compatible Elm project as a baseline. \(Note that you do not need to install Node and\/or npm- install elm-test, but of course feel free to do so, but it isn't needed by elm-light Light Table plugin. \).

1. From an open Elm file in your baseline project \(project under test\), select the command `Elm - Test Setup`. This will:
  1.  Create a `test` folder in your project \(if it doesn't already exist\)
  2. Create a test runner Elm file `Main.elm` \(handy if you later want to run a test suite using a command line test runner\)
  3. Create a sample Test module : `Tests.elm`
  4. Create a `elm-package.json` file for the test project based on the one for you project under test \(so it will add src folders and dependencies for you so you don't have to the first time\)
  5. run elm-package install to download all dependencies for the new test project

2. Once it's completed setting up,  open &lt;yourprojectundertestpath&gt;\/test\/Tests.elm

3. You are reeady to start running tests. You can do that in a couple of different ways:
  1. To run all tests in your project, select the command: `Elm: Test All`
  2. To run all tests in the given module you have open, select the command : `Elm: Test Module`
  3. To run a single test, place the cursor somewhere within the range of the given test function and select the command: `Elm: Test Current`

4. If you aren't connected, elm-light will first connect to your test project, it will then run the relevant tests based on your selection and display the results in a separate tab \(as illustrated above\). It will also display test results in the console at the bottom of your editor and a notification message is shown in the statusbar when the test run is complete.


## Important notes

* You will need to provide type annotations for your tests. It is used to determine what are candidate tests to be run. It's a small price to pay !
* You can disable a test \(or suite defined by using Test.concat\) by putting a @ltignore in a doc comment for the test \(see below for example\) 

```elm
{-| @ltignore -}
test1 : Test
test1 = 
  -- etc
```

If you define a test suite that includes tests from other test definitions and\/or modules with test, and you select the test all command, you will end up running the tests twice \(elm-light doesn't have enough knowledge to avoid that safely\). By adding the @ltgnore to a doc comment for the suite, you can work around that limitation. 

