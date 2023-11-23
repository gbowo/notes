# 一级标题
## 二级标题
### 三级标题

---
**重点加粗**
__粗体__
*斜体*
~~删除线~~
==高亮==
**ctrl b**
*ctrl i*

- 无序列表 1
- 无序列表 2
  - 无序列表 2a
  - 无序列表 2b

1. 有序列表
2. 有序列表
1. 有序列表 3
  1.有序列表 3a
  2.有序列表 3b

任务列表：


- [ ] 已经完成的事 1
- [ ] 已经完成的事 2
- [ ] 仍未完成的事 3
   
引用文本：

>引用别人的话
>就这么写
>By.User

 这是行内代码的写法：


代码块语法：
``` python
print("hello world!")
```

代码行数的表示:

``` javascript {.line-numbers}
function Add(x,y){
    return x+y;
}
```


[偶像大师闪耀色彩](https://shinycolors.enza.fun/tutorial)

![浅仓透](https://moegirl.icu/media/thumb/SC_P_Asakura_Toru_SSR01%2B.jpg/426px-SC_P_Asakura_Toru_SSR01%2B.jpg)


屏幕截图测试：


![](images/2023-11-23-19-59-38.png)


表格：


| 表头 | 表头 | 表头 |
| ---- | ---- | ---- |
| 内容 | 内容 | 内容 |

*shift+alt+f自动对齐*


注释：

<!-- 看不见
看不见
看不见 -->


行内公式：


单位圆：$x^2+y^2 = 1$


公式块：


$$
\begin{cases}
x =\rho\cos\theta \\
y =\rho\sin\theta \\
\end{cases}
$$

下标


$x_1+x_2 = 0$


较小的行内行分数：$\frac{1}{2}$


展示型分数：$\displaystyle\frac{1}{2}$


紧贴 $a\!b$

没有空格 $ab$

小空格 $a\,b$

中空格 $a\;b$

大空格 $a\quad b$


累加 $\sum_{k=1}^n\frac{1}{k}  \quad  \displaystyle\sum_{k=1}^n\frac{1}{k}$

累乘 $\prod_{k=1}^n\frac{1}{k}  \quad  \displaystyle\prod_{k=1}^n\frac{1}{k}$

积分 $\displaystyle \int_0^1x{\rm d}x  \quad  \iint_{D_{xy}}  \quad  \iiint_{\Omega_{xyz}}$


圆括号 $\displaystyle \left(\sum_{k=1}^{n}\frac{1}{k} \right)^2$

方括号 $\displaystyle \left[\sum_{k=1}^{n}\frac{1}{k} \right]^2$

花括号 $\displaystyle \left\{\sum_{k=1}^{n}\frac{1}{k} \right\}^2$

尖括号 $\displaystyle \left\langle\sum_{k=1}^{n}\frac{1}{k} \right\rangle^2$


居中:

$$
\begin{aligned}
y &=(x+5)^2-(x+1)^2 \\
&=(x^2+10x+25)-(x^2+2x+1) \\
&=8x+24 \\
\end{aligned}
$$

左对齐:

$
\begin{aligned}
y &=(x+5)^2-(x+1)^2 \\
&=(x^2+10x+25)-(x^2+2x+1) \\
&=8x+24 \\
\end{aligned}
$


方程组
$$
\begin{cases}
k_{11}x_1+k_{12}x_2+\cdots+k_{1n}x_n=b_1 \\
k_{21}x_1+k_{22}x_2+\cdots+k_{2n}x_n=b_2 \\
\cdots \\
k_{n1}x_1+k_{n2}x_2+\cdots+k_{nn}x_n=b_n \\
\end{cases}
$$


矩阵:

$$
\begin{pmatrix}
1 & 1 & \cdots & 1 \\
1 & 1 & \cdots & 1 \\
\vdots & \vdots & \ddots & \vdots \\
1 & 1 & \cdots & 1 \\
\end{pmatrix}
$$

$$
\begin{bmatrix}
1 & 1 & \cdots & 1 \\
1 & 1 & \cdots & 1 \\
\vdots & \vdots & \ddots & \vdots \\
1 & 1 & \cdots & 1 \\
\end{bmatrix}
$$ 

行列式: 

$$
\begin{vmatrix}
1 & 1 & \cdots & 1 \\
1 & 1 & \cdots & 1 \\
\vdots & \vdots & \ddots & \vdots \\
1 & 1 & \cdots & 1 \\
\end{vmatrix}
$$


公式编号与引用：


$$
x+2 \tag{1.2}
$$

$$
\begin{equation}
x^n+y^n=z^n
\end{equation}
$$

由公式 $(1.2)$ 可得到结论