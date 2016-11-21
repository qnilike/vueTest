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

#### 3.父组件和子组

    我们可以在组件中定义和使用其他组件，就构成了父子组件
