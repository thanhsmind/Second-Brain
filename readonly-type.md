# Readonly< Type>
Variable khai báo readonly sẽ không thể thay đổi được 
```javascript
interface Todo {
  title: string;
}

const todo: Readonly<Todo> = {
  title: "Delete inactive users",
};

todo.title = "Hello";
//Cannot assign to 'title' because it is a read-only property.
```