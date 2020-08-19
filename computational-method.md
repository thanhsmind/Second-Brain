 # Computational method ( Phương pháp tính) 
 >Let us formally define a computational method to be a quadruple (Q, I, Ω, f), in which Q is a set containing subsets I and Ω and f is a function from Q into itself.


 ***computational method*** được tổ hợp bởi 4 thành phần ***quadruple*** `(Q,I,Ω,f)`. 
 - Trong đó `I,Ω` là tập hợp chứa nhiều giá trị khác nhau 
 - `Q` là 1 tập hợp chứa `I,Ω⊆Q`, không chỉ vậy, Khi function `f` xử lý nó sẽ lấy đầu vào `I` là những giá trị nằm trong `Q` sau đó `f` sẽ trả ra `Ω: OUTPUT` những giá trị tới `Q`

> Furthermore f should leave Ω pointwise fixed; that is, f(q) should equal q for all elements q of Ω.

Câu này đơn giản được hiểu nghĩa là. Những gì mà hàm `f` sau khi xử lý trả về sẽ giống với đối số `q` nếu đối số `q` là 1 thành phần của tập `Ω`. Lý do là `Ω` là 1  tập hợp của các giá trị đầu ra của ***computational method***(phương pháp tính). Đưa 1 giá tri `Ω` output vào trở lại làm `f` sẽ không làm thay đổi giá trị của nó.

Ý nghĩa của từng thành phần trong ***computational method***:
- `Q` the states of the computation
- `I` the input
- `Ω` the output
- `f` the computational rule



