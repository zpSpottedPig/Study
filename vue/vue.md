

## vue

开发工具:vs-code

插件：

Bracket Pair Colorizer 2  括号颜色高亮

Debugger for Chrome   谷歌debugger调试

html css support   HTML css格式化

Prettier - Code formatter  代码格式化

live service  热更新

vetur vue插件方便代码编写(自带)

vscode-icons 图标插件

快捷键：

```
!+enter  -- 生成HTML架构
ctrl+/ -- 注释  
```

vue样例

```vue
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <!-- 引入vue.js -->
    <script src="./js/vue.min.js"></script>
</head>
<body>
    -- MVVM 架构
    <div id="app">
        {{name}}{{person.sex}}
        <strong>{{names[0]}}</strong>
        <h2 v-text="name"></h2>
        <input type="button" value="点击事件" v-on:click="show">
        <input type="button" value="点击事件2" @click="show">
    </div>
</body>
<script>
     <!-- 创建vue对象 -->
    var vm = new Vue({
         <!-- 挂载元素节点 -->
        el:"#app",
         <!-- 定义数据 -->
        data:{
            name:"Hello Word!",
            person:{
                name:"lishi",
                sex:"男"
            },
            names:["111","222"]
        },
        <!-- 定义方法 -->
        methods: {
                show:function (){
                    alert("你好");
                }
            },
    });
</script>
</html>

```

vue 标签指令

```vue
v-test 加载data数据值
v-html 加载data数据值，格式化HTML标签
v-on/@ 绑定事件调用methods定义的方法
事件：
    click 单机
    keyup 键盘事件
按键修饰符：
    .enter
    .tab
    .delete (捕获“删除”和“退格”键)
    .esc
    .space
    .up
    .down
    .left
    .right
系统修饰符：
    .ctrl
    .alt
    .shift
    .meta
    .exact
事件修饰符：
    .stop
    .prevent
    .capture
    .self
    .once
    .passive


v-show 逻辑判断值为true/false显示/隐藏（操作样式:display: none;）
v-if 逻辑判断值为true/false显示/隐藏（操作dom:去掉元素标签）
v-bind 设置元素属性 v-bind:属性名=表达式 简写 :属性名=表达式
	   设置元素样式 :syle="{属性名:表达式,属性名=表达式}"
	   设置class  :设置class="{属性名:逻辑表达式值,属性名=逻辑表达式值}"
v-for  循环列表（数组,集合） item[,index](序号从0开始) in items
v-model 双向数据绑定
```

vue封装方法

```vue
push(); 添加值
shift(); 移除第一个值

```

