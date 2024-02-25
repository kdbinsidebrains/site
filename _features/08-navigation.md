---
title: "Navigation"
permalink: /features/navigation
excerpt: "Navigate around code inside a project"
toc: true
---

### Find Usages

You can do search of all usages for any variable defined in the [Code Editor](/features/editor).

To do that, you should put the cursor on the variable name and press _Alt+F7_ hot key to find a variable usages (or use
_Edit/Find Usages_ main or popup menu):

![navigationFindAll](/assets/images/features/navigation/navigationFindUsages.png)

The result is grouped by usage context as well as by files.

At this moment the plugin doesn't search text files, like csv or txt. We recommend doing full search if you have some
text config files in your project.
{: .notice--warning}

### Call Hierarchy

Any option for find usages or a variable is to build calls hierarchy for the variable.

To do that,
you should put the cursor on the variable name like for _Find Usages_ and press _Ctrl+Alt+H_
or use main
menu [Navigate/Call Hierarchy](https://www.jetbrains.com/help/idea/viewing-structure-and-hierarchy-of-the-source-code.html):

![navigationCallHierarchy](/assets/images/features/navigation/navigationCallHierarchy.png)

The _Call Hierarchy_ opens new _Tool Dialog_ with found results separated into two categories:

- You can view all **callers** - do search all functions or expressions that call or use the variable:

  ![navigationCallers](/assets/images/features/navigation/navigationCallers.png)
  This functionality is useful if you need to find out all dependencies on the variable. This view is enabled by
  default.


- You can view all **callees** - works only for a lambda definition and shows all functions, tables, symbols and other
  elements used by the lambda:

  ![navigationCallees](/assets/images/features/navigation/navigationCallees.png)