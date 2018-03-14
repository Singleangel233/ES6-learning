# ES6学习
## 1、使用ES6和使用babel
babel：是可以将ES6转换为ES5的工具。<br>
首先，我们在某一新建目录下建立两个文件夹,src和dist文件夹。<br>
<br>
其中src用来存储ES6代码的JS文件，然后dist目录用于存储ES6转换后的文件。<br>
然后我们使用npm来对文件进行初始化，在命令行输入指令<br>
```npm init -y```<br>
这个指令用于初始化，-y是让后面的选项选择默认。<br>
初始化完毕后，将会出现一个package.json文件，里面存储着关于项目的内容。<br>
package.json中的内容：<br>
```
{
  "name": "es6test",   //这个是项目名称
  "version": "1.0.0",	
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },				//这个是后面通过运行build后执行的命令
  "keywords": [],
  "author": "",		//这个是作者，可以写名字
  "license": "ISC"	//这个是协议
}
```
<br>
然后使用npm安装babel，在命令行里输入：<br>
```npm install -g babel-cli```<br>
要注意-g是表示全局安装，要注意是安装babel-cli。<br>
安装完毕之后，实际上还是不能直接转换，还需要安装一个工具 babel-preset-es2015 <br>
所以需要在命令行输入<br>
```npm install --save-dev babel-preset-es2015 babel-cli```<br>
安装完成后，在package.json里面有关于这个组件的版本号。<br>
例，在package.json文件中：<br>
```
"babel-preset-es2015": "^6.24.1"
```
<br>
安装完毕后，还需要一步，在当前目录下添加.babelrc文件，并且添加内容。<br>
.babelrc中的内容为：<br>
```
{
	"presets"[
		"es2015"
	],
	"plugins":[]
}
```
输入完成后，然后在命令行里面直接输入：<br>
```
babel src/index.js -o dist/index.js·
```
<br>
这个意思就是表示从src下的index.js经过转换，然后转到dist目录下，并且新生成转换后的index.js<br>
<br>
执行完成后，会在dist目录下生成一个index.js文件。<br>
在dist目录的index.js文件中：<br>
```javascript
"use strict";

var a = 5;
console.log(a);
```
则已经转换完成。<br>
<br>

### 通过不用输入babel src/index.js -o dist/index.jsm直接使用npm run build实行转换。
首先找到package.json文件，然后再script中进行修改，最终修改为 <br>
```
{
  "name": "es6test",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "build": "babel src/index.js -o dist/index.js"  //更改的就是这一行
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "babel-preset-es2015": "^6.24.1"
  }
}
```

然后再命令行输入```npm run build```，就可以直接进行转换了。<br>