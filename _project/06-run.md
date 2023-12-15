---
title: "Run Configuration"
permalink: /project/run
excerpt: "Create new runnable KDB configuration"
toc: true
---

## Overview
This functionality is available in _InelliJ IDEA_ product. In all other platforms this functionality is not available.
{: .notice--warning}

## New Local Process

One of the features of the IDEA and the plugin is to be able to start local KDB instance just by one click on a file.

You must set up the correct [KDB SDK](/project/sdk) for your project or module.
{: .notice--info}

Just right-click on any Q file in the project tree and select 'Run <filename>' menu:

![runFromProject](/assets/images/project/run/runFromProject.png)

IDEA provides the ability to run a process in _'Debug'_ mode or _'Run tests Coverage'_. For KDB process, there is no
difference, and any of the options just start local KDB instance.  
{: .notice}

Please make sure you have correct [module content is set up](/project/module#module-content) and source or content root
folder is set correctly.
{: .notice--info}

## Modify Run Configuration

When you start a new process from the project tree, all required parameters are taken from module configuration and KDB
SDK, but you can change all of them or add more parameters with 'Modify Run Configuration':

![runModifyMenu](/assets/images/project/run/runModifyMenu.png)

and in the opened dialog you can set:
- Name of the run (you can select the process by the name from 'Run' menu)
- Module that will be used as content and SDK source (the module must have KDB SDK as SDK)
- Script path, that is filled from running file
- Any process arguments, like _-p <port>_ or any other KDB parameters
- Working directory that will be used as the root for the file
- Environment variables

![runModifySetup](/assets/images/project/run/runModifySetup.png)

You can modify all these arguments later in Run/Debug Configuration dialog available from the main menu:
![runEditConfiguration](/assets/images/project/run/runEditConfiguration.png)
{: .notice--info}
