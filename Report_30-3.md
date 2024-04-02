## Report tuần 30/3

### BigColor with Encoder T

| ![](https://raw.githubusercontent.com/hoanghai912/temporary/main/images/BigColor-modify.PNG) | 
|:--:| 
| *Mô hình BigColor tích hợp Encoder T* |

- Tuần này nhóm implement mô hình kết hợp của 2 mô hình. Code của nhóm đã chạy được quá trình training trên dữ liệu test (không chính thức). Nhóm chưa đánh giá kết quả đầu ra của mô hình

- Về tổ chức dataset, cấu trúc thư mục dataset của mô hình có dạng:
```
└── db_root_dir/
    ├── train/
    │   ├── 0/
    │   │   ├── n02666196/
    │   │   │   ├── 001.jpg
    │   │   │   ├── 002.jpg
    │   │   │   └── ...
    │   │   ├── n02782093/
    │   │   │   ├── 001.jpg
    │   │   │   ├── 002.jpg
    │   │   │   └── ...
    │   │   ├── n02966193/
    │   │   │   ├── 001.jpg
    │   │   │   ├── 002.jpg
    │   │   │   └── ...
    │   │   └── ...
    │   ├── 1/
    │   ├── 2/
    │   └── ...
    ├── val
    └── norm_presets
		├── 0.json
		├── 1.json
		├── 2.json
		└── ...
```
- Trong đó 
	- ```n02666196, ...``` là các folder class của ImageNet
	- Folder ```0, 1, 2, ...``` là group của các ảnh được apply cùng một preset
	- Folder ```norm_presets``` chứa các ground-truth preset ở dạng file json

- Dataset mà nhóm dự định sử dụng chính thức để train mô hình bao gồm:
	- 20 presets
	- 400 class
	- 50 image per class
--> Total = ``` 20 x 400 x 50 = 400000 image ```

### Khó khăn gặp phải
- Việc áp dụng từng preset vào ảnh để chuẩn bị dataset cho quá trình training phải làm bằng tay trên Lightroom (nếu không tìm được script auto)

## Công  việc tuần tiếp theo
- Tiếp tục train mô hình và đánh giá các kết quả sơ bộ (một vài sample trên tập dataset nhỏ)
- Chuẩn bị dataset chính thức để train mô hình
- Bắt đầu viết báo cáo luận văn trện overleaf