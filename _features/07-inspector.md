---
title: "Inspector"
permalink: /features/inspector
excerpt: "Inspect/Scan real KDB instance and get all defined variables/functions and tables in one place"
toc: true
---

## Overview

_KDB Inspector_ scans active instance and loads definition of all global variables, tables and functions and shows it in
a tree-like structure.

The _Kdb Inspector_ tool window is located in the right bottom corner and is hidden by default:

![inspectorTool](/assets/images/features/inspector/inspectorTool.png)

By default, the Inspector doesn't query an instance, and you have to manually force an update process, but you can
enable
it for activating instances in [configuration](/settings/options).

You can enable/disable grouping and filtering options in the tool window toolbar.

An instance is enquired only one per session, and switching between instances doesn't generate additional loading on an
instance. You can see time of last update in the statusbar of the _Inspector_.

## Permissions

The _Inspector_ executes a free-form query to load all information from an instance. You must allow the query on the
server side if free-form queries are prohibited. You can find the latest query on
the [plugin GitHub page](https://github.com/kdbinsidebrains/plugin/blob/main/src/main/resources/org/kdb/inside/brains/inspector.q)
for validation.

## Filtering

The Inspector loads definition of all functions, variables and tables, but you can hide any with the appropriate toolbar
button:

![inspectorFilter](/assets/images/features/inspector/inspectorFilter.png)

You can also hide/show system namespaces: _.q, .Q, .h, .j_ and _.o_. Dy default system namespaces are hidden.

The _.z_ is not a namespace but system functions, so it's not returned by an instance and not shown in the inspector.
{: .notice}

## Grouping

To reduce tree complexity, you can group all elements by returned types:

![inspectorGroup](/assets/images/features/inspector/inspectorGroup.png)

## Search

When the Inspector tree is in focus, just start typing a varibale/table or function name to search it in the tree:

![inspectorSearch](/assets/images/features/inspector/inspectorSearch.png)

## Query Value

_Double-click_ or _Enter_ on an item will query its value and show the result in [Console](/features/console):

![inspectorExecute](/assets/images/features/inspector/inspectorExecute.png)

## View Source

If _Scroll To Source_ is enabled and item is defined in the project source code, when the item will be highlighted in
the main editor.

If an item is defined in the project source code, you can just to its definition by pressing _F4_ or from pop-up menu.

If an item is a function and is defined in the project source code, you can compare its content defined in the instance
with the content of the source code.

![inspectorExecute](/assets/images/features/inspector/inspectorExecute.png)

## Code Difference

When you have a function defined in your source code that is also defined in the instance, you can use 'Diff'
functionality compare exist source code with actual implementation by _Ctrl+D_ or context menu:

![inspectorDiffMenu](/assets/images/features/inspector/inspectorDiffMenu.png)

The Diff works only for functions (object type 100) as make no sense for any other types.

New diff tab will be opened in the main editor to show you the difference:
![inspectorDiffContent](/assets/images/features/inspector/inspectorDiffContent.png)

It could be a good idea to ignore white-spaces as KDB can do post-processing and remove some spaces.
{: .notice--info}

## Code Completion

If you have the active Inspector with loaded structure, the content of the inspector is used to get completion variables and
the source is indicated as _inspector_:

![inspectorCompletion](/assets/images/features/inspector/inspectorCompletion.png)
