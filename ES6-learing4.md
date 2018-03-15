<a name="top"><h2>扩展运算符</h2></a>
<a href=""><h4>对象扩展运算符</h4></a>
<a href=""><h4>rest运算符</h4></a>
<br>
<a name="01">对象扩展运算符></a>
有时候考虑方法的参数个数不确定，就可以使用扩展运算符来使用。<br>
例：<br>
```javascript
funciton tianer(...arg){  //...arg表示扩展运算符
	console.log(arg[0]);
	console.log(arg[1]);
	console.log(arg[2]);
	console.log(arg[3]);
}
tianer(1,2,3);  //输出情况为，1,2,3,undefined
```
使用已有变量来赋值，产生的问题：<br>
例：<br>
```javascript
let arr1 = ['a','b','c'];
let arr2 = arr1;
console.log(arr2);  //输出['a','b','c']
arr2.push('d');
console.log(arr2);  //输出['a','b','c','d']
console.log(arr1);  //输出['a','b','c','d']，arr1的值也受到影响
```
在上面的例子中，实际上arr1的值受到影响的原因在于，根本都没有开辟新的内存，因此arr2的变化只是起到了一个指代的作用，实际上指向的还是arr1。<br>
如果要解决这样的情况，则需要用到扩展运算符。<br>
例：<br>
```javascript
let arr1 = ['a','b','c'];
let arr2 = arr1[...arg];
console.log(arr2);  //输出['a','b','c']
arr2.push('d');
console.log(arr2);  //输出['a','b','c','d']
console.log(arr1);  //输出['a','b','c']，各是各的，不会影响
```
<a href="#top">返回顶部</a>
<br>
<a name="01"><h4>rest运算符</h4></a>
例：<br>
```javascript
function tianer(a,...arg){
	console.log(arg.length)
}
tianer(1,2,3,4,5,6,7);  //输出为6
```
综上所述，也就是...arg是表示剩余（rest）参数，而且可以通过arg来调用对应的属性（arg.length）。<br>
<br>
使用rest运算符来输出，剩余里面的每个元素：<br>
```javascript
function tianer(a,...arg){
	for(let i=0;i<arg.length;i++){
		console.log(arg[i]);
	}
}
tianer(1,2,3,4,5,6,7);  //输出为2,3,4,5,6,7
```
使用这种方法为let i=0开辟了新的内存空间，所以在ES6中得到了更改。<br>
例：<br>
```javascript
function tianer(a,...arg){
	for(let val of arg){
		console.log(val);
	}
}
tianer(1,2,3,4,5,6,7);  //输出为2,3,4,5,6,7
```
使用这种方法他也可以直接得到arg里面的剩余元素的情况。<br>
<br>
<a href="#top">返回顶部</a>