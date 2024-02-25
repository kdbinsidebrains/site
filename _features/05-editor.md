---
title: "Code Editor"
permalink: /features/editor
excerpt: "Code Editor"
toc: true
---

## Overview

The best way to get know the _Code Editor_ is to check the official
documentation: [https://www.jetbrains.com/help/idea/working-with-source-code.html](https://www.jetbrains.com/help/idea/working-with-source-code.html)

Not all features are applicable to Q language, but most of them are. Here we will concentrate only on specific
functionality of the plugin.

Meanwhile, the plugin does full static scan of all Q code and build internal index. The index is used by mostly all
functionality, like code completion and quick lookup.

## Execution

Apart from [Console](/features/console) you can execute any part of code from active editor with hot keys or from pop-up
menu:
![editorExecuteMenu](/assets/images/features/editor/editorExecuteMenu.png)

There are three ways how you can execute a code.

### Execute Line/Selection

Initiated by _Ctrl+Enter_. If you have no selection, then current line will be executed
of the whole otherwise. This way sends selected text/line to active [Console](/features/console) and print the result
there in the console. It's the base method of code execution.

### Quick Execute Line/Selection

Initiated by _Shift+Enter_ but instead of sending code to the console, it executes
code 'offline' and displays result in a pop-up window with no any footprint in the console:

![editorExecutionQuick](/assets/images/features/editor/editorExecutionQuick.png)

This execution is useful if you don't need the result (function definition or any kind) or operation is so simple that
it's faster to view result inline.

Even the functionality was designed for quick response it works with complex responses, like tables, as well but most
functionality doesn't work properly:

![editorExecutionQuickComplex](/assets/images/features/editor/editorExecutionQuickComplex.png)

### Execute Global Assignment

Initiated by _Ctrl+Shift+Enter_ and executes the whole statement till the file root. Its most complex but very useful
execution type for code editing.

Let's suppose you work on a complex function with some inner function:

~~~ q
.my.func:{[x;y]
    f:{[x;y] x+y};
    :f[x;y];
 }
~~~

When you change the function implementation or even code of the inner function, you have to select the whole definition
of the root function to redefine the implementation.

With _Execute Global Assignment_ wherever your caret is placed inside the function, all statements will be iterated till
root assignment and all root assignment code will be executed redefining the _.my.func_ function.

## Editing Features

### Navigation

If you have a lambda definition somewhere in a project (in editing file or any other files or even in a file from
libraries) you can quickly just to the lambda or variable definition by middle-click on the name or by pressing _
Ctrl+B_:

If a lambda or a variable is defined in one file all usages will be highlighted:

![editorNavigation](/assets/images/features/editor/editorNavigation.png)

### Code Analysis

The plugin does static code analysis and shows all found errors in editing file:

![editorAnalysis](/assets/images/features/editor/editorAnalysis.png)

Some errors can be fixed just by pressing _Alt+Enter_, like defining unknown function:

![editorFixUnknown](/assets/images/features/editor/editorFixUnknown.png)

or changing typo in type cast:

![editorFixCast](/assets/images/features/editor/editorFixCast.png)

### Code Completion

When you start typing in the editor, the IDEA suggests you most suitable functions based on your entering:

![editorSuggestion1](/assets/images/features/editor/editorSuggestion1.png)

Code completion works not only for system functions (which are supported manually) but also for any other code in a
project:

![editorSuggestion2](/assets/images/features/editor/editorSuggestion2.png)

You have to enter at least three chars to get auto-suggestion. You can press _Ctrl+Space_ to force suggestions for two
chars.
{: .notice--info}

### Invoke Parameters

If you invoke a function and not sure about its parameters, you can press _Ctrl+P_ inside invocation brackets to force
parameters tooltip:

![editorParametersSuggestion](/assets/images/features/editor/editorParametersSuggestion.png)

### Rename Variable

You can rename any variable by _Shift+F6_:

![editorRenaming](/assets/images/features/editor/editorRenaming.png)

For more andanced search and renaming functionality, please
check [Find & Rename](/features/navigation#Find%20&%20Rename) in [Navigation](/features/navigation) feature.

### Code Documentation

The plugin parses and supports variables docs. Just place the caret to a variable and press _Ctrl+Q_ to fetch related
variable doc:

![editorDocs](/assets/images/features/editor/editorDocsCustom.png)

This functionality works for custom variables and system functions as well:

![editorDocsSystem](/assets/images/features/editor/editorDocsSystem.png)

The documentation for system functions is supported manually and hardcoded in the plugin. If something is wrong - let us
know.
{: .notice--info}

### Auto-Formatting

The plugin supports auto-code formatting. Please use appropriate _Code_ menu items or hot keys to force auto-formatting:

![editorFormattingMenu](/assets/images/features/editor/editorFormattingMenu.png)

Please check [auto-formatting style](/settings/style) to find out more about rules or change required parameters.