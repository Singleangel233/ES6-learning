## ES6中字符串的控制
#### ES6 中对于字符串的表达
首先举一个ES5中字符串表达的例子<br>
```javascript
var a = '233';  //ES5中字符串的表达
```
这种表达方式是有一定缺点的，比如字符串比较长的时候不能用回车键换行，不然编译就有错误。<br>
<br>
ES6新增对于字符串的表达方式<br>
例：<br>
```javascript
let a = `2333`;  //用``包裹表达
```
在使用这种包裹号表达时候，换行可以识别，并且可以通过${a}来加入之前声明的字符串变量。<br>
例：<br>
```javascript
let a = '阿喵';
let b =`${a}你最乖<br />又可爱`;  //${a}表示之前声明的变量，同时标签也可以识别
document.write(b);  
```
里面还可以增加表达式<br>
例：<br>
```javascript
let a = 1;
let b = 2;
let c = `${a+b}`;   //里面也可以加入表达式
document.write(c);  //在页面上输出c=3
```
#### ES6中对于字符串的判断
首先举一个ES5的字符的判断<br>
例：<br>
```javascript
let a = '天儿';
let b = '带不带天儿飞';
document.write(b.indexOf(a)>0); //ES5的判断字符串是否存在方法，返回boolean
```
b.indexOf(a)方法是ES5中字符串用于查找另一字符串是否存在的方法，如果不加>0那么返回的是a在b中的索引号，加了>0则返回boolean。<br>
ES6直接就有对应的方法，如下所示<br>
例：<br>
```javascript
let a = '天儿';
let b = '带不带天儿飞';
document.write(b.includes(a));  //ES6中判断字符串是否存在，返回boolean
```
includes()方法就可以直接判断，并且直接返回boolean。<br>
同时还有查找开头和结尾位置的，如下所示。<br>
开头，例：<br>
```javascript
let a = '天儿';
let b = '带不带天儿飞';
document.write(b.startsWith(a));  //查找开头有没有，返回boolean
```
结尾，例：<br>
```javascript
let a = '天儿';
let b = '带不带天儿飞';
document.write(b.endsWith(a)); //查找结尾有没有，返回boolean
```
#### 字符串中的复制
ES6有一个方便的方法用于复制想要的字符串。<br>
例：<br>
```javascript
document.write('tianer|'.repeat(4)); //repeat()方法，字符串中的复制
```
repeat()方法就可以复制想要的字符串，里面的参数为数字，是指复制的次数。<br>