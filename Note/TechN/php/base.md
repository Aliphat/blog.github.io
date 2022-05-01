# PHP入门的简单教程

#### 第一章入门
```PHP
#!/usr/bin/php
<?php
echo 'hello shiyanlou';
?>
```

#### 第二章

##### 1.将PHP代码嵌入HTML中 
```php
<?php 
$highlight = true;
?>
<html>
  <body>
    <p <?=$highlight ? "class='highlight'" : ''?>>
    This is a paragraph
    </p>
  </body>
</html>
?>
```

##### 2.PHP注释相关
```php
<?php
#单行注释
echo 'Hello World';

$a = 'shiyanlou';//单行注释

/**
 * 多行注释
 * 注释内容
 *
 */
?>

```


#### 第三章PHP 支持 8 种原始数据类型。

四种标量类型：

boolean（布尔型）
integer（整型）
float（浮点型，也称作 double)
string（字符串）

两种复合类型：
array（数组）
object（对象）

最后是两种特殊类型：
resource（资源）
NULL（无类型）