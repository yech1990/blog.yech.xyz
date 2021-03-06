+++
title = "Cascade Notation in Dart is Magic"
description = ""
featured_image = "https://avatars1.githubusercontent.com/u/1609975?s=400"
date = 2020-03-12T18:43:07+08:00
categories = ["coding"]
tags = ["dart"]
comment = true
+++

在编写 Python 代码的时候，`sort()` 和 `sorted()` 是两个不同的函数，对于列表 `l = [2, 6, 1]`，
可以用 `l.sort()` 来进行排序，也可以用 `sorted(l)`
来进行排序。但是如果打印出来会发现，

```python
>>> print(l.sort())
None

>>> print(sorted(l))
[1, 2, 6]
```

原因是 `sorted()` 返回（return）的是变换后的列表，`.sort()`
是对列表进行**原位**地排序，虽然列表改变了，但是返回的是 None。
所以要输出 `.sort()` 的结果，需要两步。

```python
>>> l.sort()
>>> print(l)
[1, 2, 6]
```

这可能是 Python 维护了两个排序函数的原因，同时 `sorted` 的使用频率也高一点。

Dart 语言里面 List 也有 `.sort()` 函数，和 Python 类似，运行以下代码，输出的结果是 `{null}`。

```dart
void main() {
  var l = [2, 6, 1];
  print(l.sort());
}
```

但是 Dart 里面无需额外的 `sorted()` 函数来实现这个功能，只要把 `l.sort()` 换成 `l..sort()` 即可获取排序后的列表。
这里用到了 Dart 的 **Cascade Notation**[^1]，`..` 表示调用函数后依旧返回对象本身。

因此，可以高效地实现很多有趣的功能，例如：

```dart
void main() {
  var l = [1, 6, 2];
  l
    ..add(10)
    ..add(8)
    ..add(20)
    ..sort();
  print(l);
}

// output: [1, 2, 6, 8, 10, 20]
```

[^1]: https://dart.dev/guides/language/language-tour#cascade-notation-
