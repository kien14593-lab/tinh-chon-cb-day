# Tính chọn Aptomat & Tiết diện dây – Nhà dân dụng

Web app chạy hoàn toàn trên trình duyệt (1 file HTML, không cần cài đặt, chạy được offline) để tính chọn **aptomat (CB)**, **tiết diện dây/cáp**, **ống luồn** và **thống kê vật tư** cho hệ thống điện nhà ở theo sơ đồ 2 cấp: **Tủ tổng → Tủ nhánh → Thiết bị**.

🔗 **Dùng thử:** https://<tên-tài-khoản>.github.io/<tên-repo>/

## Tính năng
- Nguồn 1 pha 220V hoặc 3 pha 380V (chia tủ theo pha A/B/C, nút **Tự cân pha**, báo lệch pha).
- Thư viện ~50 thiết bị dân dụng (sửa/thêm được): công suất, cosφ, có cần RCBO chống giật, CB tối thiểu.
- Tự chọn CB thiết bị → CB nhánh → CB tổng, đảm bảo chọn lọc (mỗi cấp lớn hơn ít nhất 1 bậc).
- Chọn dây theo khả năng tải (IEC 60364-5-52, hiệu chỉnh nhiệt độ & nhóm mạch) **và** sụt áp; tự tăng tiết diện khi cần.
- Sơ đồ nguyên lý, bảng kết quả, bảng vật tư (CB, mét dây/cáp, ống, vỏ tủ).
- Xuất Excel, In/PDF, Lưu/Mở dự án dạng `.json`. Dữ liệu tự lưu trên trình duyệt của từng máy.

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
