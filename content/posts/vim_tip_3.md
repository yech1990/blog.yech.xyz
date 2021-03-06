+++
title = "随手记录点vim技巧(三)"
description = "vim 怎么快速插入 iso-8601 格式的时间戳？"
featured_image = "/img/nvim_custom_config.png"
date = 2018-02-01T15:21:53+08:00
categories = ["coding"]
tags = ["vim", "editor"]
comment = true
+++

> Q: vim 怎么快速插入 iso-8601 格式的时间戳？

<!--more-->

修改`~/.vimrc`，加入以下两行：

```
nmap <F8> i<C-R>=system('date --iso-8601=second')<CR><Esc>
imap <F8> <C-R>=system('date --iso-8601=second')<CR>
```

输出格式：

`2018-02-01T15:26:36+08:00`

vim 内置命令`strftime("%FT%T%z")`输出的结果是`2018-02-01T15:26:36+0800`，和 iso-8601 类似，但时区少了分割，不完全兼容。
故调用系统`date`命令。

---

> Q：什么是 iso-8601 格式？

**yyyy-mm-ddThh:mm:ss±hh:mm**

- **第一部分**：完整年月日（完整意味着位数不够用 0 补齐，像`2018-1-1`这样，是不符合格式的）
- `T`分割日期和时间
- **第二部分**：完整时分秒
- **第三部分**：时区偏移量（当地时间和 UTC 的偏差，可以带正号或负号）
- 日期时间都是当地的时间，比如偏差量`+08:00`，反推 UTC 的时候应该是 `UTC = localTime-8:00`，这里有点反直觉。
