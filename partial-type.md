# Partial< Type>

```javascript
interface Product {
   name: string;
   description: string;
}
let currentProduct: Product = {
   name: "FS2000",
   description: "Hippie Control"
};
function update1(product: Product) {
   Object.assign(currentProduct, product);
}

function update2(product: Partial<Product>) {
    Object.assign(currentProduct, product);
}
```

Như ví dụ trên, khi sử dụng hàm `update1` thường IDE sẽ cảnh báo lỗi nếu tham số truyền vào  không đủ property như
`update1({name: "FSLight" });`

Với `Partial<Type>` ta có thể truyền 1 phần property vào mà không bị IDE báo lỗi 
`update2({name: "FSLight" });`