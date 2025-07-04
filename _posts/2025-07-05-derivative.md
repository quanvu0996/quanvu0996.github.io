---
title: 'Đạo hàm theo ngôn ngữ ma trận'
date: 2025-07-05
permalink: /posts/vi/2025/07/matrix_derivative/
tags:
  - Derivative
  - Matrix
  - Vietnamese
---
# Đạo hàm trong ngôn ngữ ma trận
Đạo hàm được ứng dụng rộng rãi trong các bài toán tối ưu. Nó cho biến hướng thay đổi của hàm trong không gian biến. Trong trường hợp của không gian nhiều biến, ngôn ngữ ma trận thường được sử dụng. Các phép toán đạo hàm cũng có một số khác biệt.

Hãy xét một hàm số $y=f(x)$ nhận vào một vector $n$ chiều $(x_1, x_2,...,x_n)$ để tính một giá trị $y$. <br>
Ta viết dạng toán học là $f(x): \mathbb{R}^{m \times n} \rightarrow \mathbb{R}^m$
## Đạo hàm bậc 1
Một vector gradient của $f(x)$ là một vector cột gồm tất cả các giá trị đạo hàm riêng của $f$ theo từng $x$: <br>
$$
    J = \nabla f(x) = 
        \begin{bmatrix}
            \frac{\partial f}{\partial x_1} \\
            \frac{\partial f}{\partial x_2} \\
            ... \\
            \frac{\partial f}{\partial x_n} \\
        \end{bmatrix}
$$

Đây là dạng đơn giản của ma trận Jacobi (Jacobian matrix).<br>
Ví dụ. xét hàm số $y = f(x_1, x_2) = \begin{bmatrix} 5 & 4 \end{bmatrix} \times \begin{bmatrix} x_1 \\ x_2 \end{bmatrix} = 5x_1+4x_2$

$\frac{\partial f(x)}{\partial x_1} = 5$;
$\frac{\partial f(x)}{\partial x_2} = 4$ <br>
<br>
$\Rightarrow \nabla f(x) = \begin{bmatrix} 5 \\ 4 \end{bmatrix}$

Điều này có nghĩa là: tại một điểm $(x_{01}, x_{02})$, nếu ta giữ nguyên $x_2$ và dịch $x_1$ đi một đoạn nhỏ $\Delta x_{1}$, thì giá trị hàm $f(x)$ sẽ biến động tăng thêm 1 lượng gấp $5$ lần $\Delta x_{1}$. Và nếu giữ nguyên $x_1$, dịch $x_2$ đi một đoạn nhỏ $\Delta x_2$ thì giá trị hàm $f(x)$ sẽ tăng thêm một lượng gấp $4$ lần $\Delta x_2$.

Trong các bài toán tối ưu, việc biết được hướng tăng/giảm và độ dốc của hàm tại từng điểm sẽ giúp lựa chọn bước đi tối ưu để tối thiểu hoặc tối đa hóa giá trị hàm.

## Đạo hàm bậc 2
Ta cũng cần quan tâm đến đạo hàm bậc 2. Thường được dùng để xác định tính lồi của hàm số hoặc trạng thái cực trị là cực đại hay cực tiểu. <br>
Ý tưởng cũng như đạo hàm bậc 1, ta cũng xét các đạo hàm riêng của của đạo hàm bậc 1 theo từng biến. Chỉ khác là hiện giờ có $n$ biểu thức. Các kết quả thu được ta ghi vào một ma trận, được gọi là ma trận Hessian:

$$
    H = \nabla^2 f(x) = 
        \begin{bmatrix}
            \frac{\partial^2 f}{\partial^2 x_1} & \frac{\partial^2 f}{\partial x_1 \partial x_2} &... & \frac{\partial^2 f}{\partial x_1 \partial x_n}\\ 
            \frac{\partial^2 f}{\partial x_2 \partial x_1} & \frac{\partial^2 f}{\partial^2 x_2} & ... & \frac{\partial^2 f}{\partial x_2 \partial x_n} \\
            ... & ... & ... & ... \\
            \frac{\partial^2 f}{\partial x_n \partial x_1}  & \frac{\partial^2 f}{\partial x_n \partial x_2} &... & \frac{\partial^2 f}{\partial^2 x_n} \\
        \end{bmatrix}
$$

Các giá trị trong ma trận Hessian cho biết gia tốc theo các hướng của hàm $f(x)$ như thế nào.

Hãy xét một ví dụ: $y=f(x_1, x_2) = 2x_1^2 + 3x_1x_2+5x_2^2 +10$ <br>
Vector Gradient: 
$\nabla f(x) = \begin{bmatrix} 4x_1 +3x_2 \\ 3x_1+10x_2 \end{bmatrix}$

Ma trận Hessian:

$\nabla^2 f(x) = \begin{bmatrix} 4 & 3 \\ 3 & 10 \end{bmatrix}$

## Đạo hàm trên ngôn ngữ ma trận
Giờ hãy xét các hàm trên ngôn ngữ ma trận:

Với $x \in \mathbb{R}^n, c \in \mathbb{R}^n, A \in \mathbb{R}^{m \times n}$

(1) $f(x) = c \Rightarrow \nabla f(x) =0 ; \nabla^2 f(x) = 0 $ 

(2) $f(x) = cx \Rightarrow \nabla f(x) = c; \nabla^2 f(x) = 0 $ 

(3) $f(x) = Ax \Rightarrow \nabla f(x) = A; \nabla^2 f(x) = 0 $ 

(4) $f(x) = x^TAx \Rightarrow \nabla f(x) = (A+A^T)x; \nabla^2 f(x) = A+A^T $ 

** Chứng minh (4): <br>
Ta có:
$f(x) = x^TAx = \sum_{i=1}^n \sum_{j=1}^n x_iA_{ij}x_j$

Lấy đạo hàm riêng phần:

$$ \frac{\partial f}{\partial x_k} = \sum_{k}^n{2A_{kk}x_k} + \sum_{j=1, j \neq k}^n {A_{kj}x_j} + \sum_{i=1, i \neq k}^n {A_{ik}x_i} = \sum_{j=1}^n {A_{kj}x_j} + \sum_{i=1}^n {A_{ik}x_i} = (Ax)_k + (A^Tx)_k$$

($(Ax)_k$ hiểu là hàng thứ k của ma trận $Ax$)

$$\Rightarrow \nabla f(x) = (A+A^T)x $$

Q.E.D $\square$

**Ví dụ** <br>
Hãy xét ví dụ sau: $f(x) = \parallel Ax-b \parallel ^2_2$ <br>

Ta thấy: 
$$ f(x) = (Ax-b)^T(Ax-b) = (x^TA^T-b^T)(Ax-b) = x^TA^TAx - 2b^TAx +b^Tb $$ 

Đạo hàm bậc 1:
$$ \nabla f(x) = (A^TA + (A^TA)^T)x - 2b^TA = 2A^TAx - 2b^TA $$

Đạo hàm bậc 2: 
$$ \nabla ^2 f(x) = 2A^TA$$