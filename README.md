# JavaScript-Function

typeof

valuof

this

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


Symbol.iterator 就是：

定義物件如何被 for...of、展開運算子(...)、Array.from() 逐一取出元素的規則。

# JavaScript 重點整理

## 1. 解構賦值（Destructuring Assignment）

```js
let point = [80, 90, 100]
let [x, y, z] = point
```

結果：

```js
x = 80
y = 90
z = 100
```

---

## 2. Rest Operator

```js
let [head, ...tail] = point
```

結果：

```js
head = 80
tail = [90, 100]
```

說明：

- `head` 取得第一個元素
- `...tail` 收集剩餘元素成陣列

---

## 3. 三元運算子（Ternary Operator）

語法：

```js
條件 ? 成立時執行 : 不成立時執行
```

例如：

```js
head ? head + sum(tail) : 0
```

等同於：

```js
if (head) {
    return head + sum(tail)
} else {
    return 0
}
```

---

## 4. 遞迴（Recursion）

```js
function sum([head, ...tail]) {
    return head ? head + sum(tail) : 0
}

console.log(sum([1, 2, 3, 4, 5]))
```

輸出：

```js
15
```

較安全寫法：

```js
function sum([head, ...tail]) {
    return head !== undefined
        ? head + sum(tail)
        : 0
}
```

避免遇到 `0` 時提前結束。

---

## 5. valueOf()

取得物件的原始值（Primitive Value）。

```js
let num = new Number(100)

console.log(num.valueOf())
```

輸出：

```js
100
```

常用於數值運算。

---

## 6. toString()

將資料轉換成字串。

```js
let arr = [1, 2, 3]

console.log(arr.toString())
```

輸出：

```js
"1,2,3"
```

---

## 7. Symbol()

建立唯一的 Symbol。

```js
let s1 = Symbol("id")
let s2 = Symbol("id")

console.log(s1 === s2)
```

輸出：

```js
false
```

每次建立都是不同的 Symbol。

---

## 8. Symbol.for()

從全域 Symbol 註冊表取得或建立 Symbol。

```js
let s1 = Symbol.for("id")
let s2 = Symbol.for("id")

console.log(s1 === s2)
```

輸出：

```js
true
```

相同 key 會取得同一個 Symbol。

---

## 9. Symbol.keyFor()

取得 Symbol.for() 的 key。

```js
let s = Symbol.for("student")

console.log(Symbol.keyFor(s))
```

輸出：

```js
"student"
```

---

## 10. Symbol.iterator

定義物件如何被遍歷（Iterate）。

常用於：

```js
for...of
[...array]
Array.from()
```

範例：

```js
let arr = [10, 20, 30]

let it = arr[Symbol.iterator]()

console.log(it.next())
```

輸出：

```js
{ value: 10, done: false }
```

Iterator 格式：

```js
{
    value: 值,
    done: 是否結束
}
```

---

## 11. throw

主動拋出錯誤。

```js
throw new Error("發生錯誤")
```

搭配 try...catch：

```js
try {
    throw new Error("帳號不存在")
}
catch(err) {
    console.log(err.message)
}
```

輸出：

```js
帳號不存在
```

---

## 12. try...catch

捕捉程式錯誤。

```js
try {
    可能出錯的程式
}
catch(err) {
    錯誤處理
}
```

範例：

```js
try {
    throw "Error"
}
catch(err) {
    console.log(err)
}
```

---

# 考試重點速查表

| 語法 | 功能 |
|--------|--------|
| `[a,b] = arr` | 解構賦值 |
| `...tail` | 收集剩餘元素 |
| `condition ? A : B` | 三元運算子 |
| Recursion | 函式呼叫自己 |
| `valueOf()` | 取得原始值 |
| `toString()` | 轉字串 |
| `Symbol()` | 唯一 Symbol |
| `Symbol.for()` | 共用 Symbol |
| `Symbol.keyFor()` | 取得 Symbol key |
| `Symbol.iterator` | 定義迭代規則 |
| `throw` | 拋出錯誤 |
| `try...catch` | 捕捉錯誤 |
