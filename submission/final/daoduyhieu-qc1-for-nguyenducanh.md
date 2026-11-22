# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên): Nguyễn Đức Anh  
Người kiểm (học viên): Đào Duy Hiếu  
Ngày: 22/11/2026  
Phiên bản guideline: Road v1.0  
File được kiểm: `nguyenducanh-front.zip`, `nguyenducanh-fisheye.zip` (không có manifest; revision không rõ)  
Số ảnh kiểm: 20 ảnh bắt buộc (A01–A12, B01–B08; không kiểm ảnh extra)  
Số nhãn đã kiểm (shape + tag): 218 (138 shape + 80 tag)

Phương pháp: chạy `road_check lint` trên hai ZIP và đối chiếu nhãn với ảnh gốc theo Road v1.0.

## Tổng hợp theo mã

| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 tag camera | sai thuộc tính / bỏ sót | 20 ảnh | 0 | nặng |
| QC1-02 đủ L1, R1 | bỏ sót | 24 biên | 1 (5 chờ lead) | nặng |
| QC1-03 position | sai thuộc tính / thừa | 43 lane | 4 | nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | sai phạm vi / bỏ sót | 43 lane | 1 | chính |
| QC1-05 vạch đứt, che | sai phạm vi / sai thuộc tính | 43 lane | 2 | chính |
| QC1-06 style, color, kind | sai thuộc tính | 43 lane | 0 | chính |
| QC1-07 vùng lái | sai phạm vi / bỏ sót / thừa | 55 shape | 0 (2 chờ lead) | chính |
| QC1-08 đèn, màu | bỏ sót / sai phạm vi / sai thuộc tính | 23 đèn | 0 | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính | 40 box | 0 | chính |
| QC1-10 hình in, đủ biển | bỏ sót / sai phạm vi | 17 biển | 0 | chính |
| QC1-11 fisheye | sai phạm vi / sai thuộc tính | 39 shape | 9 | chính |
| QC1-12 file | lỗi file | 2 file | 0 | nhẹ / nặng |

## Danh sách lỗi (mỗi lỗi một dòng)

| # | Mã | Ảnh | Nhãn (label, id) | Mức | Mô tả ngắn |
| ---: | --- | --- | --- | --- | --- |
| 1 | QC1-02 | A07 | lane L1 | nặng | Thiếu L1 dù biên trái của làn xe còn nhìn thấy; cần sửa hoặc xin lead xác nhận loại biên. |
| 2 | QC1-03 | B06 | lane #0 | nặng | Camera `fisheye_left` nhưng lane không có `position=other`. |
| 3 | QC1-03 | B07 | lane #0 | nặng | Camera `fisheye_right` nhưng lane đang dùng R1; phải là `other`. |
| 4 | QC1-03 | B07 | lane #1 | nặng | Camera `fisheye_right` nhưng lane đang dùng R1; phải là `other`. |
| 5 | QC1-03 | B08 | lane #0 | nặng | Camera `fisheye_right` nhưng lane đang dùng R1; phải là `other`. |
| 6 | QC1-04 | A07 | lane R2 | chính | Polyline có điểm đầu ở xa và điểm cuối ở gần; vẽ ngược chiều. |
| 7 | QC1-05 | A01 | lane L2 #0/#1 | chính | Hai polyline cùng position L2, gần như gán trùng một vạch. |
| 8 | QC1-05 | A08 | lane L1 #0/#1 | chính | Hai polyline cùng position L1; cần kiểm tra vạch đứt có bị tách không. |
| 9 | QC1-11 | B02 | road_curb #0 | chính | Chỉ có 3 điểm, chưa bám đủ cung fisheye. |
| 10 | QC1-11 | B02 | road_curb #1 | chính | Chỉ có 3 điểm, chưa bám đủ cung fisheye. |
| 11 | QC1-11 | B02 | traffic_light | chính | Tâm box ngoài 80% bán kính nhưng `edge_zone` chưa bật. |
| 12 | QC1-11 | B03 | lane #1 | chính | Chỉ có 3 điểm, cần thêm điểm theo cung. |
| 13 | QC1-11 | B03 | traffic_sign | chính | Tâm box ngoài 80% bán kính nhưng `edge_zone` chưa bật. |
| 14 | QC1-11 | B04 | traffic_sign | chính | Tâm box ngoài 80% bán kính nhưng `edge_zone` chưa bật. |
| 15 | QC1-11 | B07 | lane #0 | chính | Chỉ có 3 điểm, cần thêm điểm theo cung. |
| 16 | QC1-11 | B07 | lane #1 | chính | Chỉ có 3 điểm, cần thêm điểm theo cung. |
| 17 | QC1-11 | B08 | lane #0 | chính | Chỉ có 2 điểm, chưa thể bám cung fisheye. |

## Ca mơ hồ

| Ảnh | Câu hỏi cho lead | Lời đáp (nếu có) |
| --- | --- | --- |
| A05 | Thiếu L1 và R1. Ảnh đường hẻm có xe đỗ hai bên và không thấy vạch sơn; có được miễn QC1-02 không? |  |
| A06 | Thiếu L1 và R1. Cần xác nhận các biên nhìn thấy ở giao lộ có phải lane bắt buộc hay không. |  |
| A09 | Thiếu R1. Bên phải là lề/curb và không thấy vạch rõ; có được miễn QC1-02 không? |  |
| B01, B02 | `drivable` chủ yếu phủ vùng crosswalk và chưa phủ rõ phần mặt đường phía xa; phần đó có phải mở rộng vào drivable không? |  |

## Quyết định

Lỗi nặng: 5 (thêm 5 mục QC1-02 chờ lead)  
Lỗi chính: 12 / 218 nhãn = 5,50% (thêm 2 mục QC1-07 chờ lead)  
Lỗi nhẹ: 0  
Ca chờ lead: 7  

Quyết định (Release / Hold / Rework): **Rework**  
Lý do: Có lỗi nặng đã xác nhận ở QC1-02/QC1-03; đồng thời tỉ lệ lỗi chính 5,50% vượt ngưỡng 5%. Các ca chờ lead không làm thay đổi quyết định Rework hiện tại.

Loại lỗi: bỏ sót = thiếu nhãn phải có; thừa = gán đối tượng không tồn tại; sai phạm vi = hình lệch, sai chiều, dừng sai chỗ hoặc tràn vùng. “Sai thuộc tính” và “lỗi file” là loại lỗi bổ sung của khóa học. Xem [thang mức lỗi](../../docs/qc_severity_road_v1.0.md).
