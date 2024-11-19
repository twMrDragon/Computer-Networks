# 計算機網路 hw3

## 資工三 111590012 林品緯

### 1.

Ans:<br>
否。host A 和 host B 在和 host C 連線後會使用不同的 socket 來傳送資料。

Ans:<br>
是。因為 host A 和 host B 的 source IP 或 source port 不同，所以 TCP 可以在使用相同 port 80 的情況下對應的不同的 socket。

### 2.

#### (a)

因為 receiver 沒有收到 90，receiver 下一個期望收到的是 90，所以會是 ACK 90。

Ans:<br>
90

#### (b)

$110-90=20$

Ans:<br>
20 bytes

### 3.

因為 receiver 期待的是 k，代表 k 因為還未發送或是 NAK，所以在 window 內。又因為 window size 為 3，所以 window 內包含 $k \mod 1024$，$(k+1)\mod 1024$，$(k+2)\mod 1024$。

Ans:<br>
$k \mod 1024$，$(k+1)\mod 1024$，$(k+2)\mod 1024$

### 4.

host B 會把 rwnd 告訴 host A 達成流量控制。
當 host B 的 rwnd 快沒空間時，host A 會降低傳送的資料量直到 host B 的 rwnd 有更多空間。避免 host B 的 receiver buffer 有 overflow 的可能。

### 5.

重新傳送的 SampleRTT 表示可能有資料丟失或是 timeout 發生，代表網路可能有一些問題，這樣的 SampleRTT 不能反映的出正常情況下的網路延遲。
