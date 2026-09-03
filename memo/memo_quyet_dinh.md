# Memo quyết định — Klarna AI Assistant

**Quyết định:** SỬA — tiếp tục AI cho ca thường, tăng human-in-the-loop cho ca phức tạp.  
**Phạm vi:** Klarna AI Assistant; khách hàng cần hỗ trợ; bốn workflow gồm tiếp nhận, phân loại, AI giải quyết và chuyển người/QA/phản hồi.

## 1. Vấn đề và nguyên nhân gốc

Klarna đã triển khai AI ở quy mô lớn và đạt hiệu quả rõ, nhưng usage/deployment cao chưa đồng nghĩa adoption có chất lượng. Hai nguyên nhân gốc là việc tối ưu quá mạnh theo chi phí/khối lượng khiến quality gate chưa giữ vai trò quyết định, và handoff người–AI cho ca phức tạp chưa đủ nổi bật trong thiết kế vận hành.

## 2. Framework và bằng chứng

Gartner-Lite cho thấy Direction và Readiness đạt nhờ quy mô dữ liệu/vận hành lớn, nhưng Absorption cần sửa ở governance chất lượng. Mollick được dùng để giao AI xử lý ca thường và giữ quyền cuối cho con người ở ca tài chính, ID theft, khiếu nại hoặc ngoại lệ. ADKAR xác định điểm nghẽn chính ở Desire/niềm tin, nên giải pháp là tăng minh bạch, human option và QA thay vì chỉ đào tạo.

Klarna 20-F 2025 công bố AI xử lý 80% chat, 31 triệu hội thoại, thời gian trung bình 2 phút so với 12 phút ở nhân viên, giảm 25% câu hỏi lặp lại, CSAT ngang nhân viên và tiết kiệm khoảng 39 triệu USD năm 2024. Một SEC staff letter năm 2025 đồng thời dẫn thông tin rằng một số dịch vụ AI có chất lượng thấp hơn và nhấn mạnh khách hàng phải có thể gặp người thật. Đây là bằng chứng cho việc sửa quality gate thay vì chạy theo usage.

Nguồn: https://www.sec.gov/Archives/edgar/data/2003292/000200329226000007/klar-20251231.htm · https://www.sec.gov/Archives/edgar/data/2003292/000162828025034998/filename1.htm · https://www.sec.gov/Archives/edgar/data/2003292/000162828025052805/exhibit992klarnapresenta.htm · https://www.sec.gov/Archives/edgar/data/2003292/000000000025005760/filename1.pdf

## 3. Thay đổi sau phản biện

1. Thêm quality/risk metric bên cạnh volume, tốc độ và chi phí; mỗi metric có baseline, target, nguồn, owner và hành động khi xấu.
2. Thiết kế lại workflow với taxonomy ca phức tạp, confidence gate, SLA chuyển người và RACI rõ.
3. Chuyển roadmap 30–60–90 từ danh sách việc thành ba cổng có bằng chứng, tiêu chí qua cổng và phương án khi không đạt.

## 4. Quyết định

**SỬA.** Tiếp tục dùng AI cho FAQ và ca rủi ro thấp vì năm trong sáu metric đang đạt; không mở rộng tự động hoá ca phức tạp cho đến khi quality-risk flag về 0, human option được bảo đảm và QA theo phân khúc đạt yêu cầu. Dừng workflow rủi ro nếu xảy ra lỗi nghiêm trọng về quyền, tài chính hoặc không thể tạo đường chuyển người an toàn sau hai vòng sửa.

## 5. Lý do, bước tiếp theo và owner

Trong 0–30 ngày, AI Product Owner/Data Owner **Giang Minh Phú** chuẩn hoá bốn workflow, taxonomy và data dictionary. Ngày 31–60, QA Lead/Risk Owner **Lê Thị Thuý** thiết kế QA mẫu phân tầng, theo dõi lỗi nghiêm trọng và quality-risk flag. Ngày 61–90, Chủ quy trình/Human Escalation Owner **Trần Thị Kiều Oanh** kiểm SLA chuyển người, đối chiếu dashboard và trình Sponsor quyết định tiếp tục, sửa thêm hoặc dừng.
