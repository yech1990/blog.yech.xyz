+++
title = "奇异矩阵（singular matrix）和 非奇异矩阵（nonsingular matrix）"
date = "2015-12-27T00:27:27+08:00"
tags = ["math"]
categories = ["sci"]
draft = false
+++

# 奇异矩阵（singular matrix）

# 非奇异矩阵（nonsingular matrix）

> 对于矩阵 A，如果存在一个矩阵 B，使得 AB=BA=I，其中 I 为与 A,B 同维数的单位阵，就称 A 为可逆矩阵（或者称 A 可逆），并称 B 是 A 的逆矩阵，简称逆阵。（此时的逆称为凯利逆） 　　矩阵 A 可逆的充分必要条件是|A|≠0。 　　奇异矩阵阵或非方阵的矩阵不存在逆矩阵，但可以用函数 pinv(A)求其伪逆矩阵。基本语法为 X=pinv(A),X=pinv(A,tol),其中 tol 为误差：max(size(A))*norm(A)*eps。函数返回一个与 A 的转置矩阵 A' 同型的矩阵 X，并且满足：AXA=A,XAX=X.此时，称矩阵 X 为矩阵 A 的伪逆，也称为广义逆矩阵。pinv(A)具有 inv(A)的部分特性，但不与 inv(A)完全等同。
> 如果 A 为非奇异方阵，pinv(A)=inv(A)，但却会耗费大量的计算时间，相比较而言，inv(A)花费更少的时间。
> 奇异矩阵是线性代数的概念，就是对应的行列式等于 0 的矩阵。
> 奇异矩阵的判断方法：首先，看这个矩阵是不是方阵（即行数和列数相等的矩阵。若行数和列数不相等，那就谈不上奇异矩阵和非奇异矩阵）。 然后，再看此方阵的行列式|A|是否等于 0，若等于 0，称矩阵 A 为奇异矩阵；若不等于 0，称矩阵 A 为非奇异矩阵。 同时，由|A|≠0 可知矩阵 A 可逆，这样可以得出另外一个重要结论:可逆矩阵就是非奇异矩阵，非奇异矩阵也是可逆矩阵。