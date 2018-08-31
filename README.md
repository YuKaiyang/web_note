## web_note
webpack4已经默认包含json-loader，再次添加rules反倒会失效报错
IE11 has an issue with only having min-height. This cause the flex-grow property dosn't work.
## js_note

```
"use strict"
// 普通函数（如果用new操作符调用时就会返回一个新的对象实例，这时就是构造函数）
function Person(name, age) {
  this.name = name
  this.age = age
}
/*
* 构造函数的prototype指向对象原型, 此时是
* Person {
*   say(...)
* }
*/
Person.prototype.say = function () {
  console.log(`Hello my name is ${this.name}`)
}

const p1 = new Person('p1', 12)
const p2 = new Person('p2', 30)
const p3 = Object.create(p1)
// const p3 = p1
// 此时p3是空对象，它的全部属性都通过原型链指向p1
console.log(p3)
console.log(p3.age)
p3.name = 'p3'
console.log(p3)
p1.say()
p3.say()
```

## vue_note
1. 计算属性有基于依赖的缓存，方法则每次都会重新执行
1. v-if为false时组件根本不会被渲染，v-show只是操作是否可见（需要频繁切换的情况更适合用show）
1. 替换数组（用一个含有相同元素的数组去替换原来的数组是非常高效的操作）
1. 如果v-model表达式的初始值未能匹配任何选项，`<select>`元素将被渲染为“未选中”状态。在iOS中，这会使用户无法选择第一个选项。因为这样的情况下，iOS不会触发change事件。因此，更推荐像上面这样提供一个值为空的禁用选项。
1. 组件中的data必须是一个函数，作用是为每个实例可以维护一份被返回对象的独立的拷贝
1. 组件中非prop的特性（attribute）会被直接添加到组件中的根元素上  
接上，使用inheritAttrs: false可以关闭该特性
1. `.sync`修饰符用于实现组件内部更新父组件props值的emit的缩写（作用于对象字面量时无效）
1. `<slot>`跟react中的child类似，不过可以配合name进行指定分发，另外还允许指定默认值`<slot>Submit</slot>`
1. keep-alive属性用来缓存组件的状态
1. $root用来访问根元素实例, $parent用来访问父组件实例, `ref`属性用来定义子组件的引用, 定义后可从$refs访问子组件实例
