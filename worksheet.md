# Worksheet — Candidate Ranking

Họ tên: Tô Anh Đức · MSSV: 2A202602639 · Ngày làm: 09/10/2026

Sản phẩm: trợ lý AI sàng lọc CV. Một job = 1 CV được screening hoàn tất theo JD/rubric đã duyệt (PII đã ẩn, có điểm từng tiêu chí + evidence + recommendation để HR review). Nguồn số: workbook Day 22 `ToAnhDuc_Day22_model.xlsx`, chốt giá API 08/10/2026. Chưa có khách trả phí.

## Trạm 1 — Loại mô hình

**Ba câu hỏi (thực tế hôm nay):**

1. Ai trả tiền? Doanh nghiệp — team HR SME, không phải ứng viên cá nhân.
2. Ai dùng sản phẩm? Chính HR (người trả tiền) tạo JD, import CV, duyệt shortlist. Ứng viên không đăng nhập và không dùng sản phẩm.
3. Có chạm end-user qua partner không? Không. Kênh đã chốt ở Day 22 là PLG (Gmail/CSV), không có partner đứng giữa.

**Câu chốt loại:** Chúng tôi là B2B vì tiền đến từ team HR, người dùng thật là chính HR khi sàng lọc CV, và ứng viên không phải người dùng sản phẩm.

Đèn bật trước của B2B: **time-to-first-value (TTFV)**. Ký hoặc tạo account không phải là thắng; thắng là HR có shortlist dùng được.

**Bảng đèn §3.2 — đánh dấu toàn bộ:**

| Đèn | ✅ / 🔧 / ❌ | Số nằm ở đâu / cần gì để đo |
|---|---|---|
| TTFV | 🔧 | Chưa có org thật. Cần log `account_created` và `shortlist_approved` (HR duyệt hoặc xuất shortlist). Đo trong 3 pilot tháng 1. Có số dự kiến 31/10/2026. |
| Pipeline coverage | ❌ | PLG, không có CRM cơ hội và chưa có doanh thu quý thật. Muốn đo phải định nghĩa cơ hội = org đã tạo JD và import ≥10 CV, rồi mới có tử/mẫu. Chưa có hạn vì chưa có target tiền. |
| % deal chết ở security/procurement | 🔧 | Chưa có. Cần ghi lý do org dừng: DPA, IT/security, hoặc tự bỏ. Mẫu tối thiểu 5 org đã bắt đầu pilot. Có số dự kiến 30/11/2026. |
| POC → paid | 🔧 | 0 org trả phí. Cần billing và mốc "pilot xong" = đã có ≥1 shortlist HR duyệt. Có số sau vòng pricing test, dự kiến 08/12/2026. |
| Sales cycle | ❌ | Day 22 kết luận sales-led bất khả thi: ACV $1,932, CAC có sales lệch khoảng 19 lần ngân sách. Không dựng pipeline sales. Không đo chỉ số này. |
| Usage depth | 🔧 | Cần event JD đang tuyển và screening hoàn tất theo tuần. Có số sau 2 tuần pilot, dự kiến 31/10/2026. |
| Chi phí triển khai ÷ ACV | 🔧 | ACV mô hình = $1,932/năm đã có. Chưa log giờ onboard. Cần timesheet 3 pilot thủ công. Có số dự kiến 31/10/2026. |
| Tập trung doanh thu | ❌ | Doanh thu = 0. Chỉ đo khi có ≥2 org trả phí. |
| NRR | ❌ | Chưa có cohort gia hạn. Sớm nhất sau một quý có khách trả phí. |
| Gross Margin | 🔧 | Công thức và GM mô hình 68,3% nằm ở tab `2_Pricing`. Đó là giả định, chưa có hóa đơn token hay usage thật. |
| CAC payback | 🔧 | Ngân sách CAC $1,320 và payback mục tiêu 12 tháng nằm ở tab `4_Channel_Fit`. CAC thực chi chưa có vì chưa chạy kênh. |

## Trạm 2 — Thẻ đèn

**North Star:** TTFV — hiện tại chưa đo (0 org pilot) — mục tiêu ≤ 7 ngày.

Chọn 7 đèn. Bỏ sales cycle, pipeline, NRR, tập trung doanh thu, CAC payback, chi phí triển khai khỏi trang điều khiển vì chưa có dữ liệu hoặc không phải đòn bẩy của kênh PLG. Thêm 2 đèn của riêng sản phẩm: Cost/Job và containment — đây là chỗ mô hình Day 22 gãy khi AI làm sai.

| # | Tầng | Đèn | Định nghĩa (đếm gì · **không** đếm gì) | Công thức | Nhịp · ai lấy số | Báo trước cho |
|---|---|---|---|---|---|---|
| 1 | L | TTFV | Số ngày từ `account_created` đến lần đầu HR duyệt hoặc xuất shortlist có ≥1 CV screening hoàn tất. **Không** đếm lúc cài xong, upload CV, xem demo, hay tài khoản nội bộ. | Ngày shortlist đầu − ngày tạo account, lấy trung vị các org | Mỗi org · người vận hành pilot, từ log | Usage depth ở tuần 4–8, rồi POC → paid |
| 2 | L | Tỷ lệ dừng ở security/DPA | Org đã bắt đầu pilot (≥1 JD thật) rồi dừng vì chưa có DPA hoặc không qua IT/security. **Không** đếm org tự bỏ vì hết nhu cầu tuyển. | Org dừng vì DPA/security ÷ org đã bắt đầu pilot trong kỳ | Tháng · người vận hành, từ lý do dừng | POC → paid (chậm khoảng 4–8 tuần) |
| 3 | O | Cost/Job | Chi phí đưa 1 CV screening hoàn tất: LLM + speech + infra + retry + HITL QA. **Không** chia cho job chỉ mới thử. **Không** gồm overhead $30/tháng. | (Chi phí các khoản trên trong tháng) ÷ số job hoàn thành | Tuần · tech, từ bill API + log job | Gross Margin của tháng đó |
| 4 | O | Containment | Job AI làm xong, không escalate. Escalate = không đủ điểm + evidence + recommendation, hoặc HR đánh dấu không dùng được. **Không** nới định nghĩa "xong" để kéo tỷ lệ. | Job hoàn tất không escalate ÷ job đã thử | Tuần · tech + HR pilot | Cost/Job, rồi Gross Margin |
| 5 | O | POC → paid | Org đã có ≥1 shortlist HR duyệt và chuyển sang trả phí trong 90 ngày. **Không** đếm org chỉ tạo account. | Org trả phí ÷ org đã xong pilot, cửa sổ 90 ngày | Tháng · người vận hành, từ billing | CAC payback (quý sau, khi có đủ số chi kênh) |
| 6 | O | Usage depth | JD trạng thái đang tuyển có ≥1 CV screening hoàn tất trong 7 ngày. **Không** đếm JD nháp và CV mới upload chưa chấm xong. | JD đang tuyển có screening trong 7 ngày ÷ JD đang tuyển | Tuần · tech, từ event JD | Gia hạn / NRR của quý sau |
| 7 | G | Gross Margin | (Doanh thu − COGS) ÷ doanh thu. COGS = Cost/Job × job hoàn thành, chưa overhead, cùng cách tab `2_Pricing`. | (Doanh thu − COGS) ÷ doanh thu | Quý · người vận hành | Không báo trước đèn nào — đây là bảng điểm |

Đèn chi phí AI là đèn số **3 (Cost/Job)**. Token LLM riêng lẻ khoảng $0.001/job trên giá $0.32, nên đèn token thuần gần như không bao giờ đỏ. Cost/Job gộp HITL và infra mới bắt được lúc containment giảm, trước khi GM quý lộ ra.

## Trạm 3 — Ngưỡng

| # | Đèn | 🟢 | 🟡 | 🔴 | Nguồn | Lý do (1 câu) · ngày kiểm tra nếu [BM] |
|---|---|---|---|---|---|---|
| 1 | TTFV | ≤ 7 ngày | 8–30 ngày | > 30 ngày | [TB] | Chưa có baseline. Handbook để xanh dưới 30 ngày cho B2B có dự án triển khai; PLG Gmail/CSV không có triển khai, ngưỡng đó gần như luôn xanh. Pain moment Day 22 là sáng thứ Hai xử lý CV trong tuần, nên xanh là trong 7 ngày. Đo 2 chu kỳ pilot, chốt baseline 31/10/2026. |
| 2 | Tỷ lệ dừng ở security/DPA | < 10% | 10–20% | > 20% | [TB] | Chưa có chuẩn riêng. Dùng mốc §3.2 làm điểm khởi đầu vì CV có PII và Risk Checklist chưa viết (hạn 18/10/2026). Có số khi đủ ≥5 org, dự kiến 30/11/2026. |
| 3 | Cost/Job | ≤ $0.128 | > $0.128 và ≤ $0.176 | > $0.176 | [MH] | $0.128 là COGS tối đa để giữ GM 60% ở giá $0.32; $0.176 là mức GM còn 45%. Phép tính ở phụ lục [MH] 1. |
| 4 | Containment | ≥ 76,9% | ≥ 67,3% và < 76,9% | < 67,3% | [MH] | 67,3% là containment hòa vốn để GM còn 60%; 76,9% là mức để GM còn 65%. Phép tính ở phụ lục [MH] 2. |
| 5 | POC → paid | ≥ 50% | 35–50% | < 35% | [BM] | ICONIQ, State of Go-to-Market 2026: POC/free-trial → paid khoảng 50% năm 2026, khoảng 36% năm 2025 (HANDBOOK §8.2 mục 8, chốt 27/08/2026). Ngày kiểm tra 09/10/2026, dưới 3 tháng nên giữ số này. Kế hoạch Day 22 đặt paid conversion ≥ 20% ở tháng 2–3 — mức đó nằm dưới ngưỡng đỏ, không dùng làm ngưỡng xanh. |
| 6 | Usage depth | ≥ 60% | 30–60% | < 30% | [TB] | Chưa đo. Dùng mốc §3.2 làm điểm khởi đầu: dưới 30% là đa số JD không được dùng, đúng tín hiệu churn sớm của luật B2B-4. Thay bằng baseline sau 2 tuần pilot, 31/10/2026. |
| 7 | Gross Margin | ≥ 65% | ≥ 60% và < 65% | < 60% | [MH] | 60% là GM mục tiêu trong tab `2_Pricing` (ô breakeven). Dưới 60% là vỡ mục tiêu đó. 65% tương ứng containment 76,9% ở [MH] 2. ICONIQ 2026E khoảng 53% chỉ là mặt bằng ngành, không phải mục tiêu của mô hình này. |

### Phụ lục [MH] — phép tính

Đầu vào chung, từ Day 22 (ô công thức, không sửa):

- Giá bán P = $0.32/job hoàn thành (Hybrid: $49/account/tháng gồm 150 screening, vượt gói $0.32).
- ARPU = $161/tháng. ACV = $1,932/năm. Kiểm tra: ngân sách CAC $1,320.195 = 161 × GM × 12, với GM mô hình 68,331% → 161 × 0.68331 × 12 = $1,320.20.
- Job hoàn thành / tháng (giả định 1 khách) = 500 job thử × containment 85% = 425.
- Cost/Job chưa overhead = $0.1013 = $43.067 / 425. Trong $43.067: LLM $0.525, infra $20, retry $0.042, HITL QA $22.50. Speech = 0. Overhead $30 không đưa vào COGS.
- v = chi phí biến đổi / job thử = $0.041134. q = QA nội bộ / job thử = $0.045. e = chi phí escalate = 0 (biến thể A: HR khách xử lý exception).

**[MH] 1 — Cost/Job**

```
P = 0.32 USD/job
COGS tối đa để GM ≥ 60% = P × (1 − 0.60) = 0.32 × 0.40 = 0.128 USD/job
COGS tối đa để GM ≥ 45% = P × (1 − 0.45) = 0.32 × 0.55 = 0.176 USD/job
Cost/Job mô hình hiện tại = 0.1013 USD/job → GM = 1 − 0.1013/0.32 = 68.3% (đang xanh, nhưng là giả định)

Kết quả → 🟢 ≤ 0.128 · 🟡 > 0.128 và ≤ 0.176 · 🔴 > 0.176
```

**[MH] 2 — Containment**

```
Công thức breakeven trong tab 2_Pricing:
R ≥ (v + q + e) / (P × (1 − GM) + e)

GM mục tiêu 60% (đỏ nếu thủng):
R ≥ (0.041134 + 0.045 + 0) / (0.32 × 0.40 + 0) = 0.086134 / 0.128 = 0.67292 = 67.3%

GM 65% (xanh):
R ≥ 0.086134 / (0.32 × 0.35) = 0.086134 / 0.112 = 0.76905 = 76.9%

Containment giả định hiện tại = 85% → trên 76.9%, đang xanh trên giấy.

Kết quả → 🟢 ≥ 76.9% · 🟡 ≥ 67.3% và < 76.9% · 🔴 < 67.3%
```

**[MH] 3 — Gross Margin**

```
Cùng một mô hình với [MH] 2, đọc ngược từ containment sang GM:
- Containment 76.9% ↔ GM 65% → xanh
- Containment 67.3% ↔ GM 60% → dưới mức này là đỏ
- Dải giữa là vàng

GM mô hình ở containment giả định 85% = 68.3% (tab 2_Pricing).

Kết quả → 🟢 ≥ 65% · 🟡 ≥ 60% và < 65% · 🔴 < 60%
```

## Trạm 4 — 5 luật quyết định

Đánh dấu ⏹ cho luật dừng.

1. ⏹ **NẾU** TTFV trung vị > 30 ngày **TRÊN** 3 org pilot gần nhất **VÀ** mỗi org có ≥1 JD thật (không tính tài khoản nội bộ) **THÌ** đóng băng mọi pilot mới trong 14 ngày và cả đội chỉ sửa luồng import CV → shortlist một JD **KHÔNG THÌ** không tuyển sales và không thêm tích hợp ATS.
2. ⏹ **NẾU** tỷ lệ org dừng vì DPA/security > 20% **TRONG** 1 quý **VÀ** mẫu ≥ 5 org đã bắt đầu pilot **THÌ** dừng nhận pilot mới trong 14 ngày và viết xong Evidence Pack (Eval Results, Risk Checklist, Pilot Report) trước khi mở lại **KHÔNG THÌ** không giảm giá để đổi lấy việc bỏ qua DPA.
3. **NẾU** Cost/Job > $0.176 **TRONG** 4 tuần liên tiếp **VÀ** cửa sổ đó có ≥ 200 job hoàn thành **THÌ** đặt trần độ dài CV trên gói $49 và chuyển phần token vượt trần sang tính riêng **KHÔNG THÌ** không nhận thêm org mới ở cùng giá $0.32/job.
4. ⏹ **NẾU** containment < 67,3% **TRONG** 2 tuần liên tiếp **VÀ** cửa sổ đó có ≥ 100 job thử **THÌ** tắt self-serve công khai, chỉ giữ tối đa 3 pilot, và sửa rubric trên đúng 1 JD mẫu **KHÔNG THÌ** không đổi định nghĩa "job hoàn thành" cho dễ đếm.
5. **NẾU** usage depth < 30% **SAU** 60 ngày kể từ ngày org đó duyệt shortlist đầu **VÀ** org đó có ≥ 3 JD đang tuyển **THÌ** một người ngồi cùng HR org đó 2 tuần để gắn JD thật vào luồng screening, trước mọi cuộc nói gia hạn **KHÔNG THÌ** không bán thêm gói ngành hoặc seat cho org đó.
