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


# JavaScript 物件導向（OOP）

---

# 1. 物件 Object

建立物件：

```js
let student = {
    name: "Amy",
    age: 18,

    sayHello() {
        console.log("Hello")
    }
}
```

存取屬性：

```js
console.log(student.name)
console.log(student["age"])
```

呼叫方法：

```js
student.sayHello()
```

---

# 2. this

代表目前物件本身。

```js
let student = {
    name: "Amy",

    introduce() {
        console.log(`我是 ${this.name}`)
    }
}
```

輸出：

```js
我是 Amy
```

---

# 3. 建構式 Constructor Function

ES6 出現前建立物件的方式。

```js
function Student(name, age) {
    this.name = name
    this.age = age
}
```

建立物件：

```js
let s1 = new Student("Amy", 18)
let s2 = new Student("Tom", 20)
```

結果：

```js
s1.name // Amy
s2.name // Tom
```

---

# 4. new 的作用

```js
let s1 = new Student("Amy", 18)
```

new 會：

1. 建立空物件
2. this 指向新物件
3. 執行建構式
4. 回傳新物件

相當於：

```js
let obj = {}

Student.call(obj, "Amy", 18)

return obj
```

---

# 5. 原型物件 Prototype

每個函式都有 prototype。

```js
function Student(name) {
    this.name = name
}

console.log(Student.prototype)
```

---

# 6. 在 Prototype 加入方法

錯誤寫法：

```js
function Student(name) {
    this.name = name

    this.sayHello = function() {
        console.log("Hello")
    }
}
```

每建立一次物件就產生一份函式。

---

較佳寫法：

```js
function Student(name) {
    this.name = name
}

Student.prototype.sayHello = function() {
    console.log("Hello")
}
```

建立：

```js
let s1 = new Student("Amy")
let s2 = new Student("Tom")
```

所有物件共用同一個方法。

---

# 7. Prototype Chain 原型鏈

```js
console.log(s1.__proto__ === Student.prototype)
```

結果：

```js
true
```

關係：

```text
s1
 ↓
Student.prototype
 ↓
Object.prototype
 ↓
null
```

---

# 8. instanceof

判斷物件是否由某建構式建立。

```js
let s1 = new Student("Amy")

console.log(s1 instanceof Student)
```

結果：

```js
true
```

---

# 9. 類別 Class（ES6）

ES6 新語法。

```js
class Student {

    constructor(name, age) {
        this.name = name
        this.age = age
    }

    sayHello() {
        console.log("Hello")
    }
}
```

建立：

```js
let s1 = new Student("Amy", 18)
```

---

# 10. constructor

類別中的建構函式。

```js
class Student {

    constructor(name) {
        this.name = name
    }
}
```

執行：

```js
let s1 = new Student("Amy")
```

自動呼叫 constructor。

---

# 11. 類別方法

```js
class Student {

    constructor(name) {
        this.name = name
    }

    introduce() {
        console.log(`我是 ${this.name}`)
    }
}
```

使用：

```js
s1.introduce()
```

---

# 12. Getter

讀取屬性時自動執行。

```js
class Student {

    constructor(name) {
        this.name = name
    }

    get upperName() {
        return this.name.toUpperCase()
    }
}
```

使用：

```js
console.log(s1.upperName)
```

注意：

```js
不要加 ()
```

---

# 13. Setter

設定屬性時自動執行。

```js
class Student {

    constructor(name) {
        this.name = name
    }

    set studentName(value) {
        this.name = value
    }
}
```

使用：

```js
s1.studentName = "Tom"
```

---

# 14. static

靜態方法。

屬於類別，不屬於物件。

```js
class MathTool {

    static add(a, b) {
        return a + b
    }
}
```

呼叫：

```js
MathTool.add(3, 5)
```

不能：

```js
let m = new MathTool()

m.add()
```

---

# 15. 繼承 extends

```js
class Animal {

    eat() {
        console.log("eat")
    }
}

class Dog extends Animal {

}
```

使用：

```js
let dog = new Dog()

dog.eat()
```

輸出：

```js
eat
```

---

# 16. super

呼叫父類別 constructor。

```js
class Animal {

    constructor(name) {
        this.name = name
    }
}

class Dog extends Animal {

    constructor(name, age) {
        super(name)

        this.age = age
    }
}
```

---

# 17. 方法覆寫 Override

```js
class Animal {

    speak() {
        console.log("Animal")
    }
}

class Dog extends Animal {

    speak() {
        console.log("Woof")
    }
}
```

輸出：

```js
Woof
```

---

# 18. Object.create()

建立指定原型的物件。

```js
let animal = {
    eat() {
        console.log("eat")
    }
}

let dog = Object.create(animal)
```

結果：

```text
dog
 ↓
animal
 ↓
Object.prototype
```

---

# 19. Object.keys()

取得所有屬性名稱。

```js
let obj = {
    name: "Amy",
    age: 18
}

console.log(Object.keys(obj))
```

輸出：

```js
["name", "age"]
```

---

# 20. Object.values()

取得所有值。

```js
console.log(Object.values(obj))
```

輸出：

```js
["Amy", 18]
```

---

# 21. Object.entries()

轉成鍵值對陣列。

```js
console.log(Object.entries(obj))
```

輸出：

```js
[
  ["name", "Amy"],
  ["age", 18]
]
```

---

# 物件導向考試速查表

| 主題 | 功能 |
|--------|--------|
| Object | 物件 |
| this | 目前物件 |
| Constructor | 建構式 |
| new | 建立物件 |
| prototype | 原型物件 |
| Prototype Chain | 原型鏈 |
| instanceof | 判斷類型 |
| class | 類別 |
| constructor | 建構函式 |
| get | Getter |
| set | Setter |
| static | 靜態方法 |
| extends | 繼承 |
| super | 呼叫父類別 |
| override | 方法覆寫 |
| Object.create() | 指定原型建立物件 |
| Object.keys() | 取得所有 key |
| Object.values() | 取得所有 value |
| Object.entries() | 取得所有鍵值對 |
