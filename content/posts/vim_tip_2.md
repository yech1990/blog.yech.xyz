+++
title = "随手记录点vim技巧(二)"
description = "删除到/插入到/移动到 行首怎么搞?"
featured_image = "/img/nvim_custom_config.png"
date = 2015-12-27T23:41:23+08:00
categories = ["coding"]
tags = ["vim", "editor"]
comment = true
+++

> Q: 删除到/插入到/移动到 行首怎么搞?

<!--more-->

- 有 N 种方法

| 命令       |    按键     |
| ---------- | :---------: |
| 移动到行首 | `(` `^` `0` |
| 移动到行尾 |   `)` `$`   |
| 插入到行首 |     `I`     |
| 插入到行尾 |     `A`     |
| 删除到行首 |    `d(`     |
| 删除到行尾 |  `d)` `D`   |

- 最规范的还是行用() 段用{}
