## Report tuần 21/4

### BigColor with Encoder T

- Tuần này nhóm hiện thực các mô hình để tìm ra mô hình nào phù hợp có tác dụng trong việc apply preset của ảnh tham chiếu vào trong quá trình học:

#### Mô hình test 1
| ![](https://raw.githubusercontent.com/hoanghai912/temporary/main/images/bigcolor-test-1.PNG) | 
|:--:| 
| *Mô hình Test 1* |

- Mô hình này dựa trên việc chỉ sử dụng hàm loss function để condition mạng GAN giống như AngularGAN. Nhưng mô hình này không khả thi vì ảnh reference chỉ được nhận làm tham chiếu trong quá trình training, không có tác dụng trong quá trình test.

#### Mô hình test 2

| ![](https://raw.githubusercontent.com/hoanghai912/temporary/main/images/bigcolor-test-2.PNG) | 
|:--:| 
| *Mô hình Test 2* |

- Mô hình này hiện thực các skip connection từ 2 bộ encoder sang Generator giống trong mô hình gốc của DeepPreset. Kết quả tô màu ảnh xám có sự ảnh hưởng của ảnh reference, nhưng màu sắc được tô không tốt.
- Có 2 kết quả cần chú ý: 
    - Nếu ảnh reference trong quá trình training là ảnh ground-truth, kết quả đầu ra của mô hình bị phụ thuộc rất nhiều vào ảnh tham chiếu, đổi ảnh tham chiếu khác với ảnh xám là kết quả tô màu không tốt.
    - Nếu ảnh reference trong quá trình training là ảnh ngẫu nhiên, kết quả tô màu của mô hình không tốt, ảnh đầu ra không có tác động của ảnh tham chiếu.

<center>

| ![](https://i.imgur.com/72QA87M.jpeg) | 
|:--:| 
| *Kết quả fail phổ biến cho 2 trường hợp trên* |

</center>

#### Mô hình test 3

| ![](https://raw.githubusercontent.com/hoanghai912/temporary/main/images/bigcolor-test-3.PNG) | 
|:--:| 
| *Mô hình Test 3* |

- Mô hình này sử dụng cả 2 bộ Encoder T để tăng khả năng condition mạng GAN này, nhưng kết quả của mô hình cho ra vẫn không có ảnh hưởng của ảnh tham chiếu.

## Tình hình hiện tại
- Nhóm vẫn đang tìm cách để cải tiến kết quả của mô hình.
- Nếu thời gian không còn:
    - Kết quả sau khi được mô hình BigColor generator ra sẽ được đưa qua mô hình DeepPreset (2 phase).
    - Có thể áp dụng CycleGAN vào để condition kết quả sau khi đã được generator.