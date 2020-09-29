# Arrow function
#es6, #ecmascript2015 
Arrow Function là cú pháp giúp đơn giản việc định nghĩa hàm.
Cú pháp : `() => { };`

**Hàm số không có tham số**
```javascript
let sayHello => () {
    console.log("Hello everyone!");
}
```
**Hàm số có 1 đối số**
```javascript
let doubleNumber = a => {
    return a * 2;
}
```