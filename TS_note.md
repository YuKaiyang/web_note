1. undefine和null是任意类型的子类型
1. 声明变量时如果未指定类型则隐式声明为any类型
1. any的变量可以进行任意操作，比如访问不存在的属性和方法（可以理解为不做检查了）
1. interface可以对对象的形状进行描述（类似schema）
1. interface定义对象属性时有前缀只读`readonly`,后缀可选`?`和任意属性`[propName:类型]:类型`
1. 类型别名与字符串字面量类型都是使用 type 进行定义。
1. 一个斐波那契数列的尾递归实现

```ts
function fib(n: number): number {
  function inside(n: number, a = 1, b = 1): any {
    if (n <= 2) {
      return b
    } else {
      return inside(--n, b, a + b)
    }
  }
  return inside(n)
}
```
