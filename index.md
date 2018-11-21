# PHP编码规范
>写在前面：本文适用于前端团队协作时使用，目的为形成统一的编码风格，仅供参考。这里也先简单介绍下几种常见的命名法：匈牙利命名法，编写规范为“变量名=[属性＋]类型＋对象描述”，这种写法可以看出变量的一些基础信息，如：m_strName；骆驼式命名法，主要采用大小写混合的方式来表示变量，这种方式目前较为流行，如：myName(小驼峰)；帕斯卡命名法（也可叫大驼峰命名法），变量名以几个大写字母开头的单词拼接而成，如：MyName；下划线命名法：采用下划线来拆分单词，如：my_name，在C语言中较为常见。

# 一、命名规范

## 1、变量名
- 采用比较直观的 **“小驼峰命名法”**（即：首字母小写）来编写，绝大部分场景均以【名词】为准，前缀可以加【形容词】;
- 变量名包括全局变量、局部变量、函数的传参等，必须是能表示某种含义的 **英文** ，禁止使用拼音，
- 禁止使用保留字，[保留字查询地址>](http://php.net/manual/zh/reserved.keywords.php)

如：

```php

// 正确示例
$userName = "Johnxy";
$rankList = array("Johnxy", "Rye");

// 错误示例
$queryUserName = "Johnxy"
$getRankList = array("Johnxy", "Rye")

```

## 2、常量名

采用全大写的下划线命名方式，使用这种命名方式的绝大部分场景也为【形容词】+【名词】，如：

```php

// 正确示例
define("BASIC_CONFIG", array("token" => "fdasfdsa"));

// 错误示例
define("Basic_Config", array("token" => "fdasfdsa"));

```

## 3、常用函数名

函数名（构造函数除外）和变量名类似，采用比较直观的“小驼峰命名法”来编写，使用这种命名方式的绝大部分场景也为【动词】+【名词】，如：
```php
// 正确示例
function sayHi() {
  print_r("Hi!Johnxy.");
}

// 错误示例
function SayHi() {
  print_r("Hi!Johnxy.");
}
```
常用动词前缀

|前缀|返回类型|说明|
|---|---|---|
|is|Boolean|常用于“是否”的判断|
|has|Boolean|常用于“有无”的判断|
|can|Boolean|常用于“能否”的判断|
|set|Boolean|操作结果，也可不返回或通过回调方法接受结果|
|get|Object|常用于返回一些数据，有时也通过回调的方式返回结果|

```php
// 正确示例
function isVip() {
    // your code
    return true
}

function hasTail() {
    // your code
    return true
}

function canFly() {
    // your code
    return true
}

function setUserInfo(info) {
    // your code
    return true
}

function getUserInfoById(id) {
    // your code
    return info
}

```

## 4、构造函数及类

构造函数及类名采用帕斯卡命名法，这样写的好处：与普通函数做一些区分；让使用者很明确使用方式。使用这种命名方式的绝大部分场景也为【名词】，类的私有属性或私有方法建议采用下划线加小驼峰命名法，如：
