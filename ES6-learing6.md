## ES6中数字的操作
### 关于二进制和八进制的声明方式
二进制的声明方式有一个特殊的词汇，binary。<br>
例：<br>
```javascript
let binary = 0b0110010110;  //注意这里是0b开头，后面跟二进制数，b可以大写也可以小写
console.log(binary); //二进制的声明
```
八进制的声明方式也是有一个特殊的词汇，octal。<br>
例：<br>
```javascript
let octal = 0o666;  //这里是0o开头，后面跟八进制数，o可以大写也可以小写
console.log(octal); //八进制的声明
```
### 判断是否为一个数字
例：<br>
```javascript
let a = 11/4;
console.log(Number.isFinite(a)); //Number.isFinite()判断是否为一个数字，控制台返回true
console.log(Number.isFinite('tianer')); //控制台返回false
console.log(Number.isFinite(NaN)); //控制台返回false
console.log(Number.isFinite(undefined)); //控制台返回false
```
实际上在ES6中，对于数字对象基本都整合在了Number中。<br>
### 判断是否为NaN(not a number)
例：<br>
```javascript
console.log(Number.isNaN(NaN));  //Number.isNaN()方法判断是否是NaN，这里控制台返回true
console.log(Number.isNaN('tianer'));
```
### 判断是否是整数(ES6新增方法)
例：<br>
```javascript
let a = 233.23;
console.log(Number.isInteger(a)); //判断整数的方法Number.isInteger()
console.log(Number.parseInt(a)); //转换成整型数字的方法
console.log(Number.parseFloat(a));  //转换成浮点型数字的方法
```
### 关于JS的安全数字
例：<br>
```javascript
//JS的安全数字，2的53次方
let a = Math.pow(2,53)-1;  //这边使用了ES5的方法计算出来
console.log(a);    
```
在ES6中直接有指代安全数字的声明方式，例：<br>
```javascript
let a =Number.MAX_SAFE_INTEGER;
console.log(a);    //这是在ES6中表达最大安全整数的方式，有一个定义好的值在Number里面了

let b = Number.MIN_SAFE_INTEGER+1;
console.log(b);    //ES6中的表达最小安全整数，ES6已经有定义好的值了
```
判断是否是安全数字的方法，例：<br>
```javascript
let c = Number.isSafeInteger(b);  //ES6中判断是否是在安全整数之内的方法
console.log(c);  //返回boolean
```