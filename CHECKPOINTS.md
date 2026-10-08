# Checkpoints — 5 trạm, 120 phút

Nguyên tắc xuyên suốt: mọi con số bạn viết ra phải trả lời được câu **"dựa vào đâu mà là con số này?"**. Ngưỡng không có lý do bị chấm 0 — kể cả khi nó đúng.

Làm Trạm 1–4 trong `worksheet.md`, Trạm 5 trong `dashboard.md` (mẫu ở [`templates/`](templates/)).

| Mốc | Checkpoint | Phải có |
|---|---|---|
| Phút 15 | CP1 — Loại & bảng đèn | 1 câu chốt loại có lý do · bảng đèn §3 đã đánh dấu ✅/🔧/❌ toàn bộ |
| Phút 40 | CP2 — Cây 3 tầng | 1 North Star · 6–8 thẻ đèn · ≥2 đèn Leading · ≥1 đèn chi phí AI |
| Phút 70 | CP3 — Ngưỡng ⭐ | 100% đèn có 🟢🟡🔴 + [BM]/[MH]/[TB] + 1 câu lý do · ≥2 ngưỡng [MH] |
| Phút 100 | CP4 — Luật ⭐ | 5 luật đủ 4 vế bắt buộc · ≥2 luật dừng · không luật nào "xem xét lại" |
| Phút 120 | CP5 — Dashboard | 1 trang · 3 cổng gác có số · kill criteria · mục "chưa đo được" |

---

## Trạm 1 — Chốt loại & lấy bảng đèn · 15'

**Cần làm**

1. (5') Trả lời 3 câu hỏi theo **thực tế hôm nay**, không theo kế hoạch quý sau ([HANDBOOK §2.5](HANDBOOK.md#25-đèn-nào-bật-trước--theo-loại)):
   - Ai trả tiền cho bạn? Cá nhân → B2C. Doanh nghiệp → B2B hoặc B2B2C.
   - Ai dùng sản phẩm? Chính người trả tiền → B2B. Khách hàng *của* người trả tiền → B2B2C.
   - Nếu có bên trung gian: bạn có chạm được người dùng cuối không? Không chạm, không có dữ liệu, không có thương hiệu trước mặt họ → dùng bảng **B2B**.
2. (3') Viết **1 câu** chốt loại. Mẫu: *"Chúng tôi là B2B2C vì tiền đến từ [X], người dùng thật là khách của [X], và chúng tôi chạm được họ qua [bề mặt cụ thể]."*
3. (7') Mở đúng bảng đèn của mình ở [HANDBOOK §3](HANDBOOK.md#3-ba-bảng-điều-khiển). Với **từng đèn**, đánh dấu:
   - ✅ Đo được hôm nay — số nằm ở đâu?
   - 🔧 Đo được trong 2 tuần — cần gì? (log, event tracking, điều khoản hợp đồng)
   - ❌ Chưa đo được và chưa biết cách — ghi ra, đừng giấu.

**Sản phẩm:** mục "Trạm 1" trong `worksheet.md`.

**Cần hiểu:** mỗi loại có **một** đèn bật trước — sai đèn này thì mọi đèn khác vô nghĩa.

**Tự kiểm tra**
- [ ] Câu chốt loại nói rõ ai trả tiền, ai dùng, chạm end-user qua đâu.
- [ ] Mọi đèn trong bảng §3 của loại mình đều có ✅/🔧/❌.
- [ ] Không chọn B2B2C chỉ vì "nghe có đòn bẩy", không chọn theo kế hoạch năm sau.

---

## Trạm 2 — Dựng cây 3 tầng · 25'

**Cần làm**

1. (4') Chọn **1 North Star** — con số duy nhất bạn nhìn mỗi tuần nếu chỉ được nhìn một. Thường chính là đèn bật trước của loại mình.
2. (12') Chọn **6–8 đèn** từ bảng §3 (được thêm đèn riêng của sản phẩm) và điền thẻ đèn ([HANDBOOK §2.2](HANDBOOK.md#22-thẻ-đèn--cấu-trúc-một-chỉ-số-dùng-được)): tên & định nghĩa (đếm gì, **không** đếm gì) · công thức · nhịp đo · báo trước cho đèn nào.
   - ≥2 đèn **Leading**
   - ≥1 đèn về **chi phí AI** (token, inference, cost/job)
   - ≤3 đèn **Lagging**
3. (5') Viết trường "báo trước cho đèn nào" cho mỗi đèn. Không viết được → **bỏ đèn đó**.
4. (4') Cắt bớt. Quá 8 đèn là dashboard không ai mở.

**Sản phẩm:** bảng thẻ đèn trong `worksheet.md`.

**Cần hiểu:** Leading đổi theo ngày/tuần và báo trước 1–3 tháng; Operating là đòn bẩy bạn kéo được; Lagging là bảng điểm.

**Tự kiểm tra**
- [ ] Hai người khác nhau đọc định nghĩa sẽ đếm ra **cùng một số** ("user hoạt động" = mở app? làm xong một việc? quay lại lần hai?).
- [ ] Mỗi đèn Leading chỉ ra được một đèn cụ thể ở tầng dưới.
- [ ] Bí? Chạy **Prompt 5.1** (Dashboard Tier Audit) ở [HANDBOOK §5](HANDBOOK.md#5-prompts-cho-ai-english-only).

---

## Trạm 3 — Đặt ngưỡng · 30' ⭐

**Cần làm**

1. (6') Gắn nguồn cho từng ngưỡng: **[BM]** benchmark có nguồn · **[MH]** suy từ mô hình của bạn · **[TB]** tự đo baseline ([HANDBOOK §2.3](HANDBOOK.md#23-ngưỡng-đến-từ-đâu)).
2. (8') Đèn **[BM]**: lấy số ở [HANDBOOK §8](HANDBOOK.md#8-references), **ghi ngày bạn kiểm tra**. Benchmark cũ hơn 3 tháng so với ngày làm bài → mở nguồn gốc và cập nhật.
3. (10') Đèn **[MH]** — phần quan trọng nhất. Mở số mô hình tài chính và Cost/Job, **suy ngược**:
   - Mô hình chỉ sống khi khách ở lại ≥N tháng → retention tháng 3 tối thiểu là bao nhiêu?
   - CAC payback < 12 tháng → với ARPU và GM này, CAC tối đa là bao nhiêu?
   - GM mục tiêu 50% → chi phí inference mỗi job tối đa là bao nhiêu?

   Ghi **đủ phép tính** vào mục "Phụ lục [MH]" của worksheet. **Bắt buộc ≥2 ngưỡng [MH].**
4. (6') Đèn **[TB]**: ghi *"chưa có chuẩn, đo 2 chu kỳ rồi lấy làm baseline"* + ngày dự kiến có số. Đây là câu trả lời hợp lệ.

**Ví dụ một phép tính [MH] (số minh hoạ — thay bằng số của bạn):**

```
ARPU = 200.000đ/tháng · GM mục tiêu = 60% · payback tối đa = 12 tháng
Lãi gộp/khách/tháng = 200.000 × 60% = 120.000đ
CAC tối đa = 120.000 × 12 = 1.440.000đ  → 🟢 < 1,2tr · 🟡 1,2–1,44tr · 🔴 > 1,44tr
```

**Cần hiểu:** benchmark ngành là điểm bắt đầu, không phải mục tiêu. Số suy từ mô hình hiếm khi tròn — 10%, 20%, 50% thường là dấu hiệu đoán.

**Tự kiểm tra**
- [ ] 100% đèn có 🟢🟡🔴 + ký hiệu nguồn + 1 câu lý do.
- [ ] ≥2 ngưỡng [MH] có phép tính đầy đủ.
- [ ] Mọi [BM] có ngày kiểm tra.
- [ ] Không có ngưỡng đặt dễ để đèn luôn xanh.
- [ ] Bí? Chạy **Prompt 5.2** (Threshold Justification Challenger).

---

## Trạm 4 — Viết luật quyết định · 30' ⭐

**Cần làm**

1. (4') Chọn 5 đèn quan trọng nhất (ưu tiên Leading) — mỗi đèn một luật.
2. (14') Viết đủ các vế ([HANDBOOK §2.4](HANDBOOK.md#24-luật-quyết-định)):

   ```
   NẾU        <đèn> <toán tử> <ngưỡng>                  ← bắt buộc
   TRONG/TRÊN <thời gian hoặc số quan sát>              ← bắt buộc
   VÀ         <điều kiện mẫu đủ lớn>                    ← khi metric dễ nhiễu vì mẫu nhỏ
   THÌ        <động từ hành động cụ thể>                ← bắt buộc
   KHÔNG THÌ  <hành động bị cấm>                        ← bắt buộc
   ```

   Vế THÌ bắt đầu bằng động từ: *đóng băng · cắt · dừng · đàm phán lại · chuyển · tuyển*. **Cấm** dùng: *xem xét, cân nhắc, đánh giá lại, theo dõi thêm*.
3. (7') Vế **KHÔNG THÌ**: tự hỏi *"khi đèn này đỏ, phản xạ đầu tiên của tôi là gì?"* rồi cấm nó. Gợi ý: B2C → đổ thêm tiền ads · B2B → giảm giá · B2B2C → ký thêm partner.
4. (5') Đếm lại: **≥2 luật dừng** (dừng chi tiêu, dừng ký partner, dừng bán, dừng nhận khách). Đánh dấu ⏹.

**Ví dụ đạt:**

> **NẾU** đường cong retention chưa phẳng sau D30 **TRONG** 2 cohort liên tiếp **VÀ** mỗi cohort ≥200 user **THÌ** đóng băng toàn bộ chi tiêu acquisition 3 tuần, cả đội quay về làm activation **KHÔNG THÌ** không được tăng ngân sách ads để bù churn. ⏹

**Ví dụ không đạt:** *"Nếu retention thấp thì xem xét lại sản phẩm."* — thấp là bao nhiêu, đo bao lâu, làm gì, cấm gì?

**Cần hiểu:** viết luật **trước** khi đèn đỏ, vì lúc đèn đỏ là lúc bạn hoảng.

**Tự kiểm tra**
- [ ] 5 luật, mỗi luật đủ NẾU / TRONG-TRÊN / THÌ / KHÔNG THÌ.
- [ ] Hành động đủ nhỏ để đội 3 người làm được thứ Hai tuần sau.
- [ ] ≥2 luật dừng, đã đánh dấu ⏹.
- [ ] Bí? Chạy **Prompt 5.3** (Decision Rule Red-Team) và **5.4** (Wrong-Reflex Finder).

---

## Trạm 5 — Cổng gác 90 ngày & ráp dashboard · 20'

**Cần làm**

1. (10') Lấy 3 cổng gác gợi ý của loại mình (cuối [§3.1](HANDBOOK.md#31-b2c--trận-đánh-giữ-chân) / [§3.2](HANDBOOK.md#32-b2b--trận-đánh-rút-ngắn-đường-tới-giá-trị) / [§3.3](HANDBOOK.md#33-b2b2c--trận-đánh-bắt-partner-thực-sự-đẩy)), **thay bằng số của bạn**. Mỗi cổng: **đúng 1** metric · 1 ngưỡng có số · bằng chứng vật lý (file, báo cáo, log) · quyết định nếu trượt (FIX / PIVOT / KILL).
2. (4') Viết **kill criteria**: 1 câu, có số, có ngày.
3. (6') Ráp mọi thứ vào `dashboard.md` và xuất `dashboard.pdf` (trang 1 = dashboard, trang 2 = phụ lục [MH]).

**Cần hiểu:** ngày 30 là cổng **học**, không phải cổng doanh thu. FIX chỉ dùng **một lần** cho cùng một vấn đề — FIX lần hai là PIVOT đang giả trang.

**Tự kiểm tra**
- [ ] Dashboard in ra vừa **đúng một mặt giấy**.
- [ ] 3 cổng đều có metric + ngưỡng + bằng chứng + quyết định; không cổng nào kiểu "có traction tốt".
- [ ] Kill criteria có số và mốc thời gian.
- [ ] Mục "Chưa đo được" có nội dung thật, kèm cần gì để đo và khi nào có số.
- [ ] Bí? Chạy **Prompt 5.6** (90-Day Gate Designer).

Xong? Đi tiếp [SUBMISSION.md](SUBMISSION.md).
