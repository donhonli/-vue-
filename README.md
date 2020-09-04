原生js模拟vue响应式

引入vue.js
<script src="./js/vue.js"></script>
创建vue实例对象
let vm = new Vue({
            el:"#app",
            data:{
                msg:'Hello Vue',
                count:100,
                person:{name:'zs'}
            }
        })

Vue.js:把data中成员注入到vue实例，并把data中成员转为getter/setter
Observe.js:对数据对象的所有属性进行监听，如有变动通知Dep（发布者）
Compiler:解析每个元素的指令以及差值表达式，替换成响应模式，首次渲染页面，数据变化后重新渲染视图
Dep.js:收集依赖，添加观察者
Watcher:当数据变化 触发依赖，dep通知所有Watcher实例更新视图（自身实例化时 往dep中添加自己）
