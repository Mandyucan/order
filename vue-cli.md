```
// js
var one = new Vue({
    el: "#vue-app-one",
    data: {
        title:"app one 的内容"
    },

    methods: {
        
    },
    computed: {
        greet: function(){
            return "hello app one"
        }
    }
});

var two = new Vue({
    el: "#vue-app-two",
    data: {
        title:"app two 的内容"
    },

    methods: {
        changeTitle:function () {
            one.title = "已经改名了" //在app2里改变app1的title
        }
    },
    computed: {
        greet: function(){
            return "hello app two"
        }
    }
});
two.title= "app two 的title也发生变化" // 也可以在最外面改变app2的title
```

```
// html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Vue.js</title>
    <link rel="stylesheet">
    <script src="https://unpkg.com/vue/dist/vue.js"></script>    
</head>
<body>
    <h1>初始化多个Vue实例对象</h1>
    <div id="vue-app-one">
        <h2>{{title}}</h2>
        <p>{{greet}}</p>
    </div>
    <div id="vue-app-two">
        <h2>{{title}}</h2>
        <p>{{greet}}</p>
        <button @click="changeTitle">Change App One Title</button>        
    </div>
    <script src="app.js"></script>
</body>
</html>
```
