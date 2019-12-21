```
int itp = 10;
const int citp = 100;

char ctp = 'a';
const char cctp = 'b';
```
#### 指向常量的指针
```
const int* p = tp;
```
#### 指向常量的常量指针
```
const int* const p = ctp;
```
#### 指向char的常量指针
```
typedef char* pstring;
const pstring p = ctp;
```
#### 指向常量char的指针
```
const char* p = cctp;
```
#### 注释
这里可以看到`const pstring p`与`const char* p`并不等价，因为`pstring`是指针类型，可以看成是一种类似于`int`这种基本类型，即`const pstring p`与`const int p`，都是表示常量类型，而后一个是`char`类型，`*`是修饰符。