#  vueTest
## vue学习--初级 
### 一、组件的学习 
#### 1.组件使用的基本步骤 
    （1）创建组件
    
        var componentName=Vue.extend({
            template:'<div>this is the way to create a component</div>'
        });
        
    （2）注册组件
    
         Vue.component('lable-name',componentName);
         
    （3）创建vue示例，应用组件
    
         new Vue({
            el:'#app'
         });
         
    （4）页面实例化组件,放置u需要组件的位置
    
         <lable-name></lable-name>
         
#### 2.全局组件和局部组件
    （1）全局组件
    
         以上的写法就属于全局组件
        
    （2）局部组件
    
         组件定义到某个元素的示例内部,该组件只能应用在#app内
            
         var componentName=Vue.extend({
             template:'<div>this is the way to create a component</div>'
         });
         new Vue({
            el:"#app",
            components:{
                  'lable-name':componentName
            }
         });
         
#### 3.父组件和子组件

        我们可以在组件中定义和使用其他组件，就构成了父子组件
        
#### 4.组件注册语法糖
        简单理解就是代码的简写：
    
        Vue.component('label-name',{template:'<div>i这是一个语法糖</div>'})
      
#### 5.使用script或者template---推荐使用

        更好的让js和html分开
        Vue.component('component-name','模板ID');
        (1)script需要些上type类型
            <script type="x-template" id="模板ID">
                html代码
            </script>
        (2)template不需要些上type类型
            <template id="模板ID">
                html代码
            </template>
          
#### 6.props、sync、once

        props是子组件借用父组件的值，默认是单向绑定，父级改变，子组件跟着变化;
        sync可以把单向绑定转化为双向绑定;
        once是单次绑定，父组件不会影响子组件，互不影响;
     
#### 注意事项

    在c组件中写data、el的时候，需要使用函数格式;
        Vue.component({
            template:'#com',
            data:function(){
            return {
                msg:'this is a expamle';
              }
           }
        });
        
### 二、组件的学习（下）

#### 1.作用域

    通俗说子组件的数据只能在子模板中使用，父组件的数据只能在父模板中使用；
    子组件要想使用父组件的数据可以使用props
    
#### 2.slot的介绍

    slot就是一个内容插槽，多个插槽可以使用name区别
    
#### 3.父子组件之间的通信

    父组件访问子组件：$children或者$refs(refs是通过v-ref：aaa的方法给子元素起一个索引ID);
    子组件访问父组件：$parent;
    子组件访问根组件：$root;
    
Demo：
[$children](https://github.com/qnilike/vueTest/blob/master/vueComponentD/%24children.html)
[$ref](https://github.com/qnilike/vueTest/blob/master/vueComponentD/%24refs.html)
[$parent](https://github.com/qnilike/vueTest/blob/master/vueComponentD/%24parent.html)

#### 4.自定义事件

    每个 Vue 实例都是一个事件触发器：
    使用 $on() 监听事件；
    使用 $emit() 在它上面触发事件；
    使用 $dispatch() 派发事件，事件沿着父链冒泡；
    使用 $broadcast() 广播事件，事件向下传导给所有的后代。

Demo：[派发事件](https://github.com/qnilike/vueTest/blob/master/vueComponentD/%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6-%E6%B4%BE%E5%8F%91%E4%BA%8B%E4%BB%B6.html)
[广播事件](https://github.com/qnilike/vueTest/blob/master/vueComponentD/%E8%87%AA%E5%AE%9A%E4%B9%89%E4%BA%8B%E4%BB%B6-%E6%B4%BE%E5%8F%91%E4%BA%8B%E4%BB%B6.html)

### 总结
    Vue.js组件的API来源于三部分——prop，slot和事件。
    prop 允许外部环境传递数据给组件；
    事件 允许组件触发外部环境的 action；
    slot 允许外部环境插入内容到组件的视图结构内。



==================================================================
### 二、router
