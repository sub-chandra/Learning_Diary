---
file_type: "Manual" 
file_catalogue: "Computer Science" 
Catalogue: 
  Main: "DOS"
  Secondary: ".bat"
CreateTime: 2022
---

#Template/Knowledge/Manual/Main_Basic  
>[!INFO] Introduction
>This page introduces the usage of the   `.bat`
>
>**<font color="#ffa900">LINK:**</font>
>- [批处理菜鸟教程_BetaGarf的博客-CSDN博客_bat教程 菜鸟教程](https://blog.csdn.net/Joker_N/article/details/89838719)
> - [Windows 批处理(bat)语法大全_MakeGreatEffort的博客-CSDN博客_bat语法](https://blog.csdn.net/qq_36838191/article/details/83046599)\
>-  [bat 批处理教程_w3cschool](https://www.w3cschool.cn/dosmlxxsc1/wvqyr9.html)


**Bat 批处理的换行符切记是 CRLF（\r\n）**

如果使用 [VSCode](https://so.csdn.net/so/search?q=VSCode&spm=1001.2101.3001.7020) 编辑 Bat 文件时使用的换行符是 LF（\n），将导致 Bat 处理非首行的指令时运行出错，被这害惨了，耗费了很长时间，无意间看到 VSCode 如下图所示处：

括号“（” 要位于跟if 同一行，如果不在同一行的话执行时会报语法错误。

```c
if …… ( 
 echo ……
 echo ……
 ……
) else (
 echo ……
 echo ……
 echo ……
 echo ……
)
```
