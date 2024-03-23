## Report tuần
- Tuần này nhóm tìm cách implement mô hình BigColor có tích hợp thêm module Encoder T của mô hình Deep Preset.

### BigColor

| ![](https://raw.githubusercontent.com/hoanghai912/temporary/main/images/BigColor-model.PNG) | 
|:--:| 
| *Mô hình BigColor (baseline)* |

### Deep Preset

| ![](https://raw.githubusercontent.com/hoanghai912/temporary/main/images/deep-preset-model.PNG) | 
|:--:| 
| *Mô hình Deep Preset (Reference)* |

### BigColor with Encoder T

| ![](https://raw.githubusercontent.com/hoanghai912/temporary/main/images/BigColor-modify.PNG) | 
|:--:| 
| *Mô hình BigColor tích hợp Encoder T* |

- Nhóm sử dụng Encoder T để extract feature từ ảnh tham khảo, sau đó đưa qua lớp Conv3x3 rồi Concat với feature F từ đầu ra của Encoder của BigColor (do sự khác biệt về kích thước output của 2 bộ Encoder). Sau đó đưa feature đã được concat vào Generator.
- Về hàm Loss, nhóm sử dụng thêm 2 hàm loss là $L_{pp}$ và $L_{p}$ của mô hình Deep Preset.

## Khó khăn gặp phải
- Nhóm vẫn chưa tiến hành train được mô hình được đề xuất.
- Code training của mô hình Deep Preset còn bị lỗi (do tác giả không public code chạy được mà chỉ share code trên drive với các phần bị lược bỏ nên vẫn còn bug). Nhóm đang cố đọc hiểu code và fix bug
- Kỹ năng engineer (coding) còn hạn chế nên tốn nhiề thời gian trong công đoạn implement.