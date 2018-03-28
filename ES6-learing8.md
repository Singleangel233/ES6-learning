## ES6新增对数组的控制（2）
### 改变数组中的某个元素
使用fill()方法，可以改变数组中的某个元素<br>
例：<br>
```javascript
let arr = ['1','angel','233'];
arr.fill('tianer',1,2); 
//fill函数有三个参数，第一个是替换的内容，第二个是替换的位置（从0开始计算），第三个也是要替换的位置（这个是从1开始计算）
console.log(arr);  //输出为['1','tianer','233']
```
### ES6新增的对数组的循环
在ES6中，新增了for of循环，这种循环的写法更加简便<br>
例：<br>
```javascript
let arr = ['1','angel','233'];
for(let item of arr){  
//这里使用的是新增的for of循环，arr表示循环的数组，item表示数组中的元素
	console.log(item); //输出为1 angel 233
}
```
### 关于对for of循环的拓展
#### 直接输出索引号
我们可以使用keys()实例方法来获取索引号，然后输出<br>
例：<br>
```javascript
let arr = ['1','angel','233'];
for(let item of arr.keys()){  
//arr.keys()这个实例方法表示获取里面的索引
	console.log(item);  //输出0 1 2
}
```
#### 输出索引号，并且输出索引的值（第一种）
我们可以使用entries()实例方法来输出索引号以及索引值<br>
例：<br>
```javascript
let arr = ['1','angel','233'];
for(let item of arr.entries()){  
//arr.entries()这个实例方法表示获取有索引号并且有值的
	console.log(item); //输出:0 "1",1 "angel",2 "233"
}
```
#### 输出索引号和值（第二种）
将原来的item进行修改，可以对应得到索引号和值<br>
例：<br>
```javascript
let arr = ['1','angel','233'];
for(let [index,val] of arr.entries()){  
//将item改成了index,val，第一个表示索引，第二个表示值，用中括号进行包裹
	console.log(index+':'+val); //直接输出:0 1,1 angel,2 233
}
```
### 对于entries()方法的细节
entries()方法也是一个实例方法，并且能让数组变成一个Iterator数组。<br>
例：<br>
```javascript
let arr = ['1','angel','233'];
let list = arr.entries();  //这个list实际上是一个Iterator对象
console.log(list); //这个Iterator对象比较特别，以后谈到
```
#### 手动循环数组，使用next（）方法
使用next()方法，可以手动循环数组。<br>
例：<br>
```javascript
let arr = ['1','angel','233'];
let list = arr.entries();  //这个list实际上是一个Iterator对象
console.log(list.next().value); //使用list的next()方法，然后配合value值，可以进行手动循环
console.log(list.next().value); //next()方法可以自己记录循环到的位置
console.log(list.next().value); //每次输出都是下一个值
//最后输出为[0,"1"] [1,"angel"] [2,"233"]
```