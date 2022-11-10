---
layout: page
title: Scripting
categories: notes
permalink: /scripting/
---

## CMD and Bash

- Outputs in text
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
