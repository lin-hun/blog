# 问题：怎么判断代码写得好？
## 应该需要两个标准
+ 可阅读性
+ 可维护性

## 可阅读性
+ 代码的语法规则，诸如===、字符串用单引号、换行等等，可以参考[airbnb语法风格](https://github.com/airbnb/javascript),辅以eslint强检查。
    + hint:良好的代码风格能帮助大家更好的合作，谁愿意看到对方的代码写的跟自己不一样呢？你想因为tab等于几个空格吵架吗？
+ 良好的逻辑性，又分为代码逻辑和产品逻辑。
    + 代码逻辑，诸如公用方法提炼成单独function or 文件、事件绑定和数据处理分离等（这其实是包含设计模式）
    + 产品逻辑，不管是业务代码还是技术底层，是需要产品逻辑去支撑。业务代码更多的是对pm、ui的消化 => 代码 => 再通过逻辑整理 =>得到代码逻辑。（这个地方可以展开了说）
## 可维护性
### 怎么才能得到一份可维护的代码呢？和以上的可阅读性区分开来，我认为是把设计模式引入代码。
+ 在代码中体现设计模式。
  + 思考：其实数据管理（model）、控制器或者监听器（controller）、视图管理（view）应该分离，也就是传统mvc，在java、ios、Android，mvc、mvp的设计模式一直很健壮，为什么到了前端有那么多的变化和分离呢？
+ 使用已有的设计模式,其实是引入框架，这也是我们为什么要用框架的原因。
  + 思考：不管是flux还是mvvm都是对mvc架构的延伸和扩展，重点是为了解决model层的厚重。在前端，model层很重。
  + 思考：vue一开始是和angular做了数据的双向绑定，但到了2之后，更偏向单向数据流，这是不是说vue2其实是mvc的设计？  
+ 那么问题来了，我们引入了框架还能不能再在代码中体现设计模式？比如vue是mvvm框架，我能否用mvc的思想写代码？写出的代码会不会更好？
  + vue和react到底解决了什么问题呢？ 我认为是实现了一个高效率的mvc模式，让开发者专注于数据和视图，不必关心controller层。而区别在于controller层的实现方式不同，vue通过数据劫持和封装的事件语法糖如@click实现controller层，react通过发布订阅模式和封装的语法糖实现。其他的react实现了virtualDom，带来了[性能](https://www.zhihu.com/question/31809713)和移植到其他平台的可能性(RN等等)，当然这是他们其他的特点，但重点是解决了c层。