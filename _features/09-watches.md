---
title: "Watches"
permalink: /features/watches
excerpt: "Watches expression with auto-refreshing after each operation"
toc: true
---

## Overview

_Watches_ functionality is part of [KdbConsole](/features/console) that allows to automatically track the state of variable or
expressions.

All _Watches_ are re-calculated each time when any operation is performed on an instance when any other expression is
executed.

## Permissions

All _watches_ are refreshed via the same connection and access to free-form queries and **value** command is required
for correct work.

You can find the appropriate code in source code of the project on [GitHub](https://github.com/kdbinsidebrains/plugin)
in [watches.q](https://github.com/kdbinsidebrains/plugin/blob/main/src/main/resources/org/kdb/inside/brains/inspector.q)
file.

## Watching Panel

You can show _Watches_ from [Kdb Console](/features/console) left toolbar by enabling 'Show Watches Panel' button.

![panel.png](/assets/images/features/watches/panel.png)

The _Watches_ panel is part of main console windows and when enabled, shown in the right part of the console:

![split.png](/assets/images/features/watches/split.png)

## Watching Expressions

You can add a watching expressing by typing it in the editor at the top, pressing 'Insert' button of using the context menu.

![expressions.png](/assets/images/features/watches/expressions.png)

All entered expressions are stored in the project configuration and restored after IDE restart for each opened console.
If a console was closed, all associated watches are removed.

## Watches State

All watching expressions have 2 states:

- the value of an expression wasn't changed after execution, and in this case the colour of the watch expression is not
  changed
- the value of an expression was changed, and in this case the colour will be changed to bold blue
  ![state.png](/assets/images/features/watches/state.png)

An error value highlighted with red colour.

## Updating watches

Watches uses the same connection as the console to query values, and if an instance is not available or busy,
appropriate 'updating' message is shown after 1 second if a result can be received.
![updating.png](/assets/images/features/watches/updating.png)

Watches are designed to be very light functionality and even any expression can be watches, it could be very wise to add
only simple variables to watches and avoid tables or function calls.
{: .notice--warning}

## Table Result

As tables can't be shown in the limited space of watches, only they schemas if shown but state is calculated based on
all data in the tables.

You can expand a table or a dictionary from the context menu or by double-click on the value.

![table.png](/assets/images/features/watches/table.png)

Please avoid big tables in watches as it takes a lot of time for state calculation and receiving the tables.
{: .notice--warning}

## Manual Refreshing

Even all watches are auto-refreshed, you can manually refresh selected or all watches from the context menu.