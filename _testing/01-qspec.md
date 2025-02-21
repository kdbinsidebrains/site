---
title: "QSpec Testing Framework"
permalink: /testing
excerpt: "QSpec Testing Framework"
toc: true
---

## Overview

The plugin prides integration with QSpec testing framework by Nugend: https://github.com/nugend/qspec.

The framework allows you to run an individual expectation, or a test case, or file or all files in a directory with
processing all status, times and logs per each test:   
![QSpec Overview](/assets/images/testing/qspec/overview.png)

## Initialization

To run tests on local PC with the plugin, you need to install the following applications:

- KDB+ binaries to run KDB on local machine. You can download one from the official KX
  website: https://kx.com/kdb-personal-edition-download/
- [Setup KDB SDK](/project/sdk) to run the binaries from the plugin
- Download QSpec libraries from GitHit https://github.com/nugend/qspec (this step can be done from the plugin
  configuration page). You don't have to install it as described on the main GitHub page but just download as is. QUtil
  lib is not required for the plugin.

Once you have all binaries and libraries, open _QSpec Testing_ item in [KDB+ Q settings page](/settings/options) to
provide the path to downloaded QSpec lib, or you can download the lib directly from the page:
![QSpec Downloading](/assets/images/testing/qspec/downloading.png)

You can also provide a custom configuration script if it's required for your project. For example, in case if you need
to define some variables for tests or load custom libraries.

## Running Test Cases

You can run all tests in a file, particular test case or even an expectation from the Editor.
![QSpec Running](/assets/images/testing/qspec/running.png)

You can run all test cases in a folder from Project View.

You can also you Test View windows to re-run any tests or re-run all failed tests, or _Jump to Source_ for each test.
![QSpec ReRun](/assets/images/testing/qspec/rerun.png)
