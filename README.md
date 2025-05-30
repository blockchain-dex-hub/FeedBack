# Swap page
- ![image](https://github.com/user-attachments/assets/daaa4684-dcc9-4320-868e-3543365121ae)
- Setting nên hoạt động nhé, cái nào không dùng có thể comment lại nhé. Cái nào có trên UI thì nên hoạt động theo cấu hình khi swap nhé. Có thể đơn giản chỗ nào để lại cái nào quan trong thôi.
- Lần đầu load trang swap chỗ này hiển thị balance luôn. Như hình này là chọn nó mới lên nhé.
![image](https://github.com/user-attachments/assets/05e4cc7f-ef9f-40dc-88cc-d0f166320047)

- Phần thông tin Trading Stas cần hiện đúng thông số.
![image](https://github.com/user-attachments/assets/0d69cce7-043a-4aa3-863d-bdbde0263fa5)

- Chức năng thêm token trên Form swap khi người dùng muốn thêm token mới để swap. (Có thể làm đơn giản không cần làm pro như pancake phần add Custom token này). Khi thêm token mới thì người dùng có thể thêm thanh khoản và remove thanh khoản nhé.
![image](https://github.com/user-attachments/assets/1128a2b6-4028-4726-ab41-6139b51a2c26)
![image](https://github.com/user-attachments/assets/473229d6-a4ba-40b5-a39b-e43fd617e482)


- Phần thanh khoản (Có thể add và remove thanh khoản).
- Công thức tính giá AMM cho giá coin. (Như sàn dex thì giá sẽ là người đầu tiên tạo thanh khoản cho cặp coin)
Công thức tính giá trong mô hình AMM (Automated Market Maker) đơn giản nhất – chẳng hạn như được sử dụng trong Uniswap v2 – dựa trên công thức:

$$
x \cdot y = k
$$

Trong đó:

* $x$ là số lượng token A trong pool.
* $y$ là số lượng token B trong pool.
* $k$ là hằng số không đổi (constant product), đảm bảo thanh khoản trong pool.

### Cách tính giá:

Giá của một token so với token còn lại được tính bằng:

$$
\text{Giá Token A (so với B)} = \frac{y}{x}
$$

$$
\text{Giá Token B (so với A)} = \frac{x}{y}
$$

### Ví dụ:

Giả sử một pool có:

* 1000 USDT (Token A)
* 500 DAI (Token B)

Thì:

* Giá 1 USDT = 500 / 1000 = **0.5 DAI**
* Giá 1 DAI = 1000 / 500 = **2 USDT**

### Khi có giao dịch:

Khi người dùng swap, ví dụ swap 100 USDT vào pool, công thức được áp dụng lại để giữ $x \cdot y = k$, nhưng giá sẽ thay đổi do mất cân bằng tạm thời. Đó chính là "slippage".

### Công thức tính lượng token nhận được (chưa bao gồm phí):

$$
\Delta y = \frac{y \cdot \Delta x}{x + \Delta x}
$$

Trong đó:

* $\Delta x$: lượng token A bạn muốn swap vào
* $\Delta y$: lượng token B bạn sẽ nhận

Nếu tính phí (ví dụ 0.3% như Uniswap v2), thì:

$$
\Delta y = \frac{y \cdot (\Delta x \cdot (1 - fee))}{x + (\Delta x \cdot (1 - fee))}
$$

Ví dụ với phí 0.3%, thì fee = 0.003.

---






