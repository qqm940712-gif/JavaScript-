# JavaScript 重點整理

# 1. 變數宣告

## let

可重新賦值，不可重複宣告。

```js
let age = 18
age = 20
```

## const

不可重新賦值。

```js
const PI = 3.14
```

## var

舊式宣告方式，較少使用。

```js
var name = "Tom"
```

---

# 2. 基本資料型態

```js
Number
String
Boolean
Undefined
Null
Object
Symbol
BigInt
```

範例：

```js
let age = 18
let name = "Amy"
let pass = true
let score = null
let test
```

---

# 3. typeof

查看資料型態。

```js
console.log(typeof 123)
```

輸出：

```js
number
```

範例：

```js
typeof 123          // number
typeof "hello"      // string
typeof true         // boolean
typeof undefined    // undefined
typeof Symbol()     // symbol
```

---

# 4. 字串模板 Template Literal

```js
let name = "Amy"

console.log(`Hello ${name}`)
```

輸出：

```js
Hello Amy
```

---

# 5. 條件判斷

## if

```js
if (score >= 60) {
    console.log("Pass")
}
```

## if...else

```js
if (score >= 60) {
    console.log("Pass")
}
else {
    console.log("Fail")
}
```

## switch

```js
switch(day){
    case 1:
        console.log("Monday")
        break

    default:
        console.log("Other")
}
```

---

# 6. 比較運算子

| 運算子 | 說明 |
|---------|---------|
| == | 值相等 |
| === | 值與型別都相等 |
| != | 不等於 |
| !== | 值或型別不同 |
| > | 大於 |
| < | 小於 |
| >= | 大於等於 |
| <= | 小於等於 |

範例：

```js
5 == "5"     // true
5 === "5"    // false
```

---

# 7. 迴圈

## for

```js
for(let i = 0; i < 5; i++){
    console.log(i)
}
```

## while

```js
let i = 0

while(i < 5){
    console.log(i)
    i++
}
```

## for...of

遍歷陣列。

```js
let arr = [1,2,3]

for(let x of arr){
    console.log(x)
}
```

## for...in

遍歷物件屬性。

```js
let obj = {
    name:"Amy",
    age:18
}

for(let key in obj){
    console.log(key)
}
```

---

# 8. 函式 Function

```js
function add(a,b){
    return a+b
}
```

呼叫：

```js
console.log(add(3,5))
```

---

# 9. 箭頭函式 Arrow Function

```js
const add = (a,b)=>{
    return a+b
}
```

簡寫：

```js
const add = (a,b)=>a+b
```

---

# 10. 陣列 Array

建立：

```js
let arr = [10,20,30]
```

常用方法：

```js
arr.push(40)
```

加入尾端元素。

```js
arr.pop()
```

移除尾端元素。

```js
arr.shift()
```

移除第一個元素。

```js
arr.unshift(5)
```

加入第一個元素。

---

# 11. 物件 Object

```js
let student = {
    name:"Amy",
    age:18
}
```

存取：

```js
student.name
student["age"]
```

---

# 12. 解構賦值

```js
let point = [80,90,100]

let [x,y,z] = point
```

結果：

```js
x = 80
y = 90
z = 100
```

---

# 13. Rest Operator

```js
let [head,...tail] = point
```

結果：

```js
head = 80
tail = [90,100]
```

---

# 14. Spread Operator

複製陣列：

```js
let arr1 = [1,2,3]

let arr2 = [...arr1]
```

合併陣列：

```js
let arr3 = [...arr1,...arr2]
```

---

# 15. 三元運算子

```js
條件 ? A : B
```

例如：

```js
let result = score >= 60 ? "Pass" : "Fail"
```

---

# 16. 遞迴 Recursion

```js
function sum([head,...tail]){
    return head !== undefined
        ? head + sum(tail)
        : 0
}
```

---

# 17. valueOf()

取得原始值。

```js
let num = new Number(100)

num.valueOf()
```

結果：

```js
100
```

---

# 18. toString()

轉換成字串。

```js
let arr = [1,2,3]

arr.toString()
```

結果：

```js
"1,2,3"
```

---

# 19. Symbol()

建立唯一 Symbol。

```js
let s1 = Symbol("id")
let s2 = Symbol("id")
```

```js
s1 === s2
```

結果：

```js
false
```

---

# 20. Symbol.for()

全域共享 Symbol。

```js
let s1 = Symbol.for("id")
let s2 = Symbol.for("id")
```

```js
s1 === s2
```

結果：

```js
true
```

---

# 21. Symbol.iterator

定義如何被遍歷。

```js
let it = arr[Symbol.iterator]()
```

```js
it.next()
```

輸出：

```js
{
    value:10,
    done:false
}
```

---

# 22. throw

主動產生錯誤。

```js
throw new Error("Error")
```

---

# 23. try...catch

捕捉錯誤。

```js
try{
    throw new Error("Error")
}
catch(err){
    console.log(err.message)
}
```

---

# 24. API

API（Application Programming Interface）

用途：

- 讓不同程式互相溝通
- 取得資料
- 呼叫服務

範例：

```js
fetch(url)
```

---

# 25. JSON

物件格式資料。

```js
{
    "name":"Amy",
    "age":18
}
```

轉換：

```js
JSON.stringify(obj)
```

物件 → JSON

```js
JSON.parse(json)
```

JSON → 物件

---

# 考試重點速查表

| 主題 | 重點 |
|--------|--------|
| let | 可修改 |
| const | 不可修改 |
| typeof | 查看型別 |
| === | 值與型別都相同 |
| Array | 陣列 |
| Object | 物件 |
| Function | 函式 |
| Arrow Function | 箭頭函式 |
| Destructuring | 解構賦值 |
| Rest | 收集剩餘元素 |
| Spread | 展開元素 |
| Symbol | 唯一值 |
| Symbol.for | 共用 Symbol |
| Symbol.iterator | 迭代器 |
| valueOf | 原始值 |
| toString | 字串表示 |
| throw | 拋出錯誤 |
| try...catch | 捕捉錯誤 |
| JSON | 資料交換格式 |
| API | 程式溝通介面 |
