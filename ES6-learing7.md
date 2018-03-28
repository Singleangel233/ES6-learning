## ES6的新增的数组操作（1）
### 对Json文件的转换
#### Array.from()方法
使用Array.from()方法对json文件的转换<br>
例：<br>
```javascript
let json = {
	'0' : '233',  
	'1' : '666',
	'2' : '555',   //json文件的格式，这里的key:value值的格式中，key要注意序号从0开始
	length:3      //有个长度
} 
let arr = Array.from(json); //使用这个方法直接将json格式转换成数组
console.log(arr);  //输出为['233','666','555']
```
### ES6中构建数组的方式
#### Array.of()方法
使用Array.of()方法构建数组<br>
例：<br>
```javascript
let arr = Array.of(3,4,5); //Array.of()方法来构建数组
console.log(arr);  //输出为[3,4,5]
```
在原来ES5中，对字符串转换成数组的方式要用到eval()方法。<br>
例，使用eval()方法转化数组：<br>
```javascript
let stt = '[1,2,3]';
let arr = eval(stt); //数组的转换，eval()方法，而ES6直接可以Array.of方法解决
console.log(arr);
```
在ES6中可以直接利用Array.of()来转换。<br>
### ES6中find()实例方法的使用
实例方法：创建实例完毕后才能使用的方法。<br>
例：<br>
```javascript
let arr = [1,2,3,4,5,6];  //创建一个arr实例
var stt = arr.find(function(value,index,arr){   //value为当前的值，index当前的位置，arr当前的数组
	return value>1;  //返回出大于1的值
});
console.log(stt);  //输出2，因为2大于1就停止

let arr = [1,'233',3,4,5,6];
var stt = arr.find(function(value,index,arr){ 
	return value=='233';  //返回等于该值的值
});
console.log(stt);  //输出'233'
```
