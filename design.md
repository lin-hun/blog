## 问题：mvc设计模式的衍生问题
### 设计模式的历史演进 mvc => mvp => mvvm => flux
+ mvvm现在还在用吗？ 
  + 答:用得少。我认为前端尝试过mvvm，如angular、vue，但vue2已然偏向单向数据流。双向数据让我们管理起来更混乱，数据多的情况难以调试和维护。适当使用，比如input输入框v-model。
+ 用了vue和react确实帮我们提升了开发效率，但是vuex和redux呢（他们设计思路非常好，但是写dispatch和action让我觉得很费劲）？开发效率和维护效率到底有没有提升（有没有具体数字来衡量和评价呢）？
+ 既然谈到设计模式，我们采用mvc的方式写代码，应该是什么样的？
  + 答：传统如下
  ```javascript
  // define model
  function model(){
    this.list = []
  }
  model.prototype.add = function(){
    render()
  }
  model.prototype.remove = function(){
    render()
  }
  
  // define controller
  button.addEventListener('click',()=>{
    model.add
  })
  
  // view
  function render(){
    
  }
  
  ```
  + 答：vue的话
  ```javascript
    // 框架让我们简化了controller 简化了view层
    let data = {}
    new Vue({
        data:data,
        methods:{
            add(){
                data.a = 'a' // 直接操作data
            }
        }
    })
    
    ```