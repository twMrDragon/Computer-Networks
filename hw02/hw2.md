# 計算機網路 hw2

## 資工三 111590012 林品緯

### 1.

Ans:<br>
UDP，因為 UDP 比 TCP 少了連線時間和流量控制。

### 2.

Ans<br>
Web cache 和 clinet 會在同一個 LAN， LAN 的頻寬會比 access link 的頻寬大，並且 Web cache 和 server 比起來距離 client 更近，這樣可以在更少的時間下獲得請求的物件。並且如果請求的物件在 cache 有，那就不用使用 access link 的頻寬，減少 access link 使用的機率，降低請求一個物件的平均延遲。

### 3.

Ans<br>
因為 HTTP、FTP、SMTP 和 POP3 需要確保資料完整，而 TCP 提供可靠的資料傳輸。

### 4.

使用 DNS 找到目標 IP:

$$
\sum_{i=1}^{i}\text{RTT}_{i}
$$

初始化 TCP 連線:

$$
\text{RTT}_0
$$

request 和 receive 物件

$$
\text{RTT}_0
$$

總共:

$$
\sum_{i=1}^{i}\text{RTT}_{i}+2\times\text{RTT}_0
$$

Ans:<br>
$\sum_{i=1}^{i}\text{RTT}_{i}+2\times\text{RTT}_0$

### 5.

#### (a)

| 動作                     | 時間                  |
| ------------------------ | --------------------- |
| 初始化 HTML 的 TCP 連線  | $\text{RTT}_0$        |
| 請求和接收 HTML          | $\text{RTT}_0$        |
| 平行初始化 3 個 TCP 連線 | $\text{RTT}_0$        |
| 平行請求和接收 3 個物件  | $\text{RTT}_0$        |
| 總共                     | $4\times\text{RTT}_0$ |

Ans:<br>
$4\times\text{RTT}_0$

#### (b)

| 動作                     | 時間                  |
| ------------------------ | --------------------- |
| 初始化 HTML 的 TCP 連線  | $\text{RTT}_0$        |
| 請求和接收 HTML          | $\text{RTT}_0$        |
| 初始化物件 1 的 TCP 連線 | $\text{RTT}_0$        |
| 請求和接收 物件 1        | $\text{RTT}_0$        |
| 初始化物件 2 的 TCP 連線 | $\text{RTT}_0$        |
| 請求和接收 物件 2        | $\text{RTT}_0$        |
| 初始化物件 3 的 TCP 連線 | $\text{RTT}_0$        |
| 請求和接收 物件 3        | $\text{RTT}_0$        |
| 總共                     | $8\times\text{RTT}_0$ |

Ans:<br>
$8\times\text{RTT}_0$

#### (c)

| 動作                    | 時間                  |
| ----------------------- | --------------------- |
| 初始化 HTML 的 TCP 連線 | $\text{RTT}_0$        |
| 請求和接收 HTML         | $\text{RTT}_0$        |
| 連續請求和接收 3 個物件 | $\text{RTT}_0$        |
| 總共                    | $3\times\text{RTT}_0$ |

Ans:<br>
$3\times\text{RTT}_0$
