[toc]



---

---

<h1>HTML</h1>

# 1. 语法规范

> 1. 注释
>
> 2. 标签构成
>
> 3. 标签间的关系
>
> 4. ###### Cmd + d 选中

# 2. 标题和段落

> 1. \<p></p>
> 2. 水平分割线 \<hr>
> 3. 换行\<br>

```html
<body>
    <h1>h1</h1>
    <h2>h2</h2>
    <h3>h3</h3>
    <h4>h4</h4>
    <h5>h5</h5>
    <h6>h6</h6>
    <br>
    <p>一个段落，独占一行，段落间有间隙</p>
    <p>一个段落，独占一行，段落间有间隙</p>
</body>
```

# 3. 文本格式化标签

| 标签       | 说明   |
| ---------- | ------ |
| b , strong | 加粗   |
| u， ins    | 下划线 |
| i， em     | 倾斜   |
| s， delete | 删除线 |

```html
<del>删除线</del>
```



# 4. 媒体标签

## 1. 图片标签

> 1. Src 路径
>    1. 相对路径： 从当前文件开始找目标文件的相对位置
>    2. 绝对路径：依据盘符
> 2. alt 替换文本：图加载失败时使用
> 3. title :鼠标悬停时显示的文字
> 4. Width && height :如 只设置一个值，自动等比缩放

```html
<img src="" alt="">
```

## 2. 音/视频标签

```html
<audio src="" controls></audio>
```

| 属性名   | 功能                                                         |
| -------- | ------------------------------------------------------------ |
| src      | 路径                                                         |
| controls | 显示播放的控件                                               |
| autoplay | 自动播放（部分浏览器不支持）； 对于视频，chrome 中+muted实现静音播放 |
| loop     | 循环播放                                                     |

## 3. 链接标签

```html
<a href="./跳转目标">一个链接</a>
```

# 5. 列表标签

## 1. 无序列表

> 1. ul: 表示无序列表的整体，<u>**用于包裹li，只能包含li标签**</u>
> 2. li： 行，可以包含任意内容

## 2. 有序列表

> 1. ol：表示有序列表的整体，<u>**用于包裹li，只能包含li标签**</u>
> 2. Li: 行，可以包含任意内容

## 3. 自定义列表

> 1. dl: 表示自定义列表的整体，**<u>只能包裹dt/dd</u>**
> 2. dt：自定义列表的主题，可以包含任意内容
> 3. dd：可以包含任意内容；默认显示缩进效果

```html
	<ul>
        <li>aaa</li>
        <li>bbb</li>
        <li>ccc</li>
    </ul>

    <ol>
        <li>AAA</li>
        <li>BBB</li>
        <li>CCC</li>
    </ol>

    <dl>
        <dt>自定义列表</dt>
        <dd>111</dd>
        <dd>222</dd>
        <dd>333</dd>
    </dl>
```

# 6. 表格

> 1. 嵌套： table > tr > td
> 2. 属性: 通常使用css设置
>
>    1. Border: 数字 边框宽度
>
>    2. width： 数字 表格高度
>
>    3. height：数字 表格高度
> 3. 表格标题和单元格标签： caption th
>    1. caption：表示表格的大标题，默认顶部居中
>    2. th： 表示小标题，常用于表格第一行，默认加粗居中,替换 td
> 4. 表格结构标签: 用于包裹 tr ，**<u>可省略</u>**
>    1. thead ：表格头部
>    2. tbody：表格主体
>    3. tfoo： 表格底部
> 5. 合并单元格：
>    1. 跨行合并：rowspan 合并个数
>    2. 跨列合并：colspan 合并个数
>    3. ⚠️
>       1. 只能合并同一结构，不能跨结构标签thead，tfoot，tbody
>       2. 合并原则
>          1. 上下合并：只保留<u>最上</u>的
>          2. 左右合并：只保留<u>最左</u>的

| 名称  | 说明                     |
| ----- | ------------------------ |
| table | 表格整体，用于包裹多个tr |
| tr    | 表格 行 ， 用于包裹 td   |
| td    | 表格 列 ， 用于包裹内容  |
|       |                          |

---

```html
<table border="2" width="500" height="500" >
        <caption>
            成绩单
        </caption>
        <tr>
            <th>name</th>
            <th>score</th>
        </tr>
        <tr>
            <td>tom</td>
            <td>100</td>
        </tr>
        <tr>
            <td>merry</td>
            <td>99</td>
        </tr>
        <tr>
            <td>bob</td>
            <td>88</td>
        </tr>
    </table>
<br><br>

   <table border="2" width="500" height="500" >
    <thead>
        <tr>
            <td>name</td>
            <td>score</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>tom</td>
            <td>100</td>
        </tr>
        <tr>
            <td>merry</td>
            <td>100</td>
        </tr>
        <tr>
            <td>bob</td>
            <td>100</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
        <th>..</th>
        <th>..</th>
        </tr>
        
    </tfoot>
   </table>
    <br><br>
   
<table border="1" width="1000"height="400">
        <caption><h4>优秀学成信息表格</h1></caption>
        
            <tr>
                <th>年级</th>
                <th>姓名</th>
                <th>学号</th>
                <th>班级</th>
            </tr>
            <tr>
                <td rowspan="3">高三</td>
                <td>张三</td>
                <td>110</td>
                <td>三年二班</td>
            </tr>
            <tr>
                
                <td>李四</td>
                <td>120</td>
                <td>三年三班</td>
            </tr>
            <tr>
                
                <td>小明</td>
                <td>130</td>
                <td>三年四班</td>
            </tr>
            <tr>
                <td>评语</td>
                <td colspan="3">你们很优秀</td>
                
  </tr>
    </table>
```

# 7. 表单标签

## 1. input

> 1. 通过type属性，展示不同效果
> 2. placeholder：占位符，input框显示内容
> 3. radio：
>    1. name：分组，只能同时选中一组
>    2. checked：默认选中
> 4. file：多文件选中 multiple
> 5. 表单域：form，连接 按钮和文本框
> 6. 按钮： value 添加显示文字

| type属性 | 说明     |
| -------- | -------- |
| text     | 文本框   |
| password | 密码框   |
| radio    | 单选框   |
| checkbox | 多选框   |
| file     | 文件选择 |
| submit   | 提交按钮 |
| reset    | 重置按钮 |
| button   | 普通按钮 |

```html
<form action="">
        文本框<input type="text" placeholder="placeholder提示文本"><br><br>
        密码框<input type="password"><br><br>
        单选框1<input type="radio" name="1">单选框2<input type="radio" name="1" checked><br><br>
        多选框1<input type="checkbox">多选框2<input type="checkbox">多选框3<input type="checkbox">多选框4<input type="checkbox"><br><br>
        文件选择<input type="file" multiple><br><br>
        提交按钮<input type="submit" value="提提交"><br><br>
        重置按钮<input type="reset" value="重重值"><br><br>
        普通按钮<input type="button"value="普普通通按钮"><br><br>
    </form>
```



## 2. button

> 1. button：双标签，可包裹文字图片等
>
>    1. submit：提交
>
>    2. reset：重置
>    3. button：普通按钮

## 3. 下拉表单

> 1. select：下拉菜单的整体， <u>selected：下拉菜单的默认选中</u>
> 2. option：下拉菜单的每一项

```html
<select name="" id="">
        <option value="">
            第一项
        </option>
        <option value="" selected>
            第二项
        </option>
        <option value="">
            第三项
        </option>
    </select>
```

## 4. 文本域标签

> 1. 标签名：textarea
> 2. 属性
>    1. cols：规定文本域内可见宽度
>    2. rows：规定文本域内可见行数
> 3. ⚠️
>    1. 右下角可拖拽改变大小
>    2. 常使用css控制样式

```html
    <textarea name="" id="" cols="30" rows="10">
        文本域标签文本域标签文本域标签文本域标签文本域标签文本域标签文本域标签文本域标签
        文本域标签文本域标签文本域标签文本域标签文本域标签文本域标签文本域标签文本域标签文本域标签
        文本域标签文本域标签文本域标签文本域标签文本域标签文本域标签文本域标签文本域标签文本域标签
        文本域标签文本域标签文本域标签文本域标签文本域标签文本域标签文本域标签文本域标签文本域标签文本域标签
    </textarea>
```

## 5. label标签

> 1. 使用场景：常用于绑定内容和表单标签的关系
> 2. 使用方法1
>    1. 使用label标签把内容包裹
>    2. 在表单标签上添加id属性
>    3. 在label标签的for属性中设置对应的id值
> 3. 使用方法2
>    1. 直接使用label标签把内容和标点标签一起包裹
>    2. 需要吧label标签的for属性删除

```html
<label >
        单选框1<input type="radio" name="1">
    </label>
    <label >
        单选框2<input type="radio" name="1">
    </label>
```

# 8. 语义化标签

## 1. 无语义

> 1. div: 双标签，独占一行
> 2. span：双标签



## 2. 有语义

> 1. 显式特点同 div

| 标签名  | 语义       |
| ------- | ---------- |
| header  | 网页头部   |
| nav     | 网页导航   |
| footer  | 网页底部   |
| aside   | 网页侧边栏 |
| section | 网页区块   |
| article | 网页文章   |

# 9. 字符实体

> 空格： &nbsp



---
---


<h1>css</h1>

# 1. 引入方式

> 1. 内嵌式：写在style标签内部，head标签内
> 2. 外联式：单独写在一个 .css文件 ； 通过link标签引入
> 3. 行内式： 写在标签的style属性内

# 2. 基础选择器

## 1. 标签选择器

> 1. 标签名{css属性：属性值}
> 2. 作用：通过标签名，找到页面中所有这类标签，设置样式
> 3. ⚠️：
>    1. 标签选择器选择一类标签，而非单独某一个
>    2. 不管嵌套关系

## 2. 类选择器

> 1. .类名 {css属性：属性值}
> 2. 作用：通过类名，找到页面中所有这个含这个类名的标签，设置样式
> 3. ⚠️
>    1. 所有标签都有class属性
>    2. 类名可尤数字字母中划线组成，不以数字，中划线开头
>    3. 一个标签可有多个类名，<u>**空格**</u>隔开
>    4. 类名可以重复，一个类选择器可同时选择多个标签

## 3. id选择器

> 1. #id属性值 {css属性：属性值}
> 2. 作用：通过id属性值，找到页面中所有带这个id值的标签，设置样式
> 3. ⚠️
>    1. 所有标签都有id属性值
>    2. id属性值时唯一不重复的
>    3. 一个标签只能有一个id
>    4. 一个id选择器智能选择一个标签

## 4. 通配符选择器

> 1. \* {css属性：属性值}
> 1. 作用：找到页面中的所有标签，设置样式
> 3. ⚠️
>    1. 开发中极少使用

# 3. 文字样式

## 1. 字体大小

> 1. font-size
> 2. 数字+px
> 3. ⚠️
>    1. chrome默认16px
>    2. 需设置单位

## 2. 字体粗细

> 1. font-weight
> 2. 取值
>    1. normal：正常 400
>    2. bold：加粗 700
>    3. 或者100 - 900 的整百数
> 3. ⚠️
>    1. 不是所有字体都有九种粗细
>    2. 实际开发中一正常，加粗两种居多

## 3. 是否倾斜

> 1. font-style
> 2. 取值：
>    1. normal：正常
>    2. italic：倾斜

## 4. 字体

> 1. font-family

## 样式层叠

> 如果给同一个标签设置了相同的属性，此时样式会成叠(覆盖)，写在最下面的会生效

## 5. 复合属性

> 1. ⚠️：只能省略前两个，相当于设置了默认值
>
> 2. 如需同时设置连写的单独：
>    - 要么把单独的样式写在连写的下面，要么里面
>
> 

```css
font:style weight size fanily
```



# 4. 文本样式

> 1.  缩进： text-indent
>
>    1. 数字+px
>    2. 数字+em(推荐 ； 1em=当前标签的 font-size的大小)
>
> 2.  水平对齐：text-align
>
>    1. left：左对齐
>    2. center：居中对齐
>    3. right：右对齐
>    4. ⚠️：如需文本水平居中，text-align属性给文本所在标签设置
>
> 3.  文本修饰： text-decoration
>
>    1. underline：下划线(常用)
>    2. line- through： 删除线
>    3. overline：上划线
>    4. none: 无装饰线
>    5. ⚠️：使用 none 属性值，清除 a 标签的下划线
>
> 4.  行高：line-height
>     1.  取值：
>         1.  数字+px
>         2.  倍数（当前标签font-size的倍数
>     2.  应用：
>         1.  让单行文本垂直居中
>         2.  精准布局时
>     3.  行高于font连写时
>         1.  ⚠️覆盖问题：font： style weight size/line-height family
>

