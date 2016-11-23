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

        更好的让js和html分开;
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

    父组件访问子组件：$children或者$refs;
    子组件访问父组件：$parent;
    子组件访问根组件：$root;
