# Report tuần 28/4

## Công việc đã làm

- Tuần này nhóm đã thử nghiệm mô hình mới, kết quả khả thi hơn và tích cực hơn so với những mô hình trước
- Những mô hình trước, nhóm chỉ tác động vào input của bộ Generator, kết quả của mô hình không chịu sự ảnh hưởng của reference.
- Mô hình mới này thay vì sử dụng laten code z được lấy sample từ phân phối chuẩn, bọn em đã fix z theo preset_id trong quá trình train để mô hình học được giá trị z nào sẽ là của preset nào má áp dụng màu tương ứng cho phù hợp.

| ![](https://iili.io/JUO0Erv.md.png) | 
|:--:| 
| *Mô hình Test 5* |

![](https://iili.io/JUOuXmG.jpg)

- Kết quả của mô hình sau khi train thử trên tập test cho thấy được việc điều khiển z của mô hình có giúp mô hình thay đổi khả năng tổng hợp màu.
- Đây là một kết quả khả quan cho việc condition bộ Generator của mô hình BigColor. 
- Dữ liệu z bây giờ đang được nhập thủ công bằng số, nhóm sẽ hiện thực bộ estimate preset dựa trên encoder T của mô hình DeepPreset để mô hình hoàn toàn tự động tô màu dựa trên ảnh tham chiếu.

### Một số kết quả của mô hình:
- Ảnh reference chỉ là tượng trưng, thực tế reference nhận vào lúc này là một số (hay preset_id) của ảnh reference

Input | Reference |  Output
:-------------------------:|:-------------------------:|:-------------------------:
![](https://iili.io/JUO5S2I.jpg)  |  ![](https://iili.io/JUO5iQf.jpg) ![](https://iili.io/JUOuXmG.jpg) ![](https://iili.io/JUO7Yvt.jpg)| ![](https://iili.io/JUO7haS.jpg) ![](https://iili.io/JUO74cB.jpg) ![](https://iili.io/JUOYGOF.jpg)
| ![](https://iili.io/JUOc9TX.png) | ![](https://iili.io/JUO5iQf.jpg) ![](https://iili.io/JUOuXmG.jpg) ![](https://iili.io/JUO7Yvt.jpg) | ![](https://iili.io/JUOl9SV.jpg) ![](https://iili.io/JUOl5Vs.jpg) ![](https://iili.io/JUOlv5B.jpg)


## Công việc tiếp theo
- Hiện thực bộ Encoder T có khả năng estimate ra đúng preset để mô hình có thể tự động tô màu.
- Đánh giá kết quả.
- Viết báo cáo.

| ![](https://iili.io/JUOERx1.md.png) | 
|:--:| 
| *Mô hình Test 6 (dự kiến)* |