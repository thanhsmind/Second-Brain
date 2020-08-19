# Defining an Algorithm

> An ***algorithm*** is a computational method that terminates in finitely many steps for all `x∈I`.

Thuật toán là 1 tập hữu hạn các phép tính toán đối với mọi x là Input

>Let us formally define a computational method to be a quadruple (Q, I, Ω, f), in which Q is a set containing subsets I and Ω and f is a function from Q into itself.

***computational method*** được tổ hợp bởi 4 thành phần ***quadruple*** `(Q,I,Ω,f)`. 
 - Trong đó `I,Ω` là tập hợp chứa nhiều giá trị khác nhau 
 - `Q` là 1 tập hợp chứa `I,Ω⊆Q`, không chỉ vậy, Khi function `f` xử lý nó sẽ lấy đầu vào `I` là những giá trị nằm trong `Q` sau đó `f` sẽ trả ra `Ω: OUTPUT` những giá trị tới `Q`

> Furthermore f should leave Ω pointwise fixed; that is, f(q) should equal q for all elements q of Ω.

Câu này đơn giản được hiểu nghĩa là. Những gì mà hàm `f` sau khi xử lý trả về sẽ giống với đối số `q` nếu đối số `q` là 1 thành phần của tập `Ω`. Lý do là `Ω` là 1  tập hợp của các giá trị đầu ra của ***computational method***(phương pháp tính). Đưa 1 giá tri `Ω` output vào trở lại làm `f` sẽ không làm thay đổi giá trị của nó.

> The four quantities Q, I, Ω, f are intended to represent respectively the states of the computation, the input, the output, and the computational rule.

Ý nghĩa của từng thành phần trong ***computational method***:
- `Q` the states of the computation
- `I` the input
- `Ω` the output
- `f` the computational rule, Quy trình được áp dụng cho mỗi stage để có được state tiếp theo. Đến cuối cùng sẽ ra được output

> Each input x in the set I defines a computational sequence, x0, x1, x2, ..., as follows: x0 = x and xk+1 = f(xk) for k ≥ 0.

Mỗi Input x là 1 chuỗi tính toán nối tiếp nhau, ví dụ: `x1=f(x0)` x1 là kết quả của sau khi xử lý của `f`. `x0=x` là giá trị bắt đầu, giá trị tiếp theo được xác định `xk+1=f(xk)` với `k>=0` 

>The computational sequence is said to terminate in k steps if k is the smallest integer for which xk is in Ω, and in this case it is said to produce the output xk from x.




