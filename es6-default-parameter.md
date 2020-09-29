# Default Parameter
#es6, #ecmascript2015 

ES6 hỗ trợ gán giá trị mặc định cho tham số khi định nghĩa hàm.
```javascript
function sayHi(name="there"){
	console.log("Hi "+name);
}

```

==Lưu ý==: khi giá trị truyền vào hàm mặc định có giá trị là `undefined` tương đương với việc không truyền vào đối số. 