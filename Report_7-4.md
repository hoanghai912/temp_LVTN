## Report tuần 7/4

### BigColor with Encoder T

| ![](https://raw.githubusercontent.com/hoanghai912/temporary/main/images/BigColor-modify.PNG) | 
|:--:| 
| *Mô hình BigColor tích hợp Encoder T* |

- Tuần này nhóm implement mô hình kết hợp của 2 mô hình.
- Kết quả của mô hình không được tốt:
	- Ở những epoch đầu thì mô hình vẫn có tô màu theo hình ảnh tham chiếu, kết quả đầu ra vẫn bị ảnh hưởng bởi hình ảnh tham chiếu
	- Ở epoch phía sau (> 40 epoch) thì kết quả của mô hình không còn bị ảnh hưởng bởi hình ảnh tham chiếu, kết quả ra giống nhau ở mỗi lần thử với tham chiếu khác nhau.


### Khó khăn gặp phải
- Chưa tìm ra được nguyên nhân làm mô hình không có kết quả tốt
- 
## Công  việc tuần tiếp theo
- Tìm kiếm nguyên nhân làm mô hình không tốt.
- Viết báo cáo luận văn