# Thiết kế điện nhà dân dụng – chọn CB, dây, bóc khối lượng (v4)

Dùng trực tuyến: https://kien14593-lab.github.io/tinh-chon-cb-day/

Web app 1 file HTML, chạy trên trình duyệt, không cần cài đặt. Dữ liệu lưu trên máy (localStorage) và file .json.

## Quy trình 4 bước
1. **Công trình** – thông tin, chiều cao tầng/trần, bộ thông số mẫu.
2. **Thiết kế điện** – cây Tủ tổng → tủ nhánh → mạch. Công tắc nhập theo bảng/hạt (1 chiều, 2 chiều, chiết áp, chống nước); ổ cắm chọn đơn/đôi, thiết bị cắm, chống nước; mạch riêng có tùy chọn công tắc công suất. Tự chọn CB, dây theo IEC 60364-5-52 / TCVN 7447.
   - Công suất ổ cắm = thực tải; k_đt chỉ áp ở CB tổng tủ nhánh và CB tổng cả nhà (gợi ý theo số mạch).
   - Điện 1 pha: CB tổng ≤ 63A, báo k_đt tối đa.
3. **Bóc khối lượng** – nhập tay theo khu vực (tủ nhánh hoặc tầng) theo phương pháp VNK (chiếu sáng, ổ cắm 3 trường hợp) hoặc bảng tính video; số lộ/công tắc/hạt/đèn/ổ lấy tự động từ bước 2; mạch riêng; cáp trục làm tròn 5m.
4. **Vật tư & xuất file** – BOM có đơn giá (nhập 1 lần trong thư viện), gộp/tách dây theo màu, xuất Excel, in PDF, sơ đồ ghi kiểu bản vẽ.

Chế độ Cơ bản / Nâng cao, bảng lỗi có nút "Đi tới". Kết quả phục vụ thiết kế sơ bộ, cần kỹ sư kiểm tra lại.
