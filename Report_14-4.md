## Report tuần 14/4

### BigColor with Encoder T

- Nhóm vẽ lại mô hình để làm rõ hơn dữ liệu đầu vào của Discriminator

| ![](https://raw.githubusercontent.com/hoanghai912/temporary/main/images/BigColor-modify%20-%202.PNG) | 
|:--:| 
| *Mô hình BigColor tích hợp Encoder T* |

**Epoch 50**

Input | Reference |  Output
:-------------------------:|:-------------------------:|:-------------------------:
![](https://iili.io/JvUp7fa.png) ![](https://iili.io/JvgHkeR.png) ![](https://iili.io/JvgHmL7.png)   |  ![](https://github.com/hoanghai912/temporary/blob/main/images/result_image_1/ref3.jpg?raw=true) | ![](https://github.com/hoanghai912/temporary/blob/main/images/result_image_1/res_ref3/00000.jpg?raw=true) ![](https://github.com/hoanghai912/temporary/blob/main/images/result_image_1/res_ref3/00003.jpg?raw=true) ![](https://github.com/hoanghai912/temporary/blob/main/images/result_image_1/res_ref3/00004.jpg?raw=true)
| ![](https://iili.io/JvUp7fa.png) ![](https://iili.io/JvgHkeR.png) ![](https://iili.io/JvgHmL7.png) | ![](https://github.com/hoanghai912/temporary/blob/main/images/result_image_1/ref5.jpg?raw=true) | ![](https://github.com/hoanghai912/temporary/blob/main/images/result_image_1/res_ref5/00000.jpg?raw=true) ![](https://github.com/hoanghai912/temporary/blob/main/images/result_image_1/res_ref5/00003.jpg?raw=true) ![](https://github.com/hoanghai912/temporary/blob/main/images/result_image_1/res_ref5/00004.jpg?raw=true)

- Ở epoch phía sau (> 40 epoch) thì kết quả của mô hình không còn bị ảnh hưởng bởi hình ảnh tham chiếu, kết quả ra giống nhau ở mỗi lần thử với tham chiếu khác nhau.

## Công  việc tuần tiếp theo
- Tìm kiếm nguyên nhân làm mô hình không tốt.
- Cải tiến mô hình hiện tại bằng cách hiện thực các skip connection giữa encoder với generator
- Viết báo cáo luận văn