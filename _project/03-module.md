---
title: "Setup Module"
permalink: /project/module
excerpt: "Creating new KDB module for existing project"
toc: true
---

## Module Settings

It's possible that you already have a project or create/import project but Q code was not loaded correctly. In this case
you can change your project structure and do module setup manually.

Just open [project structure](https://www.jetbrains.com/help/idea/project-settings-and-structure.html) dialog and select
modules tab there:

![moduleStructure](/assets/images/project/module/moduleStructure.png)

## Create Module

If you need new module for Q code, there is nothinge more simple rathen than press + (plus) button at the modules'
toolbar and choose 'KDB+ Q' module type:

![moduleCreateSDK](/assets/images/project/module/moduleCreateSDK.png)

Like in [project creation](/project/create#blank-project), you can select [KDB SDK](/project/sdk), if required, and
provide new module name and path at the next step:

![moduleCreatePath](/assets/images/project/module/moduleCreatePath.png)

If you already have a KDB Module you can import it the same way. Just choose 'Import Module' and go through the same
steps.
{: .notice--info}

## Add Framework

If you already have a module of another (java or mixed), you can just add 'KDB+ Q Language' framework to it. Just
right-click on the module, select 'Add' and 'KDB+ Q Language' at the end:

![frameworkAdd](/assets/images/project/module/frameworkAdd.png)

Please note, to be able to [run](/project/run) any Q file in local KDB instance the module must
have [KDB SDK](/project/sdk) set as the module SDK:<br><br>
![moduleStructure](/assets/images/project/module/moduleStructure.png)
{: .notice--warning}

## Module Content

One of the most important thing about modules - how to define its structure and content as it has a direct impact on
ability to run and scan Q files.

Even the IDEA has many content types, like 'source', 'tests', 'resources' and so on, for now only 'source' makes sense
for KDB module and everything under 'source' is treated as the module root. 

All file loads and like
~~~ q
\l code/log.q
\l code/config.q
\l code/tables.q
~~~
will be resolved to the module's source directories.

If module has no 'source' folders, its 'Content root' will be used instead.

![moduleContent](/assets/images/project/module/moduleContent.png)