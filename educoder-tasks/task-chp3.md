# 实训作业参考答案 —— 第三章 分支程序设计



## 3.1 任务名称

编写成绩转换程序

### 任务描述


本关任务：编写一个成绩转换程序，对于输入的成绩 n，转换规则如下：A档为 90-100，B 档是 80-89，C 档是 70-79，D 档是 60-69，E 档是 0-59。

注意：编程过程中，可以采用if 语句，嵌套 if 语句或 switch 语句实现。请分别尝试各种语句的用法。

### 测试说明

输入描述：一个正整数 n(0<=n<=100)。
输出描述：对应的等级，一个字符 x ∈{A,B,C,D,E}。

样例输入：100
样例输出：A
样例输入：85
样例输出：B
样例输入：70
样例输出：C
样例输入：66
样例输出：D
样例输入：30
样例输出：E

### 代码样例

```cpp
#include<iostream>
using namespace std;

int main() {

// 请在下方添加代码
/********** Begin *********/
    int a;
    cin>>a;
    if (a<=100 and a>=90){
        cout<<"A";
    }
    else if (a<=89 and a>=80){
        cout<<"B";
    }
    else if (a<=79 and a>=70){
        cout<<"C";
    }
    else if (a<=69 and a>=60){
        cout<<"D";
    }
    else{
        cout<<"E";
    }


/********** End **********/

	return 0;
}
```





## 3.2 任务名称

判断字母是元音字母还是辅音字母

### 任务描述


本关任务：编写一个程序，对于一个输入的字母 char，判断该字母是元音字母还是辅音字母。对于元音字母，输出一个字符串"vowel"，对于辅音字母，输出一个字符串"consonant"。要求用 if 语句或 switch 语句实现。

### 测试说明

输入描述：一个小写字母c(‘a’<=c<=’z’)。 
输出描述：输出一个代表元音字母或者辅音字母的字符串。

样例输入1：c
样例输出1：consonant

样例输入2：a
样例输出2：vowel

### 代码样例

```cpp
#include<iostream>
using namespace std;

int main() {

// 请在下方添加代码
/********** Begin *********/
   char vowel[] = "aeiou";
   char a;
   cin>>a;
   for (int i=0;i<=4;i++){
   		if (a==vowel[i]){
   				cout<<"vowel";
   				return 0;
		   }
   }
   cout<<"consonant";


/********** End **********/

	return 0;
}
```





## 3.3 任务名称

电话数据加密

### 任务描述


本关任务：一个公司想通过电话传输数据，但是担心电话可能被窃听。这个公司的所有的数据都采用 4 位整数的形式进行传输。对于一个 4 位整数，他们按如下方法进行加密：首先，将每位数字替换成它与 7 相加之和再用 10 取模的结果。然后，对替换后的数，其第 1 位和第 3 位相交换，第 2 位和第 4 位相交换。我们要求编写这样一个程序：对于输入的两个 4 位整数 n,m，输出分别对 n 加密和对 m 解密的结果。（对于加密或者解密后出现小于 1000 的情况，不输出第一位的 0）。


### 测试说明

输入描述：两个 4 位整数 n,m(1000<=n,m<=9999)，使用一个空格分隔。 
输出描述：对 n 加密和 对m 解密之后的结果，使用一个空格分隔。

样例输入1：1234 5678
样例输出1：189 189

样例输入2：8071 4287
样例输出2：4857 1075

### 代码样例

```cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main(void) {
/******** Begin ********/
    int n, m;
    cin >> n >> m;
    cout << (n/10%10+7)%10 * 1000
        + (n%10+7)%10 * 100
        + (n/1000+7)%10 * 10
        + (n/100%10+7)%10
        << " "
        << (m/10%10+3)%10 * 1000
        + (m%10+3)%10 * 100
        + (m/1000+3)%10 * 10
        + (m/100%10+3)%10;
/********  End  ********/
    return 0;
}
```





## 3.4 任务名称

排序

### 任务描述


本关任务：输入三个整数，a，b，c（均在 int 范围内），要求将这三个数从小到大排序输出。


### 测试说明

输入描述：三个整数 a，b，c，使用一个空格分隔。 
输出描述：三个从小到大排序后的整数，以空格分隔

样例输入1：73 114 5
样例输出1：5 73 114

样例输入2：100 100 50
样例输出2：50 100 100

### 代码样例

```cpp
// 请在下方添加代码
/********** Begin *********/
#include<iostream>

using namespace std;
int main() 
{
int a,b,c;
cin>>a>>b>>c;
if (a>=b and a>=c){
    if (b>=c){
        cout<<c<<" "<<b<<" "<<a;
    }else{
        cout<<b<<" "<<c<<" "<<a;
    }
}
else if (b>=a and b>=c){
    if (a>=c){
        cout<<c<<" "<<a<<" "<<b;
    }else{
        cout<<a<<" "<<c<<" "<<b;
    }
}
else if (c>=b and c>=a){
    if (b>=a){
        cout<<a<<" "<<b<<" "<<c;
    }else{
        cout<<b<<" "<<a<<" "<<c;
    }
}
else {
    cout<<a<<" "<<b<<" "<<c;
}
  return 0;
}
/********** End **********/
```



## 3.5 任务名称

根据居民月用水量计算应收水费

### 任务描述


本关任务：我国是世界上严重缺水的国家之一。为了增强居民节水意识，某市自来水公司对居民用水采用以户为单位分段计费办法收费。即一月用水 10 吨以内（包括 10 吨）的用户，每吨收水费 1.5 元；一月用水超过 10 吨的用户，10 吨水仍按每吨 1.5 元收费，超过 10 吨的部分，按每吨 2 元收费。编写一个程序，输入某用户居民月用水量（单位：吨），输出应收水费（单位：元）。


### 测试说明

输入描述：一个大于等于 0 的浮点数 
输出描述：输出计算得到的应收水费

样例输入1：5.2
样例输出1：7.8

样例输入2：18.5
样例输出2：32

### 代码样例

```cpp
// 请在下方添加代码
/********** Begin *********/
#include<iostream>
#include<iomanip>
using namespace std;
int main() 
{
double s;
cin>>s;
if (s<=10){
    cout<<s*1.5;
}
else{
    cout<<(s-10)*2+15;
}
  return 0;
}
/********** End **********/

```





## 3.6 任务名称

字符转换

### 任务描述


本关任务：从键盘输入一个字符，如果是大写字母，就转换为小写；如果是小写字母，就转换成大写，如果是其他字符就保持原样输出。

### 测试说明

输入描述：用键盘输入一个任意字符 
输出描述：输出转换后的字符

样例输入1：A
样例输出1：a

样例输入2：b
样例输出2：B

样例输入3：0
样例输出3：0

### 代码样例

```cpp
// 请在下方添加代码
/********** Begin *********/
#include<iostream>

using namespace std;
int main() 
{
char c;
cin>>c;
if (c<=90 and c>=65){
    cout<<char(c+32);
}else if (c>=97 and c<=122){
    cout<<char(c-32);
}else{
    cout<<c;
}
  return 0;
}
/********** End **********/
```





## 3.7 任务名称

停车收费系统

### 任务描述


本关任务：设计一停车场的收费系统。停车场有 3 类汽车，分别用 3 个字母表示。C 代表轿车，B 代表客车，T 代表卡车。收费标准如下：

| 车辆类型 | 收费标准                                      |
| -------- | --------------------------------------------- |
| 轿车(c)  | 三小时内，每小时5元。三小时后，每小时10元。   |
| 客车(b)  | 两小时内，每小时10 元。两小时后，每小时15元。 |
| 卡车(t)  | 一小时内，每小时10元，一小时后，每小时15元。  |


### 测试说明

输入描述：汽车类型(c/b/t)、入库时间（自然数）和出库时间（自然数）
输出描述：应交的停车费

样例输入1：b 7 9
样例输出1：20

样例输入2：c 6 11
样例输出2：35

### 代码样例

```cpp
// 请在下方添加代码
/********** Begin *********/
#include<iostream>

using namespace std;
int main() 
{

char t;
int a,b;
cin>>t>>a>>b;

int s = b-a;

if (t=='c'){
    if (s<=3){
        cout<<s*5;
    }else{
        cout<<(s-3)*10+15;
    }
}else if (t == 'b'){
    if (s<=2){
        cout<<s*10;
    }else{
        cout<<(s-2)*15+20;
    }
}else if (t == 't'){
    if (s<=1){
        cout<<s*10;
    }else{
        cout<<(s-1)*15+10;
    }
}
  return 0;
}
/********** End **********/

```



## 3.8 任务名称

判断回文数

### 任务描述


本关任务：所谓“回文”是一种特殊的或者文字短语。它们无论是顺读还是倒读，结果都是一样。例如，以下的几个 5 位整数都是回文数：12321、77777、89998 和 44774。编写一个程序，读入一个 5 位整数后，判断它是否是回文数。

### 测试说明

输入描述：一个 5 位整数
输出描述：“Yes”或“No”

样例输入1：12321
样例输出1：Yes
样例输入2：12323
样例输出2：No

### 代码样例

```cpp
#include <iostream>
using namespace std;

int main(void) {
/******** Begin ********/
    int n; cin >> n;
    if (n/10000 == n%10 && n/1000%10 == n/10%10)
        cout << "Yes" << endl;
    else cout << "No" << endl;

/********  End  ********/
    return 0;
}
```


