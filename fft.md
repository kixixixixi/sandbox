# FFT
2022-10-18

---

## DFT

$$X(k) = \sum_{n=1}^{N-1} x(n) e^{-j\frac{2\pi}{N}kn}$$

サンプリング周期Dで4Dまで測定した場合

$$X(n) = x_0 + x_1 e^{-j\frac{2\pi}{4D}n} + x_2 e^{-j\frac{2\pi}{4D}2n} + x_3 e^{-j\frac{2\pi}{4D}3n}$$

$$
\begin{eqnarray}
X(0) &=& x_0 + x_1 + x_2 + x_3 \\
X(D) &=& x_0 + x_1 e^{-j\frac{2\pi}{4}} + x_2 e^{-j\frac{4\pi}{4}} + x_3 e^{-j\frac{6\pi}{4}} \\
X(2D) &=& x_0 + x_1 e^{-j\frac{4\pi}{4}} + x_2 e^{-j\frac{8\pi}{4}} + x_3 e^{-j\frac{12\pi}{4}} \\
X(3D) &=& x_0 + x_1 e^{-j\frac{6\pi}{4}} + x_2 e^{-j\frac{12\pi}{4}} + x_3 e^{-j\frac{18\pi}{4}}
\end{eqnarray}
$$

$$
\begin{eqnarray}
\begin{pmatrix}
X_0 \\
X_1 \\
X_2 \\
X_3
\end{pmatrix}
&=&
\begin{pmatrix}
1 & 1 & 1 & 1 \\
1 & e^{-j\frac{2\pi}{4}} & e^{-j\frac{4\pi}{4}} & e^{-j\frac{6\pi}{4}} \\
1 & e^{-j\frac{4\pi}{4}} & e^{-j\frac{8\pi}{4}} & e^{-j\frac{12\pi}{4}} \\
1 & e^{-j\frac{6\pi}{4}} & e^{-j\frac{12\pi}{4}} & e^{-j\frac{18\pi}{4}} \\
\end{pmatrix}
\begin{pmatrix}
x_0 \\
x_1 \\
x_2 \\
x_3
\end{pmatrix} \\
&=&
\begin{pmatrix}
1 & 1 & 1 & 1 \\
1 & W & W^2 & W^3 \\
1 & W^2 & W^4 & W^6 \\
1 & W^3 & W^6 & W^9 \\
\end{pmatrix}
\begin{pmatrix}
x_0 \\
x_1 \\
x_2 \\
x_3
\end{pmatrix}
\end{eqnarray}
$$

---

## 演習問題
### 7.1

### 7.2
1. 入力が周期の整数場合になるとはかぎらない
2. サンプリング周期が周期の周期の2倍以上である必要がある
### 7.3
0埋めもしくは最初と最後の入力を削る
