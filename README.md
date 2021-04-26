# 公民身份证信息查询awk源程序

## 例子

```bash
$ awk -f sfzcx.awk ../gb2260/gb2260/data/latest.csv

公民身份证号信息查询awk源程序！
  如果输入真实号码，则给出分析信息
  如果输入不明号码，则给出诊断信息
-------------------------------------------------------
请输入要查询的公民身份证号（18位）：440524188001010014
查询的身份证号：440524188001010014

查询到该公民身份证信息如下：

[○] 该身份证号可能有问题！在该年(1880)出生的持有者很可能已经死亡
[●] 出生日期码的月部分有效
[●] 出生日期码的日部分有效
[×] 当前年或出生年有问题，无法计算年龄和生肖
[●] 性别        男
[●] 该户籍区域内和他同年月日生的男性只有他一个
[●] 地址        广东省汕头市

```

## 安装方法

1. `git clone https://github.com/khaeru/gb2260.git`
2. `git clone https://github.com/mike2718/sfzcx.git`
3. `cd sfzcx`
4. `awk -f sfzcx.awk ../gb2260/gb2260/data/latest.csv`

## 程序设计的理念

对于输入的身份证号，尽可能详尽的给出分析，列出可靠的和不可靠的个人信息，以便给使用者判断真假的提示。

程序运行上尽可能依照标准GB 11643-1999。

## 写程序的动机

由于自己和乙方签协议时，乙方给出了有问题的身份证号，导致自己提起诉讼时引起了各种麻烦，
于是想到做一个判断身份证号真伪的程序。

## 依赖

- [One true awk (version 20180827)](https://github.com/onetrueawk/awk/releases/tag/20180827)
- [GB/T 2260 codes for the administrative divisions of the People's Republic of China](https://github.com/khaeru/gb2260)
