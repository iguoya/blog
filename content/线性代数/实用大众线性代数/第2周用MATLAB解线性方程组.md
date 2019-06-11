---
title: 第二周用MATLAB解线性方程组
date: 2019-01-16 16:20:44
categories: ["线性代数", "实用大众线性代数"]
tags: ["计算工具", "MATLAB", "矩阵转置", "单位矩阵"]
---

# MATLAB语言概述



## 科学计算工具

| 年代              | 计算工具                    |
| ----------------- | --------------------------- |
| 东汉（220年左右） | 算盘                        |
| 1630年            | 计算尺                      |
| 1970年            | 计算器                      |
| 1980年开始        | 计算机及科学计算语言 MATLAB |



```highlight
线性代数 是计算机显示其优越性的最早的发源地
不要墨守经典，无视现代。
成为时代进步的实践者和宣传员
```

## MATLAB语言特点

```highlight
MATLAB：MATrix LABoratory 
以矩阵运算为基础的交互式程序语言
```

1. 起点高

2. UI

3. 作图功能

4. 功能和可扩展性

   

---

# 基本语法



1. 标识符
2. 矩阵及其元素赋值
3. 复数
4. 变量检车
5. 基本赋值矩阵

## 标识符

大小写区别， 首字符英文
双精度的64位 （8个字节）10的+- 308次幂

## 矩阵赋值

```matlab
A = [1 2 3; 4 5 6; 7 8 9]
A =

     1     2     3
     4     5     6
     7     8     9
```
## 元素赋值
```matlab
A(4,3) = 6
A =

     1     2     3
     4     5     6
     7     8     9
     0     0     6
     6     6     6
     

A(5,:) = [ 6 6 6 ]
A =

     1     2     3
     4     5     6
     7     8     9
     0     0     0
     6     6     6
     
```



## 元素提取

```matlab
b = A([2, 4], [1, 3]) % (行, 列) %
b =

     4     6
     0     6
```
## 元素的删除
```matlab
A([2, 4, 5], :) = [] % 2 4 5 行 删除
A =

     1     2     3
     7     8     9
```
## 常数乘法
```matlab     
A*2               %系数乘法%
ans =

     2     4     6
    14    16    18
```
## 矩阵转置 
M行N列  下标交换位置
```matlab
A'              %转置%
ans =

     1     7
     2     8
     3     9
```

---



# 特殊矩阵




## 赋值函数

| 函数名称    | 描述         |
| ----------- | ------------ |
| zeros(n, m) | 全0          |
| ones(n, m)  | 全1          |
| rand(n,m)   | 随机数矩阵   |
| randn(n,m)  | 正态随机矩阵 |
| eye(n)      | 单位矩阵     |

## 变量检查 who whos

```matlab
pause,f5=linspace(0,1,5)
f5 =
         0    0.2500    0.5000    0.7500    1.0000
pause,fb1=[f1,f3;f4,f2]
fb1 =
     1     1     8     1     6
     1     1     3     5     7
     1     1     4     9     2
     1     0     0     0     0
     0     1     0     0     0
pause,fb2=[fb1;f5]
fb2 =
    1.0000    1.0000    8.0000    1.0000    6.0000
    1.0000    1.0000    3.0000    5.0000    7.0000
    1.0000    1.0000    4.0000    9.0000    2.0000
    1.0000         0         0         0         0
         0    1.0000         0         0         0
         0    0.2500    0.5000    0.7500    1.0000
pause,f=[0.000073 5.33e-6]
f =
   1.0e-04 *
    0.7300    0.0533
pause,disp(' 变量的检查')
 变量的检查
pause,who

Your variables are:

A        U1       b        f1       f4       fb2      l1       logoax   x1       z        
L        a        c        f2       f5       g        l2       s        x2       
U0       ans      f        f3       fb1      ip       logoFig  x        y        


pause,whos
  Name          Size            Bytes  Class                                Attributes

  A             3x4                96  double                                         
  L            51x51            20808  double                                         
  U0            3x4                96  double                                         
  U1            3x4                96  double                                         
  a             4x3                96  double                                         
  ans           5x5               200  double                                         
  b             2x2                32  double                                         
  c             1x1                16  double                               complex   
  f             1x2                16  double                                         
  f1            3x2                48  double                                         
  f2            2x3                48  double                                         
  f3            3x3                72  double                                         
  f4            2x2                32  double                                         
  f5            1x5                40  double                                         
  fb1           5x5               200  double                                         
  fb2           6x5               240  double                                         
  g             1x1                16  double                               complex   
  ip            1x3                24  double                                         
  l1            1x1                 0  matlab.graphics.primitive.Light                
  l2            1x1                 0  matlab.graphics.primitive.Light                
  logoFig       1x1                 0  matlab.ui.Figure                               
  logoax        1x1                 0  matlab.graphics.axis.Axes                      
  s             1x1                 0  matlab.graphics.primitive.Surface              
  x             1x5                40  double                                         
  x1            1x1                 8  double                                         
  x2            1x1                 8  double                                         
  y             1x1                 8  double                                         
  z             2x2                64  double                               complex   

```





