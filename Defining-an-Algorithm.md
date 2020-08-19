# Defining an Algorithm

> Some computational sequences may never terminate; an algorithm is a computational method that terminates in finitely many steps for all x in I.

Thuật toán là 1 tập hữu hạn các phép tính toán đối với mọi x là Input

>Let us formally define a computational method to be a quadruple (Q, I, Ω, f), in which Q is a set containing subsets I and Ω and f is a function from Q into itself.

***computational method*** được tổ hợp bởi 4 thành phần ***quadruple*** `(Q,I,Ω,f)`. 
 - Trong đó `I,Ω` là tập hợp chứa nhiều giá trị khác nhau 
 - `Q` là 1 tập hợp chứa `I,Ω⊆Q`, không chỉ vậy, Khi function `f` xử lý nó sẽ lấy đầu vào `I` là những giá trị nằm trong `Q` sau đó `f` sẽ trả ra `Ω: OUTPUT` những giá trị tới `Q`

> Furthermore f should leave Ω pointwise fixed; that is, f(q) should equal q for all elements q of Ω.

Câu này đơn giản được hiểu nghĩa là. Những gì mà hàm `f` sau khi xử lý trả về sẽ giống với đối số `q` nếu đối số `q` là 1 thành phần của tập `Ω`. Lý do là `Ω` là 1  tập hợp của các giá trị đầu ra của ***computational method***(phương pháp tính). Đưa 1 giá tri `Ω` output vào trở lại làm `f` sẽ không làm thay đổi giá trị của nó.

> The four quantities Q, I, Ω, f are intended to represent respectively the states of the computation, the input, the output, and the computational rule.

Ý nghĩa của từng thành phần trong ***computational method***:
- `Q` represents a collection of all possible states of our algorithm
- `I` the input
- `Ω` the output
- `f` the computational rule, Quy trình được áp dụng cho mỗi stage để có được state tiếp theo. Đến cuối cùng sẽ ra được output

> Each input x in the set I defines a computational sequence, x0, x1, x2, ..., as follows: x0 = x and xk+1 = f(xk) for k ≥ 0.

Mỗi Input x là 1 chuỗi tính toán nối tiếp nhau, ví dụ: `x1=f(x0)` x1 là kết quả của sau khi xử lý của `f`. `x0=x` là giá trị bắt đầu, giá trị tiếp theo được xác định `xk+1=f(xk)` với `k>=0` 

> Algorithm E may, for example, be formalized in these terms as follows: Let Q be the set of all singletons (n), all ordered pairs (m, n), and all ordered quadruples (m, n, r, 1), (m, n, r, 2), and (m, n, p, 3), where m, n, and p are positive integers and r is a nonnegative integer. Let I be the subset of all pairs (m, n) and let Ω be the subset of all singletons (n).

Theo thuật toán Euclid, đầu vào `I (input)` là 1 cặp số nguyên dương `(m,n)`.  Kết quả của mỗi state xử lý là 1 số nguyên, và nó được mô tả là ***singleton(n)*** nằm trong tập `Ω`. 

> f((m, n)) = (m, n, 0, 1);   f((n)) = (n);
f((m, n, r, 1)) = (m, n, remainder of m divided by n, 2);
f((m, n, r, 2)) = (n) if r = 0, (m, n, r, 3) otherwise;
f((m, n, p, 3)) = (n, p, p, 1).

ở phần trên chúng ta có công thức `f(xk)=xk+1`
Phần dưới này là ứng dụng công thức vào trong bài toán Euclid cụ thể 
- `f((m, n)) = (m, n, 0, 1); ` Thể hiện input đầu vào là 1 cặp `(m,n)`, 1 là thể hiện bước tiếp theo. `(m, n, 0, 1)` sẽ được đưa vào hàm `f` oh bước tiếp theo
- `f((m, n, r, 1)) = (m, n, remainder of m divided by n, 2);`. Tham số của hàm `f` được lấy bằng kết quả phần trên,  r được tính bằng phần dư của m/n. 
- `f((m, n, r, 2)) = (n) if r = 0, (m, n, r, 3) otherwise;` `(n)` được đưa vào danh sách `Ω output` nếu `r=0`. Trái lại tiếp tực quy trình trên 
- `f((m, n, p, 3)) = (n, p, p, 1).` Khi ở bước trên `r!=0` thì ta tới bước này, tiếp theo của bước này là quay lại bước 1, và gán `n=p & m=n`. 

```
f((6, 4)) = (6, 4, 0, 1);
f((6, 4, 0, 1)) = (6, 4, 2, 2);
f((6, 4, 2, 2)) = (6, 4, 2, 3);
f((6, 4, 2, 3)) = (4, 2, 2, 1);
f((4, 2, 2, 1)) = (4, 2, 0, 2);
f((4, 2, 0, 2)) = (2);
f((2)) = (2); ~ công thức f(q)=q

```