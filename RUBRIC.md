# Rubric — 100 điểm

Chấm trên `dashboard.pdf`, đối chiếu bằng chứng trong `worksheet.md`.

## Phần bắt buộc — 100 điểm

| # | Tiêu chí | Điểm |
|---|---|---|
| 1 | **Tier Discipline** — xếp đúng tầng, có đèn báo sớm thật | 20 |
| 2 | **Threshold Quality** — ngưỡng có nguồn, có lý do, có suy từ mô hình | 30 |
| 3 | **Decision Rule Quality** — luật dùng được, có vế cấm | 30 |
| 4 | **90-Day Gates** — cổng gác falsifiable | 15 |
| 5 | **Honesty** — trung thực về chỗ chưa đo được | 5 |

### 1. Tier Discipline — 20 điểm

| Cần có | Bằng chứng |
|---|---|
| ≥2 đèn Leading thật, mỗi đèn nêu được **báo trước cho đèn nào** | Cột "Báo trước cho" trong thẻ đèn |
| Định nghĩa chặt tới mức hai người đo ra cùng một số | Trường "định nghĩa" có cả phần **không** đếm |
| ≥1 đèn bắt được chi phí AI trước khi nó hiện ra ở gross margin | Đèn token / inference / cost/job |

**Mất điểm**
- Dashboard có **>50% đèn tầng Lagging** → tối đa **8/20**.
- Chọn sai loại mô hình rõ ràng (mọi dấu hiệu là B2B nhưng ghi B2B2C) → tối đa **10/20**.

### 2. Threshold Quality — 30 điểm

Chấm **lý do**, không chấm con số. Ngưỡng nào cũng đạt điểm tối đa nếu lập luận đứng được.

| Cần có | Bằng chứng |
|---|---|
| Ký hiệu [BM]/[MH]/[TB] cho mọi ngưỡng + 1 câu lý do | Bảng ngưỡng |
| Benchmark có ngày kiểm tra | Cột nguồn |
| ≥2 ngưỡng **suy ngược từ mô hình tài chính / Cost/Job** kèm phép tính | Phụ lục [MH] |

**Mất điểm**
- Ngưỡng không có lý do → **−3 điểm mỗi đèn**.
- Dưới 2 ngưỡng [MH] → **−8 điểm**.
- Benchmark không ghi ngày kiểm tra → **−5 điểm**.
- Trích một con số không truy được về nguồn → tối đa **10/30**.

### 3. Decision Rule Quality — 30 điểm

| Cần có | Bằng chứng |
|---|---|
| Đủ 4 vế NẾU / TRONG-TRÊN / THÌ / KHÔNG THÌ (vế VÀ khi metric dễ nhiễu) | 5 luật |
| Vế THÌ là hành động cụ thể một đội nhỏ làm được tuần sau | Động từ ở vế THÌ |
| Vế KHÔNG THÌ chặn đúng phản xạ sai | Vế KHÔNG THÌ |
| ≥2 luật dừng | Đánh dấu ⏹ |

**Mất điểm**
- Luật kết thúc bằng *"xem xét lại / cân nhắc / theo dõi thêm"* → luật đó **0 điểm**.
- Không có luật dừng nào → **−8 điểm**.
- Thiếu vế KHÔNG THÌ → luật đó tối đa **nửa điểm**.

### 4. 90-Day Gates — 15 điểm

| Cần có | Bằng chứng |
|---|---|
| Mỗi cổng **đúng một** metric, ngưỡng có số | Bảng cổng gác |
| Nêu bằng chứng vật lý phải tồn tại (file, báo cáo, log) | Cột bằng chứng |
| Cổng ngày 30 là cổng **học**, không phải doanh thu | Cổng ngày 30 |
| Kill criteria có số và mốc thời gian | Dòng KILL CRITERIA |

**Mất điểm**
- Cổng dạng "có traction tốt" → cổng đó **0 điểm**.
- Đặt mục tiêu doanh thu ở ngày 30 → **−5 điểm**.

### 5. Honesty — 5 điểm

Mục "Chưa đo được" có nội dung thật, kèm **cần gì để đo** và **khi nào có số**.

**Mất điểm**
- Để trống, hoặc ghi "không có" trong khi dashboard rõ ràng có đèn chưa đo được → **0 điểm**.

## Bonus

Bài này **không có điểm bonus**. Điểm tối đa là 100.

## Xếp loại

| Band | Điểm | Ý nghĩa |
|---|---|---|
| Outstanding | 90–100 | Dán lên tường họp tuần được ngay |
| Strong | 75–89 | Dùng được, cần siết 1–2 ngưỡng hoặc 1 luật |
| Pass | 60–74 | Hiểu hệ thống nhưng ngưỡng còn cảm tính |
| Needs rework | 40–59 | Sai một khái niệm lõi (toàn lagging, hoặc luật không hành động được) |
| Fail | < 40 | Chưa đạt minimum bar |
