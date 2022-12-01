---
title: "Setup KDB SDK"
permalink: /project/sdk
excerpt: "Creating new KDB+ Q SDK for local testing"
toc: true
---

## Overview

If you need to do local testing or just start a local KDB instance from IDEA you have to create new KDB+Q SDK if not
done yet.

## Configuration

To do that, please open [project structure](https://www.jetbrains.com/help/idea/project-settings-and-structure.html) and
select 'SKDs' tab in 'Platform Settings' section where you can see all current SDKs for all languages:

![sdkSettings](/assets/images/project/sdk/sdkSettings.png)

When just press add 'plus' button to create new one:

![sdkCreating](/assets/images/project/sdk/sdkCreating.png)

and select home Q folder where QHOME environment variable is pointed to:

![sdkHomeFolder](/assets/images/project/sdk/sdkHomeFolder.png)

and new KDB SDK will be added to configuration where you can always change any it's parameter:

![sdkOptions](/assets/images/project/sdk/sdkOptions.png)

## Project SDK

Depends on your setup, you can select SDK for the whole project in the same project settings dialog:

![sdkProjectLevel](/assets/images/project/sdk/sdkProjectLevel.png)

## Module SDK

If you have multi-modules project with mix of language, you can select KDB SDK for particular module only. Just select
appropriate module and required SDK on 'Dependencies' tab:

![sdkModuleLevel](/assets/images/project/sdk/sdkModuleLevel.png)