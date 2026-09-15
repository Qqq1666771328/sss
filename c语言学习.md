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

# 变量

## 变量与赋值

1. 声明一个整数a int a；

2. 声明一个小数b float b；

3. 初始化变量a为1，b为3.14      int a=1       float b=3.14； 

4. 给a、b赋值     a=2  b=5.6；

5. 变量的声明必须在使用前

6. 可以一次声明多个，之间用逗号隔开

   int a,b,c;      int a=,b=2,c;

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

## 变量的命名规则

1. 只能包含英文字母、数字、下划线
2. 不能以数字开头
3. 不能和关键字重复 （include main int...）

## 格式化输入/输出

1. printf函数

2. printf(“格式串”参数1,参数2,参数3。。。)；

3. 占位符 %d %f  转义序列 \n

4. print a=3; float b=3.14;

   printf（”a=%d\nb=%f”a,b);

5. %n.md %n.mf

   n代表最小栏宽，如果不足会在左侧补空格，超过则正常显示

   前者m代表有效位数，不足补0，超过正常显示

   后者m表示小数点后有效位数，默认为6

6. 占位符与参数不匹配

   参数多/少于占位符

   数据类型不匹配

   ```c
   int a=3;
   float b=3.14;
   int main(){
       printf("a=%d\nb=%.2f",a,b);
       return 0;
   }
   ```

7. scanf函数

8. scanf(“格式串”,参数1,参数2,参数3);

   ```c
   int a=3;
   float b=3.14;
   int main(){
       scanf("a=%d\nb=%f",&a,&b);
       printf("a=%d\nb=%.2f",a,b);
       return 0;
   }
   ```

   

# 指令

## 预处理指令

1. #include 包含

2. #define 宏定义

   #define PI 3.14f

   m=3.14f * r * r 等价 m=PI * r * r
   
   # 随堂练习

```c
#include<stdio.h>
float r1;
float r2;
float v1;
float v2;

int main(void)
{
    printf("请输入半径1=");
    scanf("%f",&r1);

    printf("请输入半径2=");
    scanf("%f",&r2);

    v1=4.0f/3.0f*r1*r1*r1*3.14159;
    v2=4.0f/3.0f*r2*r2*r2*3.14159;

    printf("体积1为%f立方米,体积2为%f立方米。",v1,v2);
    
    return 0;
}
```

