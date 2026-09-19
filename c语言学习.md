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

1. 声明一个整数a int a；声明一个小数b float b；

2. 初始化变量a为1，b为3.14      int a=1       float b=3.14； 

3. 给a、b赋值     a=2  b=5.6；

4. 变量的声明必须在使用前

5. 可以一次声明多个，之间用逗号隔开

   int a,b,c;      int a=,b=2,c;

6. 运算符的优先级和结合性

   int a,b,c;

   a+b * c=a+(b * c)

7. 赋值运算符

   把=右边的值赋给左边

   i=j   i=-j   i=-j+4-k   i=j=k=5

8. 复合赋值

   i=i+2   i+=2 i=i-2 i-=2

   -= /= *=  %=

   a+=b a=a+b

9. 自增运算符和自减运算符

   i=i+1  i++   ++i

   i=i-1   i--   --i

   int i=2,j=3;

   i=j++;   i=3 j=4

   i=++j;   i=4 j=4

10. 





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

# 语句

## 选择语句

1. if语句

   if(表达式)

     语句

     else

     语句

   例如：

   if(饿了)

     吃饭

     else

     不吃饭

2. 设计一个C程序，提示用户输入一个数，并判断这个数是奇数还是偶数，如果是奇数，就乘3再显示，如果是偶数，就乘5再显示。

   ```c
   #include<stdio.h>
   int a;
   int main(void){
       printf("请输入一个数,");
       scanf("%d",&a);
       if (a%2==0)
       {
           a=a*5;
           printf("这是一个偶数%d",a);  
       }
       else
       {
           a=a*3;
           printf("这是一奇数%d",a);  
       }
   
       return 0;
   }
   ```

   

3. 级联式if语句

4. 悬空else问题

5. 条件表达式

   if(a)b;else c;

   表达式1？ 表达式2： 表达式3

   如果1为真，就选择2，否则选择3

   int a,b=2,c=3

   a=b>c?b:c;

6. 布尔值

   int float __Bool

   int a;

   float b;

   __Boll c;

7. switch语句

   找到匹配的常量，开始顺序往后执行

     switch()

   {

     case 常量表达式 ： 语句

     case 常量表达式 ： 语句

     。。。。。。

     case常量表达式 ： 语句

     default：语句

   }

   break；

8. while语句的基本结构
   while(表达式)语句

9. 编写一个简单的C程序,在屏幕上显示5到1

   ```c
   #include <stdio.h>
   int i=5;
   int main()
   {
       while(i)
       {
           printf("%d\n",i);
           i=i-1;
       }
   return 0;
   }
   ```

   

10. i--和--i的区别

11. 无限循环while(1)

12. do语句

    do{语句} while(表达式)

    设计一个C程序，计算用户输入的整数的位数

    ```c
    #include <stdio.h>
    int num;
    int i;
    int main()
    {
        printf("请输入一个整数:");
        scanf("%d",&num);
        do
        {
            num/=10;
            i++;
    
        }
        while(num>0);
    printf("有%d位",i);
    return 0;
    }
    ```

    

13. for语句

    for(表达式1;表达式2;表达式3)语句

    编写一个简单的C程序,在屏幕上显示5到1

    ```c
    #include<stdio.h>
    int i;
    int main()
    {
        for(i=5;i>0;i--)
        {
             printf("%d\n",i);
        }
        return 0;
    }
    ```

    

14. for语句中的省略表达

15. C99中的for语句表达式1

16. 逗号运算符

17. 退出循环

18. break语句

    设计一个C代码，判断用户输入的数是不是素数

    ```c
    #include <stdio.h>
    int num,i;
    int main()
    {
        printf("请输入一个正整数：");
        scanf("%d",&num);
        for(i=2;i<num;i++)
        {
            if(num%i==0)            
                break;      
        }
        if(i<num)
        printf("合数");
    
        else
        printf("质数");
    
    return 0;
    }
    ```

    

19. continuei语句

20. goto语句

21. goto语句
    标识符:   语句
    goto标识符;

22. 空语句

23. 

24. 

25. 

    
