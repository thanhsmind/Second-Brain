# Omit< Type, Keys>
Khởi tạo type bằng cách sử dụng toàn bộ các properties từ Type đó, ngoại trừ những properties được liệt kê trong Keys
```javascript
interface Todo {
  title: string;
  description: string;
  completed: boolean;
}

type TodoPreview = Omit<Todo, "description">;

const todo: TodoPreview = {
  title: "Clean room",
  completed: false,
};

todo;
// ^ = const todo: Pick
```