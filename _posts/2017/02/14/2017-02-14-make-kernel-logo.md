---
layout: blog
istop: true
title: "用脚本生成内核logo"
background: purple
date:  2017-02-14
category: shell
tags:
- kernel
- linux
- shell
---

## 使用Shell脚本把png转换为ppm

```
#!/bin/bash

destName=`echo $1 | sed s/.png//`
logo=_logo
logoName=$destName$logo
pngtopnm $destName.png > $destName.pnm && pnmquant 224 $destName.pnm > temp.pnm && pnmtoplainpnm temp.pnm > $logoName.ppm
rm -f $destName.pnm temp.pnm
```
