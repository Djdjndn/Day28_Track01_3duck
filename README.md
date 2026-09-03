# Day28_Track01_3duck

## 1. Thành viên và đóng góp

**Nhóm phản biện chéo:** Flaiiin.

| Họ tên | MSSV | Phần phụ trách | Góp ý đã đưa cho nhóm Flaiiin |
|---|---|---|---|
| Lê Thị Thuý | 2A202601381 | Gartner-Lite, readiness và quality gate | Cần chỉ rõ data owner, nguồn dữ liệu và điều kiện qua cổng thay vì chỉ liệt kê hoạt động. |
| Trần Thị Kiều Oanh | 2A202601417 | Workflow AS-IS/TO-BE và Mollick | AS-IS và TO-BE phải cùng đơn vị so sánh; ca phức tạp cần người giữ quyền quyết định cuối. |
| Giang Minh Phú | 2A202601729 | ADKAR, metrics và tổng hợp dashboard | Không dùng login/số câu hỏi làm bằng chứng giá trị; cần metric workflow và chất lượng có action khi xấu. |

### Góp ý nhận từ Flaiiin và thay đổi trong v2

| # | Góp ý nhận được | Thay đổi trong v2 | Vị trí |
|---|---|---|---|
| 1 | Activity/volume chưa chứng minh adoption có chất lượng. | Thêm CSAT index, repeat inquiry, quality-risk flag và hành động khi xấu. | `Metrics!A5:K16` |
| 2 | Chưa rõ quyền cuối và cách xử lý ca phức tạp. | Thêm taxonomy, confidence gate, SLA chuyển người và RACI. | `Workflow!F6:I18` |
| 3 | Roadmap chưa phải cổng quyết định. | Thêm bằng chứng, tiêu chí qua cổng và phương án khi không đạt. | `Roadmap 30-60-90!A5:H8` |

## 2. Phạm vi

**Klarna AI Assistant** · **khách hàng Klarna cần hỗ trợ** · bốn workflow: tiếp nhận câu hỏi, AI phân loại, AI giải quyết, chuyển người/QA/phản hồi. Đây là case thực tế công khai: AI đạt mức sử dụng và hiệu quả cao nhưng xuất hiện tín hiệu chất lượng thấp hơn ở một số dịch vụ, buộc Klarna nhấn mạnh lựa chọn hỗ trợ con người.

## 3. Nguyên nhân gốc

Hai nguyên nhân gốc: (1) tối ưu quá mạnh theo chi phí/khối lượng khiến quality gate chưa giữ vai trò quyết định — chẩn đoán bằng Gartner-Lite và năm tầng đo lường; (2) phân chia người–AI và handoff cho ca phức tạp chưa đủ rõ — chẩn đoán bằng Mollick, với điểm nghẽn ADKAR chính ở **Desire/niềm tin**. Bằng chứng lấy từ Klarna 20-F 2025, hồ sơ F-1 và thư phản hồi SEC năm 2025.

Nguồn: https://www.sec.gov/Archives/edgar/data/2003292/000200329226000007/klar-20251231.htm · https://www.sec.gov/Archives/edgar/data/2003292/000162828025034998/filename1.htm · https://www.sec.gov/Archives/edgar/data/2003292/000000000025005760/filename1.pdf

## 4. Cách làm mới

TO-BE cho phép khách hàng chọn người thật, phân loại ca tài chính/ID theft/khiếu nại để chuyển người, chỉ tự động hoá ca rủi ro thấp, và bắt buộc QA mẫu phân tầng. Con người giữ quyền quyết định cuối; khi confidence thấp hoặc khách hỏi lại lần hai, hệ thống tự chuyển người và ghi log phản hồi.

## 5. Chỉ số

Product metric: tỷ lệ chat do AI xử lý, baseline 66%, target ≥80%, kết quả 80%, nguồn service chat log trong hồ sơ SEC, owner Giang Minh Phú. Workflow metric: thời gian xử lý, baseline 12 phút ở human, target ≤3 phút, kết quả AI 2 phút, owner Trần Thị Kiều Oanh. Dashboard còn đo repeat inquiry, CSAT index, tiết kiệm chi phí và quality-risk flag; tất cả đều có baseline, target, nguồn, owner và hành động khi xấu.

## 6. Quyết định

**SỬA — tiếp tục AI cho ca thường, tăng human-in-the-loop cho ca phức tạp.** Năm trong sáu metric đạt, nhưng quality-risk flag xấu; vì vậy usage và cost không đủ để mở rộng thiếu kiểm soát. So với v1, v2 bổ sung quality/risk metric, RACI–handoff và ba cổng 30–60–90 có tiêu chí rõ.

## 7. Owner và bước tiếp theo

| Vai trò | Người chịu trách nhiệm | Gate |
|---|---|---|
| AI Product Owner / Data Owner | Giang Minh Phú | 0–30 ngày |
| QA Lead / Risk Owner | Lê Thị Thuý | 31–60 ngày |
| Chủ quy trình / Human Escalation Owner | Trần Thị Kiều Oanh | 61–90 ngày |
| Sponsor | Vai trò phê duyệt ngoài nhóm | Ngày 90 |

## Cấu trúc repo

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

## Checklist nộp bài

- [x] Repo public và mở được khi chưa đăng nhập.
- [x] Tên repo đúng mẫu, nhánh `main`.
- [x] Có dashboard v2, memo và dashboard v1.
- [x] README đủ thành viên, MSSV, phần phụ trách và góp ý chéo.
- [x] README, memo và dashboard dùng cùng case, metric, owner và quyết định.
- [x] Không chứa dữ liệu nội bộ nhạy cảm; toàn bộ bằng chứng là dữ liệu công khai.
- [ ] Ba thành viên dán cùng link repo vào LMS.

