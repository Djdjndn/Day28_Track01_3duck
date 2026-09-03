# Day28_Track01_3duck

## 1. Thành viên và đóng góp

> Nhóm phản biện chéo: **Flaiiin**.

| Họ tên | MSSV | Phần phụ trách | Góp ý đã đưa cho nhóm bạn |
|---|---|---|---|
| Lê Thị Thuý | 2A202601381 | Phạm vi, Gartner-Lite và readiness | Flaiiin: cần khoá rõ một sản phẩm, một nhóm người dùng và tối đa bốn workflow. |
| Trần Thị Kiều Oanh | 2A202601417 | Workflow AS-IS / TO-BE và Mollick | Flaiiin: cần chỉ rõ người chịu trách nhiệm cuối và cách xử lý khi AI không chắc. |
| Giang Minh Phú | 2A202601729 | ADKAR, metrics và roadmap | Flaiiin: nên thay chỉ số activity bằng metric chất lượng/workflow có nguồn dữ liệu và hành động khi xấu. |

## 2. Phạm vi

Trợ lý AI tra cứu tài liệu nội bộ · nhân viên vận hành · bốn quy trình: tìm tài liệu, tóm tắt, kiểm chứng, sử dụng/báo lỗi. Vấn đề quan sát: công cụ đã triển khai nhưng người dùng vẫn quay lại tìm file hoặc hỏi đồng nghiệp; câu trả lời thiếu nguồn và ngày cập nhật.

## 3. Nguyên nhân gốc

Hai nguyên nhân gốc: (1) AI chưa nằm trong workflow chính thức, handoff và quyền quyết định cuối chưa rõ — chẩn đoán bằng Mollick; (2) kiến trúc tin cậy và readiness còn thiếu nguồn kiểm chứng, data owner, lịch cập nhật, QA mẫu và cơ chế chuyển người — chẩn đoán bằng Gartner-Lite, ADKAR và NIST AI RMF. Bằng chứng hiện có là dấu hiệu trong brief case của Lab; baseline định lượng được thu từ log tác vụ và QA mẫu ở tuần 1.

## 4. Cách làm mới

TO-BE bắt buộc người dùng mở nguồn và xem ngày cập nhật trước khi dùng; con người/SME chịu trách nhiệm quyết định cuối; khi AI không chắc hoặc tác vụ rủi ro cao, kết quả không được dùng và phải chuyển SME, đồng thời tạo ticket phản hồi để học từ lỗi.

## 5. Chỉ số

Product metric chính: tỷ lệ câu trả lời có nguồn và ngày cập nhật, baseline đo mẫu tuần 1, target ≥95%, nguồn là log câu trả lời + QA mẫu 10%, owner là AI Product Owner. Workflow metric chính: thời gian trung vị hoàn thành tra cứu, baseline đo tuần 1, target ≤8 phút, nguồn là timestamp task start/end, owner là Chủ quy trình. Dashboard còn đo hành vi kiểm nguồn, rework và sự cố ACL; mỗi chỉ số có hành động khi xấu.

## 6. Quyết định

**SỬA — tiếp tục pilot có điều kiện, chưa rollout rộng.** Lý do: nguyên nhân gốc có thể sửa và đo trong phạm vi pilot 20–30 nhân viên vận hành. So với v1, v2 (1) thay activity metric bằng bộ metric từ hành vi đến chất lượng/giá trị với nguồn và action rõ; (2) bổ sung RACI, nguồn kiểm chứng và escalation khi AI không chắc; (3) biến roadmap thành ba gate có tiêu chí qua cổng.

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

- Xác nhận nội dung góp ý phản biện trong bảng đúng với trao đổi thực tế cùng nhóm Flaiiin.
- Nhập baseline và kết quả pilot thật vào workbook v2; không đưa dữ liệu nội bộ nhạy cảm lên repo public.
- Đối chiếu số liệu giữa README, memo và dashboard.
- Đặt repo public, nhánh `main`, rồi thử mở link ở cửa sổ ẩn danh.
