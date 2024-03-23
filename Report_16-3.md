- Sau khi đọc kỹ lại paper [*DeepHist: Differentiable Joint and Color Histogram Layers for Image-to-Image Translation*](https://arxiv.org/abs/2005.03995) bọn em quyết định không chọn hướng đi theo histogram để control màu cho ảnh đầu ra nữa. Do màu của ảnh output phụ thuộc nhiều vào ảnh đầu ra, cũng không có đủ dataset để train mapping theo màu của ảnh tham chiếu.

- Ý tưởng của bọn em sẽ là để mô hình tổng hợp màu và cùng lúc đó sẽ control color tone của ảnh (như vintage, retro, ...)

- Vì vậy bọn em có ý tưởng sẽ sử dụng Preset màu để control màu của ảnh đó theo color tone của ảnh reference. 

### Paper tham khảo ý tưởng
- Dựa theo paper [*Deep Preset: Blending and Retouching Photos with Color Style Transfer*](https://arxiv.org/abs/2007.10701), sử dụng ảnh reference để học cách chuyển Preset màu từ ảnh ref sang ảnh input
![](https://raw.githubusercontent.com/hoanghai912/temporary/main/images/deep-preset-model.PNG)

	- Về cơ bản mô hình bao gồm: Encoder T, Encoder C, Linear Layers L và Decoder G. Mô hình dựa trên U-Net.
	- Mô hình được control thông qua vector $P \in R^{69}$ chứa 69 cài đặt đại diện cho màu sắc của bức ảnh như: Hue, Saturation, Brightness, Contrast, ...
	- Loss function:
		- $L_p$: Minimize khả năng predict Preset từ ảnh tham chiếu $Z$
		- $L_{pp}$: Positive Pair-Wise Loss. Giúp tăng cường khả năng predict Preset cho mô hình.
	- Dataset: 1200 ảnh chất lượng cao trong dataset Flickr2K, sau đó được apply 501 Preset màu thông qua Lightroom.

### Ý tưởng

| ![](https://raw.githubusercontent.com/hoanghai912/temporary/main/images/BigColor-model.PNG) | 
|:--:| 
| *Mô hình BigColor* |

- Em sẽ tận dụng Encoder T và lớp Linear L để apply vào mô hình BigColor để control màu theo ảnh tham chiếu.
- Phần Encoder C của mô hình Deep Preset chỉ dùng để trích xuất thông tin contextual nên em nghĩ mình chưa cần thêm vào.
- Cùng với việc sử hai hàm Loss $L_{p}$ và $L_{pp}$ để condition mô hình.

### Việc tuần sau
- Implement và train mô hình