1. jsx天然防止XSS攻击(因为任何变量在嵌入dom之前都会解释成普通的字符串)
```jsx
<button onClick={(e) => this.handleClick(e)}>Click me</button>
// 这种语法如果传递给子组件,可能会导致子组件重复渲染
// 所以建议还是在constructor方法中绑定方法
```
