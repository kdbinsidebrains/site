---
title: "Inspector"
permalink: /features/inspector
excerpt: "Inspect/Scan real KDB instance and get all defined variables/functions and tables in one place"
---

_KDB Inspector_ scans active instance and loads definition of all global variables, tables and functions and show it in
a tree-like structure.

The _Kdb Inspector_ tool window is located in the right bottom corner and is hidden by default:

![inspectorTool](/assets/images/features/inspector/inspectorTool.png)

By default, the Inspector doesn't query an instance, and you have to manually force update process, but you can enable
it for activating instances in [configuration](/settings/options).

You can enable/disable grouping and filtering options in the tool window toolbar.

An instance is enquired only one per session and switching between instances doesn't generate additional loading on an
instance. You can see time of last update in the statusbar of the _Inspector_.

The _Inspector_ executes free-form query to load all information from an instance. You must allow the query on the
server side if free-form queries are prohibited. You can find the latest query on
the [plugin GitHub page](https://github.com/kdbinsidebrains/plugin/blob/main/src/main/resources/org/kdb/inside/brains/inspector.q)
for validation.