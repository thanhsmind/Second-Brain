# Defining an Algorithm
#Knuth, #TheArtofComputerProgramming #taocp 

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
Bài 4 chương 1
```
f((6099, 2166)) = (6099, 2166, 0, 1);
f((6099, 2166, 0, 1)) = (6099, 2166, 1767, 2);
f((6099, 2166, 1767, 2)) = (6099, 2166, 1767, 3);
f((6099, 2166, 1767, 3)) = (2166, 1767, 1767, 1);
f((2166, 1767, 1767, 1)) = (2166, 1767, 399, 2);
f((2166, 1767, 399, 2)) = (2166, 1767, 399, 3);
f((2166, 1767, 399, 3)) = (1767, 399, 399, 1);
f((1767, 399, 399, 1)) = (1767, 399, 171, 2);
f((1767, 399, 171, 2)) = (1767, 399, 171, 3);
f((1767, 399, 171, 3)) = (399, 171, 171, 1);
f((399, 171, 171, 1)) = (399, 171, 57, 2);
f((399, 171, 57, 2)) = (399, 171, 57, 3);
f((399, 171, 57, 3)) = (171, 57, 57, 1);
f((171, 57, 57, 1)) = (171, 57, 0, 2);

f((171, 57, 0, 2)) = (57);
f((57)) = (57); ~ công thức f(q)=q
```

> If we wish to restrict the notion of algorithm so that only elementary operations are involved, we can place restric1tions on `Q, I, Ω` and `f`, for example as follows: Let `A` be a finite set of letters, and let `A*` be the set of all strings on `A` (the set of all ordered sequences `x1x2...xn`, where `n ≥ 0` and `xj` is in `A` for `1 ≤ j ≤ n`).

Với `A` là 1 tập hữu hạn các letter. `A*` là 1 tập tương ứng chứa các *combinations of letter*. `xj is in A for 1 ≤ j ≤ n` có nghĩ là với bất kỳ letter(`xj`) trong `A*` thì có tương ứng trong tập `A`.

> The idea is to encode the states of the computation so that they are represented by strings of `A*`.

Mỗi string của letter trong `A*` thể hiện 1 states trong `Q`, và mỗi tính toán ( `I` input, `Ω` output, và các bước trung gian) đều được lưu trong tập `A*`. 

> Now let `N` be a nonnegative integer and let `Q` be the set of all `(σ,j)`, where `σ` is in `A*` and `j` is an integer, `0 ≤ j ≤ N;` let `I` be the subset of `Q` with `j = 0` and let `Ω` be the subset with `j = N`.

- `Q`:  là 1 tập hợp chứa các cặp  `(σ,j)`
- `σ`: là 1 string trong tập `A*` 
- `j`: là 1 step(hay state) trong thuật toán
	- `j=0` là bước đầu tiên của thuật toán, nó là đầu vào `I`
	- `j=N` là bước cuối cùng của thuật toán, là đầu ra của thuật toán `Ω`

Mục (3) Basic Concepts có nhắc tới thuật toán Markov
***Markov algorithm*** là thuật toán dùng để chuyển 1 chuỗi các ký tự thành 1 chuỗi các ký tự khác dựa vào 1 danh sách các rules có ***thứ tự***. Mỗi luật dùng cụ thể 1 chuỗi thay thế bằng 1 chuỗi khác. Quy trình sẽ đi từ chuỗi đầu tiên cho tới cuối cùng. Khi gặp chuỗi cần thay thế thì thay thành chuỗi mới luôn. Nếu không gặp thì tiếp tục thực hiện tiếp rule tiếp theo cho tới cuối cùng là kết thúc quá trình. 
Ví dụ : 
```
1 - "u" -> "do"
2 - "p" -> "wn"
3 - "up" -> "error"
```
Giả sử, ta đưa vào 1 chuỗi cần chuyển đổi là `up`. quy trình sẽ là
```
1 - "up" => input
2 - "dop" => thay thế "u" bằng "do" ra 1 chuỗi mới
3 - "down" => gặp "p" có trong danh sách nên thay thế bằng "wn"
```


> If `θ` and `σ` are strings in `A*`, we say that `θ` occurs in `σ` if it has the form `αθω` for strings `α` and `ω`.

Định nghĩa thế nào là 1 string nằm bên trong 1 string khác. `θ`, `σ` là string nằm bên trong tập A*. `θ` được gọi là nằm trong string `σ` nếu nó có dạng  `αθω`. Cụ thể như ví dụ phía trên khi ta đưa 1 chuỗi `up` vào thì `θ=u` vì `u` có mặt trong bộ chuyển đổi. `α là 1 chuỗi empty ""` do trước `u` không có chuỗi nào.  `ω=p`.

> To complete our definition, let f be a function of the following type, defined by the strings `θj`, `φj` and the integers `aj, bj for 0 ≤ j ≤ N`:
`f((σ,j)) = (σ,aj)`     if θj does not occur in σ
`f((σ,j)) = (αφjω,bj)`     if α is the shortest string for which σ = αθjω
`f((σ,N)) = (σ,N)`

Áp dụng vào để thể hiện lời giải bài toán ***Markov algorithm***
`j` là number of the step we are performing. 
`θ&φ tương ứng mỗi step là  (θj & φj)`
`a` là luật nào đang được ứng dụng
`b` tương ứng với step nào tiếp tới, step cuối cùng `b=N`
3 bước  phía trên là thể hiện những luật của ***Markov algorithm***. 

```
j - 	θ	    φ	       a	b
0 - 	"u"	    "do"	   2	1
1 - 	"p"	    "wn"	   2	3
2 - 	"*"	    "error"	   3	3
```

Bắt đầu với chuỗi "up" cần được xử lý. Khi đưa "up" vào thuật toán 
1. `f((σ,j)) ~ f(("up", 0)) σ="up", j=0 `. 
2.  Ta thấy RULE 1 không thỏa mãn do   `σ ("up")` does contain `θ0 ("u")`. nên chuyển tới RULE 2
3. RULE 2  `f((σ,j)) = (αφjω,bj) ` được áp dụng với `θ0 là "u"`, `ω là "p".` `α là empty string (do trước u không có chuỗi nào hết`.`a0=2` do RULE 2 được sử dụng. `b0=1` thể hiện bước tiếp theo là 1. `"u" được thay thế bới "do"
4. `f((σ,j)) ~ f(("dop", 1)) σ="dop", j=1 `. 
5.  Ta thấy RULE 1 không thỏa mãn do   `σ ("dop")` does contain `θ1 ("p")`. nên chuyển tới RULE 2
6.  RULE 2  `f((σ,j)) = (αφjω,bj) ` được áp dụng với `θ1 là "p"`, `ω là "".` `α là "do"`. `a1=2` do RULE 2 được sử dụng `b1=3` thể hiện bước tiếp theo là 3. `"u" được thay thế bới "do"
7.  Kết quả `f((σ,N)) = (σ,N) = f(("down", 3))`

[[taocp-exercises-basic-concepts]]: TAOCP Exercises Basic concept