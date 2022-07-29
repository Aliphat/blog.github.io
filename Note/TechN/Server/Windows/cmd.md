# 教你如何使用cmd，俗称命令提示符?

## 导出文件夹中的所有文件的名字

```bash
dir /b>1.txt
```
然后就会生成一个  1.txt的文件





## 将txt文本中的ip，改为ip段

> 从本地文件夹中找到a.txt，然后批量替换后，输出名为out.txt的文本

[教程来源：bat读取文本内容用法](https://wenku.baidu.com/view/aa3d6ae84593daef5ef7ba0d4a7302768e996fe3.html)

```bash
@echo off
set file=a.txt
(for /f "tokens=1-3 delims=." %%a in (%file%) do echo %%a.%%b.%%c.0 %%a.%%b.%%c.255)>$
move $ out.txt>nul 2>nul
exit
```

