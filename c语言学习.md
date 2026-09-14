# C语言第一个代码

```c
#include<stdio.h>

int main()
{
printf("hello world\nhello world ");
getchar();
    return 0;
}
```

1. \+字母组成转义序列

2. \n是换行

   

# 变量

## 变量与赋值

1. 声明一个整数a int a；
2. 声明一个小数b float b；
3. 初始化变量a为1，b为3.14      int a=1       float b=3.14； 
4. 给a、b赋值     a=2  b=5.6；
5. 变量的声明必须在使用前

## 变量的运算

1. 加 减 乘 除 取余
2. +-*/%

## 实际问题

### 设计c代码 计算长方体体积

```c
#include<stdio.h>
int lenth=2;
int width=3;
int high=4;
int volum;

int main()
{
    volum=lenth*width*high;

    printf("体积=%d立方米",volum);   //输出"体积=24立方米"

    return 0;
}
```

### 显示变量的符号

1. 占位符%
2. int类型的占位符 %d
3. 输出 printf(“体积=%d”, volum);

### 优化方案

```c
/*Project Name：1.c
 *Description：计算长方形体积
 *Author：自动26-2秦子铭
 *Date：2026/9/13
 */

/*整体代码结构分析
 *1.预处理指令之一，调用标准功能库
 *2.声明变量
 *3.main函数，有且只有一个
 *4。格式化输入/输出函数
 *5.运算语句
 *6.返回
 */ 


#include<stdio.h>                  //预处理指令之一，包含一些库文件

/*变量声明区*/
int lenth=2;                       //长的变量
int width=3;                       //宽
int high=4;                        //高
int volum;

int main()                         //主函数区，有且仅有一个
{ 


    printf("请输入物体的长：");       //格式化输入函数
    scanf("%d",&lenth);            //格式化输出函数

    printf("请输入物体的宽：");
    scanf("%d",&width);

    printf("请输入物体的高：");
    scanf("%d",&high);


    volum=lenth*width*high;        //运算语句

    printf("体积=%d立方米",volum);

    return 0;                      //返回
}
```

1. 读入用户输出内容赋值变量
2. scanf(%d,&lenth);