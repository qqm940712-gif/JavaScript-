# JavaScript-Function

typeof

valuof

symbol

建立全新的 Symbol

symbol.for

建立或取得全域共享的 Symbol

symbol.keyFor

symbol.iterator

一個物件要如何被迭代

例如：

let arr = [10, 20, 30];

for (let x of arr) {
    console.log(x);
}

輸出：

10
20
30

範例:

let arr = [10, 20, 30];

let it = arr[Symbol.iterator]();

console.log(it.next());
console.log(it.next());
console.log(it.next());
console.log(it.next());

輸出：

{ value: 10, done: false }
{ value: 20, done: false }
{ value: 30, done: false }
{ value: undefined, done: true }
