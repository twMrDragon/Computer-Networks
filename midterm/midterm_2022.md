# 計算機網路 midterm 2022

## 資工三 111590012 林品緯

### 1.

| features                  | Circuit | Packet   |
| ------------------------- | ------- | -------- |
| connection setup/teardown | 需要    | 不用     |
| bandwidth reservation     | 需要    | 不用     |
| routing path selection    | 有特定  | 沒有特定 |
| queueing delay            | 沒有    | 有       |
| channel efficiency        | 效率差  | 效率低   |

### 2.

| layer       | responsibilities                            |
| ----------- | ------------------------------------------- |
| application | 提供網路應用程式服務和介面                  |
| transport   | 資料從來源 process 傳送到目標 process       |
| network     | 資料從來源 end system 傳送到目標 end system |
| link        | 資料送到相鄰的節點                          |
| physical    | bit 的傳輸                                  |

### 3.

| action                                             | protocal |
| -------------------------------------------------- | -------- |
| Alice 使用 web 發送郵件                            | HTTP     |
| Alice 的 mail server 傳送郵件給 Bob 的 mail server | SMTP     |
| Bob 訪問郵件                                       | POP3     |

### 4.

$$
\begin{aligned}
T_{d_1} &= \frac{6\times10^5}{2\times10^8}=3\times10^{-3} \\
T_{d_2} &= \frac{2\times10^5}{2\times10^8}=1\times10^{-3} \\
T_{d_3} &= \frac{4\times10^5}{2\times10^8}=2\times10^{-3} \\
\\
T_{R_1} &= \frac{2\times10^3}{1\times10^6}=2\times10^{-3} \\
T_{R_2} &= \frac{2\times10^3}{2\times10^6}=1\times10^{-3} \\
T_{R_3} &= \frac{2\times10^3}{5\times10^5}=4\times10^{-3} \\
\\
d_{\text{proc}} &= 1\times10^{-3} \\
\end{aligned}
$$

$$
total=
\begin{aligned}
(3+1+2+2+1+4+1+1)\times10^{-3}=15\times10^{-3}
\end{aligned}
$$

### 5.

#### (a)

| 動作                     | 時間                                                                      |
| ------------------------ | ------------------------------------------------------------------------- |
| DNS 查詢                 | $\text{RTT}_1+\text{RTT}_2+\text{RTT}_3+\text{RTT}_4$                     |
| 初始化 HTML 的 TCP 連線  | $\text{RTT}_0$                                                            |
| 請求和接收 HTML          | $\text{RTT}_0$                                                            |
| 平行初始化 5 個 TCP 連線 | $\text{RTT}_0$                                                            |
| 平行請求和接收 5 個物件  | $\text{RTT}_0$                                                            |
| 總共                     | $4\times\text{RTT}_0+\text{RTT}_1+\text{RTT}_2+\text{RTT}_3+\text{RTT}_4$ |

#### (b)

| 動作                     | 時間                                                                       |
| ------------------------ | -------------------------------------------------------------------------- |
| DNS 查詢                 | $\text{RTT}_1+\text{RTT}_2+\text{RTT}_3+\text{RTT}_4$                      |
| 初始化 HTML 的 TCP 連線  | $\text{RTT}_0$                                                             |
| 請求和接收 HTML          | $\text{RTT}_0$                                                             |
| 初始化物件 1 的 TCP 連線 | $\text{RTT}_0$                                                             |
| 請求和接收 物件 1        | $\text{RTT}_0$                                                             |
| 初始化物件 2 的 TCP 連線 | $\text{RTT}_0$                                                             |
| 請求和接收 物件 2        | $\text{RTT}_0$                                                             |
| 初始化物件 3 的 TCP 連線 | $\text{RTT}_0$                                                             |
| 請求和接收 物件 3        | $\text{RTT}_0$                                                             |
| 初始化物件 4 的 TCP 連線 | $\text{RTT}_0$                                                             |
| 請求和接收 物件 4        | $\text{RTT}_0$                                                             |
| 初始化物件 5 的 TCP 連線 | $\text{RTT}_0$                                                             |
| 請求和接收 物件 5        | $\text{RTT}_0$                                                             |
| 總共                     | $12\times\text{RTT}_0+\text{RTT}_1+\text{RTT}_2+\text{RTT}_3+\text{RTT}_4$ |

#### (c)

| 動作                    | 時間                                                                      |
| ----------------------- | ------------------------------------------------------------------------- |
| DNS 查詢                | $\text{RTT}_1+\text{RTT}_2+\text{RTT}_3+\text{RTT}_4$                     |
| 初始化 HTML 的 TCP 連線 | $\text{RTT}_0$                                                            |
| 請求和接收 HTML         | $\text{RTT}_0$                                                            |
| 連續請求和接收 5 個物件 | $\text{RTT}_0$                                                            |
| 總共                    | $3\times\text{RTT}_0+\text{RTT}_1+\text{RTT}_2+\text{RTT}_3+\text{RTT}_4$ |

### 6.

#### (a)

最後一個 segment 會在下面 delay 開始傳送:

$$
\begin{aligned}
(\frac{F}{S}-1)\times\frac{S+H}{R}
\end{aligned}
$$

經過兩次推到線上:

$$
\begin{aligned}
2\times\frac{S+H}{R}
\end{aligned}
$$

總共:

$$
\begin{aligned}
(\frac{F}{S}-1)\times\frac{S+H}{R}+2\times\frac{S+H}{R} =(\frac{F}{S}+1)\times\frac{S+H}{R}
\end{aligned}
$$

#### (b)

$$
\begin{aligned}
(\frac{F}{S}+1)\times\frac{S+H}{R}\frac{\mathrm{d}}{\mathrm{dS}} &=\frac{FS}{SR}+\frac{FH}{SR}+\frac{S}{R}+\frac{H}{R}\frac{\mathrm{d}}{\mathrm{dS}} \\
&=\frac{1}{R}-\frac{FH}{S^2R} \\
&=\frac{S^2-FH}{S^2R}
\end{aligned}
$$

$$
\begin{aligned}
S=\sqrt{FH}
\end{aligned}
$$
