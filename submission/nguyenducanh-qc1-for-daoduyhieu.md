# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên): Đào Duy Hiếu  
Người kiểm (học viên): Nguyễn Đức Anh  
Ngày: 21/11/2026  
Phiên bản guideline: Road v1.0  
File được kiểm: `daoduyhieu-front.zip`, `daoduyhieu-fisheye.zip` (chưa tạo manifest)  
Số ảnh kiểm: 6  
Số nhãn đã kiểm (shape + tag): 63

## Tổng hợp theo mã

| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 tag camera | sai thuộc tính / bỏ sót | 6 ảnh | 0 | nặng |
| QC1-02 đủ L1, R1 | bỏ sót | 3 ảnh front | 1 | nặng |
| QC1-03 position | sai thuộc tính / thừa | 10 lane | 0 | nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | sai phạm vi / bỏ sót | 10 lane | 0 | chính |
| QC1-05 vạch đứt, che | sai phạm vi / sai thuộc tính | 10 lane | 1 | chính |
| QC1-06 style, color, kind | sai thuộc tính | 10 lane | 0 | chính |
| QC1-07 vùng lái | sai phạm vi / bỏ sót / thừa | 14 polygon | 0 | chính |
| QC1-08 đèn, màu | bỏ sót / sai phạm vi / sai thuộc tính | 1 đèn | 0 | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính | 2 box | 0 | chính |
| QC1-10 hình in, đủ biển | bỏ sót / sai phạm vi | 1 biển | 0 | chính |
| QC1-11 fisheye | sai phạm vi / sai thuộc tính | 18 shape | 5 | chính |
| QC1-12 file | lỗi file | 2 file | 0 | nhẹ / nặng |

## Danh sách lỗi (mỗi lỗi một dòng)

| # | Mã | Ảnh | Nhãn (label, id) | Mức | Mô tả ngắn |
| ---: | --- | --- | --- | --- | --- |
| 1 | QC1-02 | A07 | lane L1 | nặng | Thiếu L1; cần xác nhận biên trái là lane hay road_curb. |
| 2 | QC1-05 | A01 | lane L2 #1/#2 | chính | Hai polyline L2 gần như trùng nhau. |
| 3 | QC1-11 | B02 | road_curb #0 | chính | Chỉ có 3 điểm, chưa bám đủ cung fisheye. |
| 4 | QC1-11 | B02 | road_curb #1 | chính | Chỉ có 3 điểm, chưa bám đủ cung fisheye. |
| 5 | QC1-11 | B07 | lane #0 | chính | Chỉ có 3 điểm, cần thêm điểm theo cung. |
| 6 | QC1-11 | B07 | lane #1 | chính | Chỉ có 3 điểm, cần thêm điểm theo cung. |
| 7 | QC1-11 | B08 | lane #0 | chính | Chỉ có 2 điểm, cần thêm điểm theo cung. |

## Ca mơ hồ

| Ảnh | Câu hỏi cho lead | Lời đáp (nếu có) |
| --- | --- | --- |
| A05 | Không thấy vạch sơn L1/R1 rõ; có được miễn QC1-02 không? | Chờ coach xác nhận. |
| A07 | Biên trái sát barrier là lane hay road_curb? | Chờ coach xác nhận. |

## Quyết định

Lỗi nặng: 1  
Lỗi chính: 6 / 63 nhãn = 9,52%  
Lỗi nhẹ: 0  
Ca chờ lead: 2  

Quyết định (Release / Hold / Rework): **Rework**  
Lý do: Có lỗi nặng QC1-02 và tỉ lệ lỗi chính vượt 5%.

Loại lỗi: bỏ sót = thiếu nhãn phải có; thừa = gán cái không phải đối tượng; sai phạm vi = hình lệch, sai chiều, dừng sai chỗ, tràn vùng. “Sai thuộc tính” và “lỗi file” là loại lỗi khóa học bổ sung. Xem [thang mức lỗi](../docs/qc_severity_road_v1.0.md).
