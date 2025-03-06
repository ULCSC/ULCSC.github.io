---
title: Install Guide for Powershell 7
date: 2025-03-06 10:17:00 -0700  
categories: [Tutorial]
tags: [tutorial, windows, shell, powershell]
author: Parker
description: A guide for installing Powershell 7 
---

Windows contains a few different terminals and they are all a little different
from one another. I would recommend using Powershell 7 since it is the newest
terminal offered by Microsoft. While it is similar to Powershell 5, Powershell 7
is a broader version allowing more modules and scripts to be used. While not
identical, Powershell uses many of the same commands like Linux does like "cd"
and "ls" allowing for muscle memory to develop.

## Installing

There are a few ways to install it.

### Winget

Winget in a package manger for WIndows and contains the necessary files for
Powershell 7. It should install once run for the first time but you might need
to accept a few conditions first. Open up the terminal and run:

```sh
winget search Microsoft.PowerShell
```

This will give you two options. There is no need to use the preview version so run

```sh
winget install --id Microsoft.PowerShell --source winget
```

There you go! Just find Powershell 7 in your program list and run it!

## Issues / Feedback / Contributing

If you see any problems with these pages (incorrect information, misspelled
words, incorrect formatting), please create an issue on the repo, or let one
of the executives know.

If you have an idea for a resource or page that could be useful, please make a
pull request so it can be added to the site, see more detail in the README.
