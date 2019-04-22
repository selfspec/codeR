# JavaScript

# 1 前言

​    

JavaScript 一直有着广泛的应用，特别是在浏览器端的行为管理。本文档的目标是使 JavaScript 代码风格保持一致，容易被理解和被维护。

# 2 代码风格

	### 2.1结构

### 2.1.1 缩进



##### [强制] 使用 `4` 个空格做为一个缩进层级，不允许使用 `2` 个空格 或 `tab` 字符。

##### [强制] `switch` 下的 `case` 和 `default` 必须增加一个缩进层级。

 ```js
// good
switch (variable) {

    case '1':
        // do...
        break;

    case '2':
        // do...
        break;

    default:
        // do...

}

// bad
switch (variable) {

case '1':
    // do...
    break;

case '2':
    // do...
    break;

default:
    // do...

}
 ```

### 2.1.2 空格	

##### 1.[强制] 二元运算符两侧必须有一个空格，一元运算符与操作对象之间不允许有空格。= 号两侧必须要有空格

```js
var a = !arr.length;
a++;
a = b + c;
```



##### 2.[强制] 用作代码块起始的左花括号 `{` 前必须有一个空格。

```js
// good
if (condition) {
}

while (condition) {
}

function funcName() {
}

// bad
if (condition){
}

while (condition){
}

function funcName(){
}
```

3.[强制] `if / else / for / while / function / switch / do / try / catch / finally` 关键字后，必须有一个空格。

```js
// good
if (condition) {
}

while (condition) {
}

(function () {
})();

// bad
if(condition) {
}

while(condition) {
}

(function() {
})();
```

4.[强制] 在对象创建时，属性中的 `:` 之后必须有空格，`:` 之前不允许有空格。

```js
// good
var obj = {
    a: 1,
    b: 2,
    c: 3
};

// bad
var obj = {
    a : 1,
    b:2,
    c :3
};
```



5.[强制] 函数声明、具名函数表达式、函数调用中，函数名和 `(` 之间不允许有空格。

```js
// good
function funcName() {
}

var funcName = function funcName() {
};

funcName();

// bad
function funcName () {
}

var funcName = function funcName () {
};

funcName ();
```

6.[强制] `,` 和 `;` 前不允许有空格。如果不位于行尾，`,` 和 `;` 后必须跟一个空格。

```js
// good
callFunc(a, b);

// bad
callFunc(a , b) ;
```

7.[强制] 在函数调用、函数声明、括号表达式、属性访问、`if / for / while / switch / catch` 等语句中，`()` 和 `[]` 内紧贴括号部分不允许有空格。

```js
// good

callFunc(param1, param2, param3);

save(this.list[this.indexes[i]]);

needIncream && (variable += increament);

if (num > list.length) {
}

while (len--) {
}


// bad

callFunc( param1, param2, param3 );

save( this.list[ this.indexes[ i ] ] );

needIncreament && ( variable += increament );

if ( num > list.length ) {
}

while ( len-- ) {
}
```

8.[强制] 单行声明的数组与对象，如果包含元素，`{}` 和 `[]` 内紧贴括号部分不允许包含空格。

声明包含元素的数组与对象，只有当内部元素的形式较为简单时，才允许写在一行。元素复杂的情况，还是应该换行书写

```js
// good
var arr1 = [];
var arr2 = [1, 2, 3];
var obj1 = {};
var obj2 = {name: 'obj'};
var obj3 = {
    name: 'obj',
    age: 20,
    sex: 1
};

// bad
var arr1 = [ ];
var arr2 = [ 1, 2, 3 ];
var obj1 = { };
var obj2 = { name: 'obj' };
var obj3 = {name: 'obj', age: 20, sex: 1};
```

### 2.1.3 换行与命名

##### 1.[强制] 不得省略语句结束的分号。

2.[强制] 在 `if / else / for / do / while` 语句中，即使只有一行，也不得省略块 `{...}`。

```js
// good
if (condition) {
    callFunc();
}

// bad
if (condition) callFunc();
if (condition)
    callFunc();
```

3.[强制] 函数定义结束不允许添加分号。

```js
// good
function funcName() {
}

// bad
function funcName() {
};

// 如果是函数表达式，分号是不允许省略的。
var funcName = function () {
};
```

4.[强制] `变量` 使用 `Camel命名法`。

5.[强制] `类` 使用 `Pascal命名法`。(大驼峰)

### 2.1.4 注释

1.[强制] 必须独占一行。`//` 后跟一个空格，缩进与下一行被注释说明的代码一致。

2.有多行注释内容时，使用多个单行注释

3.函数公共方法的注释的书写规范

```js
/**
 * 函数描述
 *
 * @param {string} p1 参数1的说明
 * @param {string} p2 参数2的说明，比较长
 *     那就换行了.
 * @param {number=} p3 参数3的说明（可选）
 * @return {Object} 返回值描述
 */
function foo(p1, p2, p3) {
    var p3 = p3 || 10;
    return {
        p1: p1,
        p2: p2,
        p3: p3
    };
}
```

## 2.2 变量

### 2.2.1 变量声明

1.[强制] 变量、函数在使用前必须先定义。（不通过 var 定义变量将导致变量污染全局环境。）

2.[强制] 变量必须 `即用即声明`，不得在函数或其它形式的代码块起始位置统一声明所有变量。

```js
// good
var name = 'MyName';

// bad
name = 'MyName';
```



### 2.2.2 对象的声明

##### 1.[强制] 使用对象字面量 `{}` 创建新 `Object`。

```js
// good
var obj = {};

// bad
var obj = new Object();
```

2.[强制] 不允许修改和扩展任何原生对象和宿主对象的原型。

```js
// 以下行为绝对禁止
String.prototype.trim = function () {
};
```

3.[建议] `for in` 遍历对象时, 使用 `hasOwnProperty` 过滤掉原型中的属性。

```js
var newInfo = {};
for (var key in info) {
    if (info.hasOwnProperty(key)) {
        newInfo[key] = info[key];
    }
}
```

4.[强制] 避免使用直接 `eval` 函数。(直接 `eval`，指的是以函数方式调用 `eval` 的调用方法。直接 `eval` 调用执行代码的作用域为本地作用域，应当避免。)



