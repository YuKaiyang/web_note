1. jsx天然防止XSS攻击(因为任何变量在嵌入dom之前都会解释成普通的字符串)
1. At Facebook, we use React in thousands of components, and we haven’t found any use cases where we would recommend creating component inheritance hierarchies.
1. { Suspense, lazy }用来实现组件懒加载(可结合react-router使用,暂不支持服务端渲染)
1. React.forwardRef实现向前(向上)引用
1. mixins被Higher-Order Components替代,HOC是纯函数,无副作用(感觉还是像组合,或者说是装饰器;参数化容器组件的定义)
1. 高阶组件的常见危险是放到render方法中,解决方法是Instead, apply HOCs outside the component definition so that the resulting component is created only once. Then, its identity will be consistent across renders. This is usually what you want, anyway.
1. 事件传递
  ```jsx
  <button onClick={(e) => this.handleClick(e)}>Click me</button>
  // 这种语法如果传递给子组件,可能会导致子组件重复渲染
  // 所以建议还是在constructor方法或者是在类字段方法中使用箭头函数中绑定this
  ```
  
