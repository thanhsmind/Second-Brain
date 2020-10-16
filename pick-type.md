# Pick< Type, Keys>
Khơỉ tạo biến bằng cách chọn một vài Keys từ Type
```javascript

interface Todo {
  title: string;
  description: string;
  completed: boolean;
}

type TodoPreview = Pick<Todo, "title" | "completed">;

const todo: TodoPreview = {
  title: "Clean room",
  completed: false,
};

todo;
// ^ = const todo: Pick
```