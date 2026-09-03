# Memo quyết định — Trợ lý AI tra cứu tài liệu nội bộ

**Quyết định:** SỬA — tiếp tục pilot có điều kiện, chưa rollout rộng.  
**Phạm vi:** Một sản phẩm AI; nhân viên vận hành; bốn quy trình: tìm, tóm tắt, kiểm chứng, sử dụng/báo lỗi.

## 1. Vấn đề và nguyên nhân gốc

Công cụ đã được triển khai nhưng chưa đạt adoption: nhân viên vẫn quay lại tìm file hoặc hỏi đồng nghiệp, còn câu trả lời AI thiếu nguồn và ngày cập nhật. Đây là triệu chứng của hai nguyên nhân gốc: AI chưa nằm trong workflow chính thức với handoff/owner rõ; kiến trúc tin cậy và readiness còn thiếu nguồn được quản lý, QA mẫu và cơ chế chuyển người khi AI không chắc.

## 2. Framework và bằng chứng

Mollick được dùng để phân lại quyền: AI tìm và tóm tắt; nhân viên kiểm nguồn; SME/quản lý phê duyệt ngoại lệ và chịu trách nhiệm cuối. Gartner-Lite cho thấy Direction đạt nhưng Readiness và Absorption thiếu data owner, lịch cập nhật, ACL, owner chất lượng và vòng phản hồi. ADKAR xác định nghẽn ở Awareness/Desire vì người dùng chưa rõ phạm vi dùng và không tin câu trả lời thiếu nguồn; vì vậy đào tạo đơn lẻ không đủ.

Bằng chứng hiện có đến từ hai nguồn và được ghi kèm nhãn nguồn ở sheet `Chan doan`: brief case của Lab (người dùng quay lại tìm file; câu trả lời không kèm nguồn và ngày cập nhật; không có bước QA hay đường chuyển SME) và dashboard v1 (bốn chỉ số đều là activity hoặc tự khai). Nhận định thiếu data owner / lịch cập nhật / ACL hiện là suy luận, được đánh dấu **chưa kiểm chứng** và sẽ xác nhận ở tuần 1. **Tại thời điểm nộp chưa có số liệu pilot thật:** cả sáu metric ở trạng thái `CHƯA ĐO`, cột Baseline chỉ ghi kế hoạch đo và cột kết quả để trống có chủ ý. Dữ liệu định lượng sẽ lấy từ task log, click log, QA checklist và security log trong tuần 1. Tham chiếu quản trị: NIST AI RMF — https://airc.nist.gov/RMF.

## 3. Thay đổi sau phản biện

1. Thay bộ chỉ số thiên về activity (login, số câu hỏi, thời gian tự khai) bằng metric có khả năng ra quyết định: tỷ lệ mở nguồn, thời gian từ log, tỷ lệ hoàn thành không cần làm lại, tỷ lệ có citation và sự cố ACL.
2. Bổ sung RACI trong TO-BE: con người giữ quyền quyết định cuối, SME nhận ngoại lệ, AI Product Owner (Giang Minh Phú) sở hữu chất lượng và vòng phản hồi.
3. Bổ sung tiêu chí qua cổng, bằng chứng hoàn thành và hành động nếu không đạt cho từng giai đoạn 30–60–90.

## 4. Quyết định

**SỬA.** Tiếp tục pilot 20–30 nhân viên vận hành, nhưng chưa mở rộng cho tới khi nguồn, quyền truy cập, trích nguồn, QA và owner vận hành đạt yêu cầu. Dừng nếu có sự cố truy cập nghiêm trọng, không xác lập được nguồn đáng tin hoặc không xuất hiện lợi ích workflow sau hai vòng sửa.

## 5. Lý do, bước tiếp theo và owner

Hai nguyên nhân gốc có thể xử lý trong phạm vi hẹp và kiểm chứng bằng dữ liệu thu được từ workflow. Trong 0–30 ngày, AI Product Owner (Giang Minh Phú) khoá bốn workflow pilot, danh mục nguồn, ACL, data owner và baseline. Ngày 31–60, QA Lead (Lê Thị Thuý) bật QA mẫu 10%, theo dõi citation/rework và hỗ trợ người dùng ngay trong workflow; Security Owner (Lê Thị Thuý) theo dõi sự cố truy cập ngoài quyền. Ngày 61–90, Chủ quy trình (Trần Thị Kiều Oanh) cùng Sponsor đối chiếu mục tiêu, kiểm governance và chốt mở rộng, sửa thêm hoặc dừng.
