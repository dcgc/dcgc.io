---
layout: page
title: Scripting / Command-line
categories: notes
permalink: /scripting/
---

## CMD

- 0 STDIN - Input
- 1 STDOUT - Output
- 2 STDERr - Error
- Streams are redirected and piped with > >> & < |
- program.exe > textfile [create file; if file exists, it is clobbered or replaced]
- program.exe >> textfile [append file; if file not exists, it is create]
- prog1.exe | prog2.exe [pipe STDOUt to STDIN]
- program.exe < textfile [input from textfile]
- program.exe 2> null [only STDOUT displayed]
- program.exe 1> null [only STDERR displayed]
- program.exe > stdout.txt 2> stderr.txt [put STDOUT and STDERR in separate files]
- dir /a/b/s
- netstat -ano


## PowerShell

- $host.version
- Execution Policy
  -  AllSigned will allow scripts to run, but they must be signed by a recognized key.
  -  Bypass will allow any script to run, nothing is blocked.
  -  Default is Restricted for Windows clients and RemoteSigned for servers
    -  RemoteSigned will allow scripts to run. However, they must be signed; config files must also be signed. Local scripts do not need to be signed.
    -  Restricted will not allow scripts to be run or config files to be loaded.
  -  Undefined defaults back to Restricted on clients.
  -  Unrestricted is default on non-Windows computers, warns on remote scripts and config files.

- Get-HotFix
- PSWindowsUpdate > Windows Update Service wuauserv > Get-WUInstall
- 
