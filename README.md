# Day28_Track01_3duck

## 1. Thành viên và đóng góp

> Nhóm phản biện chéo: **Flaiiin**.

| Họ tên | MSSV | Phần phụ trách | Góp ý nhóm mình ĐƯA CHO Flaiiin |
|---|---|---|---|
| Lê Thị Thuý | 2A202601381 | Phạm vi, Gartner-Lite và readiness | Cần khoá rõ một sản phẩm, một nhóm người dùng và tối đa bốn workflow; chấm Readiness phải chỉ được data owner và lịch cập nhật nguồn. |
| Trần Thị Kiều Oanh | 2A202601417 | Workflow AS-IS / TO-BE và Mollick | AS-IS và TO-BE phải cùng đơn vị so sánh (cùng workflow, cùng nhóm người dùng) thì mới chứng minh được cải thiện. |
| Giang Minh Phú | 2A202601729 | ADKAR, metrics và roadmap | ADKAR phải chỉ đúng nghẽn ở một chữ cái rồi mới chọn can thiệp, tránh mặc định "đào tạo thêm". |

### Góp ý Flaiiin ĐƯA CHO nhóm mình → đã sửa ở đâu

| # | Góp ý nhận được | Thay đổi trong v2 | Vị trí trong workbook |
|---|---|---|---|
| 1 | Số login và số câu hỏi chỉ là activity, chưa chứng minh giá trị. | Thêm tỷ lệ mở nguồn, thời gian từ log, tỷ lệ không cần QA làm lại và sự cố ACL. | `Metrics!A5:J11` |
| 2 | Chưa rõ ai chịu trách nhiệm và xử lý khi AI không chắc. | Thêm người phê duyệt cuối, SME escalation, ticket phản hồi và owner từng bước. | `Workflow!F6:I18` |
| 3 | 30–60–90 là danh sách việc, chưa có gate. | Thêm bằng chứng, tiêu chí qua cổng và hành động nếu không đạt cho từng giai đoạn. | `Roadmap 30-60-90!A5:H8` |

Chi tiết dấu vết chỉnh sửa xem sheet `Phan bien`.

## 2. Phạm vi

Trợ lý AI tra cứu tài liệu nội bộ · nhân viên vận hành · bốn quy trình: tìm tài liệu, tóm tắt, kiểm chứng, sử dụng/báo lỗi. Vấn đề quan sát: công cụ đã triển khai nhưng người dùng vẫn quay lại tìm file hoặc hỏi đồng nghiệp; câu trả lời thiếu nguồn và ngày cập nhật.

## 3. Nguyên nhân gốc

Hai nguyên nhân gốc: (1) AI chưa nằm trong workflow chính thức, handoff và quyền quyết định cuối chưa rõ — chẩn đoán bằng Mollick; (2) kiến trúc tin cậy và readiness còn thiếu nguồn kiểm chứng, data owner, lịch cập nhật, QA mẫu và cơ chế chuyển người — chẩn đoán bằng Gartner-Lite, ADKAR và NIST AI RMF.

Bằng chứng hiện có gồm hai nguồn, đều ghi kèm nguồn trong sheet `Chan doan` (cột Bằng chứng): **brief case của Lab** (người dùng quay lại tìm file hoặc hỏi đồng nghiệp; câu trả lời không kèm nguồn và ngày cập nhật) và **dashboard v1** (bốn chỉ số đều là activity hoặc tự khai). Riêng nhận định thiếu data owner / lịch cập nhật / ACL được đánh dấu **chưa kiểm chứng**, sẽ xác nhận ở tuần 1. Baseline định lượng **chưa đo** — thu từ log tác vụ, click log nguồn và QA mẫu ở tuần 1 pilot.

## 4. Cách làm mới

TO-BE bắt buộc người dùng mở nguồn và xem ngày cập nhật trước khi dùng; con người/SME chịu trách nhiệm quyết định cuối; khi AI không chắc hoặc tác vụ rủi ro cao, kết quả không được dùng và phải chuyển SME, đồng thời tạo ticket phản hồi để học từ lỗi.

## 5. Chỉ số

Product metric chính: tỷ lệ câu trả lời có nguồn và ngày cập nhật, target ≥95%, nguồn là log câu trả lời + QA mẫu 10%, owner là AI Product Owner (Giang Minh Phú). Workflow metric chính: thời gian trung vị hoàn thành tra cứu, target ≤8 phút, nguồn là timestamp task start/end, owner là Chủ quy trình (Trần Thị Kiều Oanh). Dashboard còn đo hành vi kiểm nguồn, rework và sự cố ACL; mỗi chỉ số có nguồn dữ liệu, owner và hành động khi xấu.

**Trạng thái dữ liệu tại thời điểm nộp:** cả 6 chỉ số đều ở trạng thái `CHƯA ĐO`. Cột Baseline ghi rõ kế hoạch đo, cột "Kết quả mới nhất" để trống có chủ ý — không điền số giả. Cột Trạng thái ở sheet `Metrics` tự tính bằng công thức theo chiều mục tiêu, nên chỉ cần nhập kết quả tuần 1 vào cột G là dashboard tự cập nhật (kể cả bộ đếm đạt/xấu/chưa đo ở sheet `Tong quan`).

## 6. Quyết định

**SỬA — tiếp tục pilot có điều kiện, chưa rollout rộng.** Lý do: nguyên nhân gốc có thể sửa và đo trong phạm vi pilot 20–30 nhân viên vận hành. So với v1, v2 (1) thay activity metric bằng bộ metric từ hành vi đến chất lượng/giá trị với nguồn và action rõ; (2) bổ sung RACI, nguồn kiểm chứng và escalation khi AI không chắc; (3) biến roadmap thành ba gate có tiêu chí qua cổng.

## 7. Phân công owner

| Vai trò trong pilot | Người chịu trách nhiệm | Gate phụ trách |
|---|---|---|
| AI Product Owner | Giang Minh Phú | 0–30 ngày |
| QA Lead · Security Owner | Lê Thị Thuý | 31–60 ngày |
| Chủ quy trình · Trưởng nhóm vận hành | Trần Thị Kiều Oanh | 61–90 ngày |
| Sponsor | Ngoài nhóm — ký quyết định tại gate ngày 90 | — |

## Cấu trúc bài nộp

```text
Day28_Track01_3duck/
├── README.md
├── dashboard/
│   └── dashboard_hanh_dong_v2.xlsx
├── memo/
│   └── memo_quyet_dinh.md
└── v1/
    └── dashboard_hanh_dong_v1.xlsx
```

## Trước khi nộp

- [x] Đối chiếu số liệu và tên owner giữa README, memo và dashboard.
- [x] Rà soát dữ liệu nhạy cảm: case là tình huống giả định của Lab, không có dữ liệu nội bộ doanh nghiệp thật; workbook không chứa metadata tác giả hay đường dẫn máy. Thông tin cá nhân duy nhất là họ tên và MSSV của ba thành viên, là phần định danh bắt buộc của bài nộp.
- [x] Ghi rõ trạng thái `CHƯA ĐO` cho toàn bộ metric thay vì điền số giả.
- [ ] **Nhóm tự xác nhận:** ba dòng "Góp ý nhóm mình ĐƯA CHO Flaiiin" ở mục 1 phải khớp biên bản buổi phản biện thật; sửa lại nếu khác.
- [ ] Nhập baseline và kết quả pilot vào cột D/G sheet `Metrics` khi có dữ liệu tuần 1.
- [ ] Đặt repo public, nhánh `main`, rồi thử mở link ở cửa sổ ẩn danh.
