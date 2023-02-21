# 1. 注释

```java
// 单行注释
/* 多行注释 */
```

# 2. 输入输出

> document.write：向body输出 ；如内容是标签，会被解析成网页元素

```html
<script>
    /* 1.文档输出 */
    document.write("文档输入")
    document.write("<h1>标题</h1>")
    /* 2.弹窗输出 */
    alert("弹窗输出")
    /* 3.控制台输出 */
    console.log("控制台输出");
    /* 4.输入 */
    prompt("输入")
</script>
```

# 3. 字面量

> 在计算机中描述 事/物
>
> 如：数字字面量，字符串字面量，数组字面量，对象字面量

# 4. 变量

> 1. 存储数据的容器
>
> 2. 本质：在内存中申请的一块存放数据的空间
>
> 3. 命名规则
>
>    - 不能使用关键字
>
>    - <u>只能使用数字，字母，下划线，$；数字不开头</u>
>
>    - **区分大小写**
>
> 4. 规范
>
>    - 有意义
>
>    - 小驼峰
>
> 5. **<u>let 和 var 的区别</u>**：使用 let
>
>    - var声明
>      - 可以先使用在声明（不合理
>      - var声明过的变量可以重复声明（不合理
>      - 



```html
<script>
    /* 声明&&赋值 */
    let number = 100    //变量初始化
    alert(number)
    /* 更新变量 */
    number = 200
    console.log(number);
    /* 多个声明:不提倡 */
    let a = 1 , b = 2
</script>
```



# 5. 数组

> 1. 按顺序保存数据的数据类型: 0 ,1, 2,.....
> 2. 数组操作
>    1. 查：访问； 数组[下标]
>    2. 改: 数组[下标] = 新值
>    3. 增: 尾添加arr.push(新值) ； arr. Unshift(新值)
>    4. 删: arr.pop() ; arr.shift() ; arr.splice(操作的下标 ， 删除的个数)

```html
<script>
    /* 字面量声明 */
    let arr  = [10, 20, 30]
    /* 使用 new Array 声明 */
    let arrs = new Array(1, 2, 3, 4)
    /* 使用 */
    console.log(arr[1],"数组长度：",arr.length);
</script>
```

```javascript
//遍历数组
for(let i = 0 ; i < arr.lenght ; i++){
  doument.write(arr[i])
}
```

---

```javascript
<!-- 新增 
arr.push() 尾添加，一个或多个元素；或返回数组长度
arr.unshift() 头添加，一个或多个元素；或返回数组长度
-->
<script>
    let arr = ["a", "b", "c"]
    arr.push("A")
    document.write(arr+", "+arr.push())
</script>
```

```javascript
<!-- 删除
arr.pop() : 尾删除 ，一个 ； 返回该元素的值
arr.shift() : 头删除 ，一个 ；返回该元素的值
arr.splice(起始位置,删除几个)
-->
<script>
let arr =[2,0,6,1,77,0,52,0,25,7]
document.write(arr.pop())

</script>
```



# 6. 常量

> 1. 使用 const 声明，必须初始化

```javascript
const PI = 3.14
```

# 7. 数据类型

> 1. 基本数据类型
>    1. number 数字型
>    2. string 字符型
>    3. boolean 布尔型
>    4. undefined 未定义型
>    5. null 空类型
> 2. 引用数据类型 ： object

## 1. Number

> 1. 整数，小数
> 2. 运算符
> 3. NaN: 代表计算错误，不是一个数字，与之运算均为NaN，且NaN != NaN

## 2. String

> 1. '' 和 "" 或 \` `包裹
> 2. 引号嵌套时，使用不同引号，或转义
> 3. 模版字符串：<u>拼接字符串和变量</u>，**使用反引号**

```html
<script>
  	/* 模版字符串 */
    let age = 18
    document.write(`我今年${age}岁了`)
</script>
```



## 3. 布尔类型

> true 和 false

## 4. undefined

> 1. 只声明，未定义的
> 2. 使用场景：开发中等待传送过来的变量
>    - 如不知道这个数据是否传送过来，判断其是否为 undefined 

## 5. null

> 1. **undefined表示未赋值**
> 2. **null表示赋值为空**

```javascript
document.write((undefined+1)+","+(null+1))	//NaN,1
```



# 8. 类型检测&&转换

## 1. 类型检测

> **<u>使用表单和 prompt获取的数值，默认为string</u>**


```javascript
document.write(typeof 12 +","+typeof('12'))		//number,string
```



## 2. 隐式转换

> 1. 规则：+ 两边只要有一个字符串，都会将另外一个转换为字符串
> 2. 除了 + 意外的算术运算符，都会把数据转换成数字类型
> 3. 使用+ 转换为number类型

```html
<script>
    /* 隐式转换 */
    document.write(typeof (1+1))        //number
    document.write(typeof ('tom'+1))    //string
    document.write(typeof (2-"tom"))    //number
    document.write(typeof (+"123"))     //number
</script>
```



## 3. 显式转换

> 1. Number(数据)
>    1. 转换成数字类型
>    2. 如字符串含有非数字，转换为NaN
> 2. parselnt(数据)
>    1. 只保留整数
> 3. parseFloat(数据)
>    1. 可以保留小数

```html
<script>
    /* 显式转换 */
    let str = '123'
    console.log(typeof str + " , " + typeof Number(str) + " , " + Number(str))
    console.log(parseInt("12px") + " , " + parseInt("12.1px"))
    console.log(parseFloat("12px") + " , " + parseFloat("12.1px"))
  /*
  string , number , 123
	12 , 12
	12 , 12.1
  */
</script>
```



# 9. 运算符

> 1. 根据运算符个数分为：一元运算符，二元运算符，三元运算符
> 2.  == ： 包含隐式转换
> 3. NaN:不等于任何值，包括NaN

---



| 优先级 | 运算符     | 顺序             |
| ------ | ---------- | ---------------- |
| 1      | 小括号     | （）             |
| 2      | 一元运算符 | ++ -- ！         |
| 3      | 算术运算符 | 先* / % 后 + -   |
| 4      | 关系运算符 | >  >=  <  <=     |
| 5      | 相等运算符 | ==  !=  ===  !== |
| 6      | 逻辑运算符 | 先 && 后 \|\|    |
| 7      | 赋值运算符 | =                |
| 8      | 逗号运算符 | ,                |



```html
<script>
    /*  赋值运算符 = ：
     对变量赋值
     */
    let num = 1
    console.log(num+=1);
    /* 自增运算符 
    +1
    */
    console.log(num++ + " , " + num)
    console.log(++num + " , " + num);
    /* 比较运算符 ：
    == 值相等  : 包含隐式转换
    === 值和类型相等 ；
    !== 不全等
    */
   console.log(2 == "2")    //true
   console.log(2 === "2")   //false
   console.log((NaN === NaN) + " , " + (NaN==NaN)) //false, false

   /* 逻辑运算符
    &&: 一假 全假
    ||：一真 全真
    ! ：反
   */
</script>
```



# 10. 分支&&循环

> 1. 表达式：可被求值，可以写在赋值语句的右边
> 2. 语句： 不一定有值，可被执行
> 3. 三大语句结构： 顺序结构 ，分支结构 ，循环结构

## 1. 分支语句

> 1. if分支语句: **<u>除了 0 ，所有数字都为真</u>**，**<u>除了 空字符串 ，所有字符串都为真</u>**
> 2. 三元运算符
> 3. switch语句: 
>    1. 全等匹配
>    2. break结束，无break会穿透
>    3. 使用 === 避免穿透
>    
> 3. **<u>效率：</u> **分支越少，if..else效率越高
>    
>    



```html
<script>
    /* if */
    if(true){
        console.log("true!");
    }

    if(3 > 5)
    {
        console.log("true1")
    }else{
        console.log("false1")
    }


    let score = 70
    if(score > 80)
    {
        console.log("A");
    }else if(score > 60){
        console.log("B");
    }else{
        console.log("C")
    }
</script>

```

```javascript
console.log(3 > 2 ? 3 : 2 )
```



```html
<script>
    switch (1) {
        case 1:
            alert("1")
        case 2:
            alert("2")
    
        default:
            break;
    }
</script>
```



## 2. 循环语句

> 1. 断点调试：浏览器，检查 ，sorce
> 2. <u>while循环</u>
> 3. break 和 continue
>    1. break退出循环
>    2. continue：跳出当前循环，进入下个循环
> 4. <u>for循环</u>

```html
<script>
    let i = 0
    while (i<6) {
        i++
        console.log(i);
    }
    console.log("i = " + i );
</script>
```



```html
//continue 和 break 
<script>
    let i = 1
    while(i <= 5){
        if(i === 3){
            break
        }
        console.log(" i = " + i)
        i++
    }

    let n = 1
    while (n <= 5) {
     /*  x
     if (n ===3) 
            continue // n = 1 
        }*/
        if (n ===3) {
            n++
            continue
        }
        console.log(" n = " + n)
        n++
        
    }
</script>
```



---

```javascript
//for嵌套
for(外部记录循环次数的变量 ； 循环条件 ；变化值){
  for(内部记录循环次数的变量 ； 循环条件 ； 变化值)
    循环体
}
 
```





# 11. 函数



