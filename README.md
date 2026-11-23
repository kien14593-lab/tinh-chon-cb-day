# Tính chọn Aptomat & Tiết diện dây – Nhà dân dụng

Web app chạy hoàn toàn trên trình duyệt (1 file HTML, không cần cài đặt, chạy được offline) để tính chọn **aptomat (CB)**, **tiết diện dây/cáp**, **ống luồn** và **thống kê vật tư** cho hệ thống điện nhà ở theo sơ đồ 2 cấp: **Tủ tổng → Tủ nhánh → Thiết bị**.

🔗 **Dùng thử:** https://kien14593-lab.github.io/tinh-chon-cb-day/

## Tính năng
- Cấu trúc **Tủ tổng → Tủ nhánh → Mạch → Điểm**, mạch chia 3 kiểu cấp nguồn: **Chiếu sáng** (đèn, quạt trần qua công tắc), **Ổ cắm** (tải sinh hoạt ≤ 2.000W), **Mạch riêng** (điều hòa, bình nóng lạnh, bếp từ, bơm… có thể qua công tắc công suất 20–30A).
- 3 kiểu đấu mạch: **mạch vòng**, **hình tia**, **phân nhánh (trục)**.
- Công tắc 1–4 hạt (1 chiều, 2 chiều, chiết áp), ổ cắm đơn/đôi, thường/chống nước.
- **Khối lượng dây – ống theo cao độ**: trần bê tông, trần giả, trục tường, tủ điện, cao độ công tắc/ổ cắm/thiết bị (sửa được); số sợi L/N/PE theo đoạn, chừa đấu nối tại đế/hộp và tủ, dự phòng ống, hao hụt dây, quy đổi cuộn theo màu; cỡ ống theo hệ số lấp đầy 40%.
- Nguồn 1 pha / 3 pha (tự cân pha); điện 1 pha giới hạn CB tổng theo CB điện lực (mặc định 63A), tự tính hệ số đồng thời tối đa.
- Chọn CB và dây theo IEC 60364-5-52 (hiệu chỉnh nhiệt độ, nhóm mạch) và sụt áp.
- **Bóc vật tư**: aptomat, SPD, tủ + thanh cái, cáp/dây theo màu, đầu cos, ống + măng sông + cút + kẹp, công tắc/mặt/hạt, ổ cắm, đế âm, hộp nối, đèn – quạt, tiếp địa; nhập đơn giá ra dự toán.
- Sơ đồ nguyên lý, xuất Excel, In/PDF, Lưu/Mở dự án `.json`.

## Cách dùng
1. Mở link dùng thử, hoặc tải `index.html` về và mở bằng Chrome/Edge.
2. Tab **Thông số**: kiểm tra điện áp, nhiệt độ môi trường, hệ số, giới hạn sụt áp.
3. Tab **Thiết kế**: thêm tủ nhánh, chọn thiết bị, nhập số lượng và chiều dài dây.
4. Xem **Sơ đồ**, **Kết quả**, **Vật tư** → Xuất Excel hoặc In.

## Công thức chính
- Itt = P / (U·cosφ); CB thiết bị: In ≥ max(Itt × 1,25; CB tối thiểu).
- Tủ nhánh: Ptt = max(k_đt·ΣP; P thiết bị lớn nhất); cosφ_tb = ΣP / Σ(P/cosφ).
- Dây: Iz × k_nhiệt × k_nhóm ≥ In và ΔU ≤ giới hạn.
- Sụt áp 1 pha: ΔU% = 2·L·I·(ρ/S·cosφ + x·sinφ)/U·100 (3 pha thay 2 bằng √3).

Tham chiếu: TCVN 9206:2012, TCVN 9207:2012, TCVN 7447 / IEC 60364.

## Góp ý khi test
Gửi góp ý qua mục **Issues** của repo: mô tả trường hợp, đính kèm file `.json` dự án (nút *Lưu (.json)*) và kết quả mong đợi.

> ⚠️ Công cụ phục vụ thiết kế sơ bộ nhà ở. Kết quả cần được kỹ sư điện kiểm tra lại (dòng ngắn mạch, khả năng cắt Icu, catalogue hãng) trước khi thi công.
