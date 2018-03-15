## 3、解构赋值
解构赋值：是可以用数组或者对象的方式来提取里面的变量，然后对应赋值。<br>
使用解构赋值可以减少代码量，并且同时可以让代码更加清晰。<br>

### 解构赋值的三种形态：<br>
<a href="#01"><p>数组的结构赋值</p></a>

#### 第一种，数组的解构赋值
例如这样声明和为变量赋值：<br>
```javascript
let [a,b,c]=[1,2,3];
console.log(a);  //输出1
console.log(b);	 //输出2
console.log(c);	 //输出3
```
或者可以像类似于这种：<br>
```javascript
let [a,[b,c],d]=[1,[2,3],4];
console.log(a);  //输出1
console.log(b);	 //输出2
console.log(c);	 //输出3
console.log(d);  //输出4
```
只要保证声明的变量跟赋值的写法相同，那么就可以实现解构赋值。<br>


也可以为在解构赋值中的变量赋一个默认值，例：<br>
```javascript
let [foo=true]=[];
console.log(foo);  //输出true
```


所以通过这个方法，这样写也是成立的：<br>
```javascript
let [a,b='tianer']=['singleangel'];
console.log(a);  //输出singleangel
console.log(b);	 //输出angel
```
<a name="01"><p>在上个例子中，让a自动赋值到'singleangel'，让b默认值为'tianer'，但是如果这样写</p></a>：<br>
```javascript
let [a='singleangel',b]=['tianer'];
console.log(a);  //输出tianer
console.log(b);	 //输出undefined
```


关于undefined和null