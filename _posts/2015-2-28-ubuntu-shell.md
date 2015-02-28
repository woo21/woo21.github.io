---
layout: post
title:  "Ubuntu shell"
tags: ubuntu bash dash
---

Ubuntu 6.10開始之後, `/bin/sh`預設為`dash`, 為何要作此改變呢?

主要是效率考量, 往往Ubuntu開機速度過慢都會歸究於[Upstart](http://upstart.ubuntu.com/), Upstart在init系統下是一個很好的平台,
Bash擁有豐富功能shell, 所以在開機執行速度相較使用Dash慢上許多, 所以Ubuntu core team才決定預設為dash, 但login shell還是使用bash.

但有可能會遇到編譯程式或是shell scripts會出現問題, 有幾種方法可解決

* `#!/bin/sh` 改寫成 `#!/bin/bash`
* makefile加上變數 `SHELL=bash`

如果還是想停止使用dash, 可以使用
`sudo dpkg-reconfigure dash`
但可能會遇到一些問題, 開機scripts是使用dash, 而bash並沒有提供.

