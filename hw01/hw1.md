# 計算機網路 hw1

## 資工三 111590012 林品緯

### 1.

#### (a)

min $\{R_1, R_2, R_3\} = $ 500 kbps

Ans:<br>
500 kbps

#### (b)

min $\{R_1, R_2, R_3\} = $ 200 kbps

Ans:<br>
200 kbps

### 2.

#### (a)

$$
\begin{aligned}
    \frac{2\text{ Mbps}}{ 100\text{ kbps}} = 20
\end{aligned}
$$

Ans:<br>
20 users

#### (b)

Ans:<br>
20%

#### (c)

Ans:<br>

$$
\begin{aligned}
    P = \binom{40}{n}0.2^n \times 0.8^{(40-n)}
\end{aligned}
$$

#### (d)

Ans:<br>

$$
\begin{aligned}
    P = \sum^{40}_{n=21}\binom{40}{n}0.2^n \times 0.8^{(40-n)}
\end{aligned}
$$

### 3.

每秒平均會有 $\frac{R}{L}$ 個 packets 抵達 buffer:

$$
\begin{aligned}
    \frac{N}{\frac{LN}{R}}=\frac{R}{L}
\end{aligned}
$$

traffic intensity:

$$
\begin{aligned}
    L\times\frac{R}{L}\times\frac{1}{R} = 1
\end{aligned}
$$

average queuing delay:

$$
\begin{aligned}
    \frac{\sum^{N-1}_{i=0}i\times\frac{L}{R}}{N} &= \frac{N\times(N-1)}{2\times N}\times\frac{L}{R} \\
    &=\frac{(N-1)}{2}\times\frac{L}{R}
\end{aligned}
$$

Ans:

$\frac{(N-1)\times L}{2\times R}$

### 4.

total end-to-end delay:

$$
\begin{aligned}
    \frac{L}{R_1}+\frac{d_1}{s_1}+d_{\text{proc}}+\frac{L}{R_2}+\frac{d_2}{s_2}
\end{aligned}
$$

| variable          | vaule             |
| ----------------- | ----------------- |
| L                 | 1000bytes         |
| $R_1$, $R_2$      | 2 Mbps            |
| $d_1$             | 4000 km           |
| $d_2$             | 1000 km           |
| $s_1$, $s_2$      | $2\times10^8$ m/s |
| $d_{\text{proc}}$ | 1 msec            |

$$
\begin{aligned}
    \frac{L}{R_1}+\frac{d_1}{s_1}+d_{\text{proc}}+\frac{L}{R_2}+\frac{d_2}{s_2} &= \frac{1000\times8}{2\times 10^6}+\frac{4000\times 10^3}{2\times10^8}+10^{-3}+\frac{1000\times8}{2\times 10^6}+\frac{1000\times 10^3}{2\times10^8} \\
    &=4\times10^{-3}+2\times10^{-2}+10^{-3}+4\times10^{-3}+5\times10^{-3} \\
    &=(4+20+1+4+5)\times10^{-3} \\
    &=34\times10^{-3} \\
\end{aligned}
$$

Ans:<br>

$\frac{L}{R_1}+\frac{d_1}{s_1}+d_{\text{proc}}+\frac{L}{R_2}+\frac{d_2}{s_2}$

34 msec

### 5.

Ans:<br>

| Layer       | principal responsibilities   |
| ----------- | ---------------------------- |
| Application | 網路應用和通訊協定運作的地方 |
| Transport   | 在應用之間傳遞應用層 message |
| Network     | 把 datagrams 送到目的地      |
| Link        | 把 packet 傳遞到下一個節點   |
| Physical    | 把 bits 移動到下一個節點     |
