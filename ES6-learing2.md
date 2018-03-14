## 2、ES6中的三种声明方式
#### 第一种，全局声明方式（var）
例如我们最常见的：<br>
```javascript
var a = 5;
console.log(a);
```
这个就是用来声明一个全局变量的，但是也有缺点。<br>
缺点就在于，如果下面再次声明一次，那么就会替代原有的变量。<br>
例如：<br>
```javascript
var a = 5;
console.log(a);
{
	var a = 4;	
}
console.log(a);
```
其中{}表示区域块，总的来说a的值在后面已经发生了变化，会污染a原来的值。<br>


#### 第二种，局部声明方式（let）
使用这种方式，可以局部声明变量<br>
例如：<br>
```javascript
var a = 5;
console.log(a);
{
	let a = 4;	
}
console.log(a);
```
这时候控制台a的值还是为5，没有改动。<br>

**要注意**，如果是这样：<br>
```javascript
var a = 5;
console.log(a);
{
	let a = 4;	
	console.log(a); //将输出a这条语句放进区域块中
}
```
那么控制台输出的a值还是为4。<br>
<br>
**let的常用之处：**<br>
一般在ES5中，使用for循环，都是以全局声明变量的方式来声明i。<br>
例如：<br>
```javascipt
for(i=1;i<5;i++){  //这里是var i=1
	console(i);
}
console("外部输出"+i);  //i值为5
```
所以i的值就不能随意更改了，不然会报错，但是使用let就可以继续在外部使用i，并且值不会受到影响。<br>
例如：<br>
```javascript
for(let i=1;i<5;i++){
	console(i);
}
console("外部输出"+i); //会报错，报错说i没有定义
```


#### 第三种，常量声明方式（const）
使用const来声明常量，常量是不可以改变值的。<br>
例如：<br>
```javascript
const a = "singleangel";
const a = 3;
```
那么这个会在命令行里面转化的时候就报错，导致转化失败，因为常量是不可以更改值的。<br>