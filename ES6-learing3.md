<a name="top"><h2>3、解构赋值</h2></a>
解构赋值：是可以用数组或者对象的方式来提取里面的变量，然后对应赋值。<br>
使用解构赋值可以减少代码量，并且同时可以让代码更加清晰。<br>

<h3>解构赋值的三种形态：</h3>
<a href="#01"><p>数组的解构赋值</p></a>
<a href="#02"><p>对象的解构赋值</p></a>
<a href="#03"><p>字符串的解构赋值</p></a>

<a name="01"><h4>数组的解构赋值</h4></a>
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
在上个例子中，让a自动赋值到'singleangel'，让b默认值为'tianer'，但是如果这样写<br>
```javascript
let [a='singleangel',b]=['tianer'];
console.log(a);  //输出tianer
console.log(b);	 //输出undefined
```


关于undefined和null在解构赋值中的意义：<br>
例如undefined：<br>
```javascript
let [a,b='tianer'] = ['singleangel','undefined'];
console.log(a+b);  //输出的是singleangeltianer
```
也就是说，如果有默认值，那么就会覆盖掉undefined。<br>
例如null：<br>
```javascript
let [a,b='tianer'] = ['singleangel','null'];
console.log(a+b);  //输出的是singleangelnull
```
也就是说，如果赋值为null，则会替换掉默认的tianer。<br>
<br>
<a href="#top">返回顶部</a>
<br>
<a name="02"><h4>对象的解构赋值</h4></a>
例：<br>
```javascript
let {a,b} = {a:'tianer',b:'singleangel'};
console.log(a+b); //输出tianersingleangel
```
这是使用了对象的解构赋值方式，跟数组不一样的地方就在于，没有数组的顺序。<br>
要注意，使用对象解构赋值，要保证每一个变量都要有值，不然编译完后会出错。<br>
<br>
使用对象赋值的一个坑：先用一行声明，再用一行赋值。<br>
例：<br>
```javascript
let foo;
{foo}={foo:'tianer'};
console.log(foo);  //npm编译不出来，会报错
```
正确写法如下：<br>
```javascript
let foo;
({foo}={foo:'tianer'});  //要在第二行使用一个圆括号才能解决
console.log(foo);  
```
<a href="#top">返回顶部</a>
<br>
<a name="03"><h4>字符串的解构赋值</h4></a>
例如：<br>
```javascript
const [a,b,c,d,e,f]='tianer';
console.log(a);  //输出t
console.log(b);  //输出i
console.log(c);  //输出a
console.log(d);  //输出n
console.log(e);  //输出e
console.log(f);  //输出r
```
这个可以用来进行权限的判断。<br>
<br>
<a href="#top">返回顶部</a>