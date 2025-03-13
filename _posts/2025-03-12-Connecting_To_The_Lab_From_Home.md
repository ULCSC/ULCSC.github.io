---
title: Connecting to the Lab from Home
date: 2025-03-12 21:24:00 -0700
categories: [Tutorial]
tags: [osx, mac, windows, help, terminal, tutorial]
author: David Peters
description: Guide to connecting to the school lab from home using SSH and SFTP
---

The following is a quick guide to connecting to the school linux machines using
SSH (secure shell) and SFTP (secure file transfer protocol). Please note that this guide
will be made as accurate as possible, but processes change and differences in personal machines
cannot be completely accounted for. If you run into trouble, speaking to a faculty member
such as the system admin is your best bet.

> DISCLAIMER: The University of Lethbridge is not responsible for the setup of
> your machine. This guide has been created by the ULCSC. The information in this
> tutorial should be correct for the most part, however you should still
> proceed with with discretion.
{: .prompt-warning }

## What are SSH and SFTP?

SSH is a protocol used to securely connect to a remote machine over an encrypted connection.
It allows users to execute commands through the terminal on a remote host.
SSH is how you will run commands as if you were working from the terminal in the lab.

SFTP is a file transfer protocol that runs over SSH (If you have SSH, you likely have SFTP access as well).
It allows the user to upload, download and manage files remotely and securely. This is how you will move files 
to and from your local machine to the lab server. 

> This guide will use the command line as that is the most machine agnostic.
{: .prompt-info }

### Checking if SSH is installed

To check whether or not SSH is installed, open a terminal session and type `ssh` or `ssh -V`

Most operating systems (Windows, Mac, Ubuntu, etc) will come with a built-in SSH client, but if 
that isn't the case, you should get an error along the lines `commmand not found`, `not recognized`, etc.

Otherwise, you should see something `usage:` and some information on how to use the SSH command.

If SSH is not installed, run the command for your respective operating system:
- Windows: `Add-WindowsFeature -Name OpenSSH.Client`
- Mac: `brew install openssh` (If you do not have homebrew installed, checkout the OSX Setup tutorial)
- Ubuntu: `sudo apt install update && sudo apt install openssh-client`

### Connecting to the University VPN

You can check out the Univerity's guide for using the VPN [here](https://uleth.service-now.com/sp?id=kb_article&sys_id=ca29e6373bc95e1062aa675aa5e45ada)

Contact IT Services if you encounter issues using the VPN

## Using SSH and SFTP

In order to use the SSH and SFTP, you will need your linux lab login credentials given by your instructor or system admin.

For example, John Doe in CPSC 1620 would have a login of the form doej1620. If you do not have these credentials speak to your instructor.

Run the SSH command with `ssh doej1620@student0.cs.uleth.ca`,
`student0`, `student1` and `student2` are all available for use. If one isn't working, it's worth trying another.

You will be prompted for your password. After successfully logging in, you will now be in a terminal session on the school network
where you can run commands as you would from the lab, including runnings your programs to ensure they work on the schools machines.
Checkout "Basic Terminal Use" if you need a refresher.

Similarly, you can enter a SFTP session by running `sftp doej1620@student0.cs.uleth.ca`, the process is the same.
The `put <filename>` will move a file from your current local machines directory to the remote machines current directory.
The `get <filename>` will behave similarly, but for retrieving files from the remote machine and storing them on your local machine.
You can also provide a path `get ~/example/assignments/<filename>` to get or put files outside of the present directory.

> Prefix commands with 'l' (lls, lcd, lpwd) to run the command on your local machine
> Commands without the 'l' prefix will be ran on the remote machine.
{: .prompt-warning }

```zsh
sftp doej@student0.cs.uleth.ca
# prompted for password

# show local files
lls 

# show remote files
ls

 # move a file from local machine to remote
put <filename>

# retrieve a file from remote machine to local
get <filename>
```

Now you can sftp to the school network, move the files you've been working on from home,
 and then ssh in and run them remotely before submitting (which you should always do).

There are a bunch of other fancy tools you can look into if you'd like a GUI, or to avoid 
using seperate ssh and sftp sessions, using IDEs such Visual Studio Code, etc. This guide 
should get you started however when you need to quickly run a program and want to save yourself 
the drive/bus ride.

### Exiting a SSH or SFTP session

Use the `exit` command to exit a SSH session.

Use the `bye` command to exit an SFTP session.

## Issues / Feedback / Contributing

If you see any problems with these pages (incorrect information, misspelled
words, incorrect formatting), please create an issue on the repo, or let one
of the executives know.

If you have an idea for a resource or page that could be useful, please make a
pull request so it can be added to the site, see more detail in the README.
