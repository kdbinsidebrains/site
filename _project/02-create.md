---
title: "New Project"
permalink: /project/create
excerpt: "Creating your first project for KDB"
toc: true
---

## Create Project

JetBrains have excellent docs how to create new
projects: [https://www.jetbrains.com/help/idea/creating-and-managing-projects.html]().

Depends on what you already have, you
can [create new project](https://www.jetbrains.com/help/idea/new-project-wizard.html) or
[import project](https://www.jetbrains.com/help/idea/new-project-wizard.html) from exist sources or even get the project
from a source control system, like Git:

![New Project Types](/assets/images/project/create/newProjectTypes.png)

Just open 'File->New' menu and go through all steps

## Blank Project

### New Project Menu

If you don't have any exist source code that you can use, you have to create new blank project:
![blankProjectMenu](/assets/images/project/create/blankProjectMenu.png)

### Project SDK

If you have had [installed KdbInsideBrains plugin](/project/start#plugin-installation) correctly, on this stage
you must see 'KDB+ Q' generator for new project:

![New Project - SDK](/assets/images/project/create/newProjectStep1.png)

There is only one part that you can initialize here - KDB+ Q SDK or binaries setup. It's required only if you'd like to
start local KDB process on local workstation for testing.

You can skip this step and add it later and go to the next step or please
check [how to set up KDB+ Q SDK](/project/sdk).
{: .notice}

### Project Location

At this step you can define where the project files will be located.The simplest way is just change the project name
that will update all dependant fields for you:

![New Project - Folders](/assets/images/project/create/newProjectStep2.png)

Your project must have at least one module that contains definition of source code configuration. By default, module
name equals to the project name but can be any. Please check JetBrains docs to get more info about
modules: [https://www.jetbrains.com/help/idea/creating-and-managing-modules.html]()

You also can find which project formats are the best for you in the official
docs: [https://www.jetbrains.com/help/idea/creating-and-managing-projects.html#project-formats]()

## From Exist Sources

### Importing Menu

Highly likely you already have existed source code and in this case you can create new project from exist source code:

![existCodeMenu](/assets/images/project/create/existCodeMenu.png)

### Source Location

Just select folder with your Q code:

![existCodeImport](/assets/images/project/create/existCodeImport.png)

### Importing Model

As it's Kdb project, probably you don't use Maven or Gradle or any other Java build tool so just create new project:

![existCodeImportType](/assets/images/project/create/existCodeImportType.png)

### Project Location

Like for new project, you have to choose project name (that is the folder name by default) and location as well. You
also can find which project formats are the best for you in the official
docs: [https://www.jetbrains.com/help/idea/creating-and-managing-projects.html#project-formats]()

![existCodeImportName](/assets/images/project/create/existCodeImportName.png)

### Project Content

If you have [installed the plugin](/project/start#plugin-installation) correctly, on the next step your KDB+ Q
code myst be auto-detected:

![existCodeContent](/assets/images/project/create/existCodeContent.png)

### Project SDK

There is only one part that you can initialize here - KDB+ Q SDK or binaries setup. It's required only if you'd like to
start local KDB process on local workstation for testing.

You can skip this step and add it later and go to the next step or please
check [how to set up KDB+ Q SDK](/project/sdk).

![existCodeSDK](/assets/images/project/create/existCodeSDK.png)

### Detected Framework

Finally on the last step you can see the project structure and detected frameworks. If you have only Q code, 'KDB+ Q
Language' framework will be detected, but you can see more if you have mix of programming languages and depends on your
IntelliJ IDEA version:

![existCodeFramework](/assets/images/project/create/existCodeFramework.png)

## From Version Control

One of the greatest options in IntelliJ IDEA is ability to get source code directly from a Version Control system.
Just select appropriate (and supported, depends on your IntelliJ IDEA version) version control system and type required
parameters:

![vcsMenu](/assets/images/project/create/vcsMenu.png)

In contrast to other ways, there are no addition settings at importing time but after import is finished, you can see
popup notification in the right bottom corner with depected frameworks:

![vcsNotification](/assets/images/project/create/vcsNotification.png)

Just press 'Configure' to see which frameworks and were detected here:

![vcsFrameworks](/assets/images/project/create/vcsFrameworks.png)