# OPERATING DASHBOARD — Candidate Ranking

**Loại mô hình:** B2B · **Cập nhật:** 09/10/2026 · Tô Anh Đức – 2A202602639
**NORTH STAR:** TTFV — hiện tại chưa đo (0 org) — mục tiêu ≤ 7 ngày

### Đèn báo sớm (Leading — nhìn hằng ngày/tuần)

| Đèn | Hiện | 🟢 / 🟡 / 🔴 | Nguồn | Báo trước cho |
|---|---|---|---|---|
| TTFV: ngày tạo account → shortlist HR duyệt đầu. Không tính upload hay demo | Chưa đo | 🟢 ≤7 ngày · 🟡 8–30 · 🔴 >30 | [TB] baseline 31/10/2026 | Usage depth, rồi POC → paid |
| Tỷ lệ org dừng vì DPA/security. Không tính org hết nhu cầu tuyển | Chưa đo | 🟢 <10% · 🟡 10–20% · 🔴 >20% | [TB] có số khi ≥5 org, 30/11/2026 | POC → paid |

### Đèn vận hành (Operating — nhìn hằng tuần/tháng)

| Đèn | Hiện | 🟢 / 🟡 / 🔴 | Nguồn | Báo trước cho |
|---|---|---|---|---|
| Cost/Job (LLM+infra+retry+HITL) ÷ job hoàn thành. Không gồm overhead | $0.1013 trên mô hình, chưa đo bill thật | 🟢 ≤$0.128 · 🟡 đến $0.176 · 🔴 >$0.176 | [MH] | Gross Margin |
| Containment: job xong không escalate ÷ job thử | 85% giả định, chưa pilot | 🟢 ≥76,9% · 🟡 67,3–76,9% · 🔴 <67,3% | [MH] | Cost/Job → GM |
| POC → paid trong 90 ngày, mẫu là org đã có shortlist | 0% (0 org trả phí) | 🟢 ≥50% · 🟡 35–50% · 🔴 <35% | [BM] 09/10/2026 | CAC payback |
| Usage depth: JD đang tuyển có screening hoàn tất trong 7 ngày | Chưa đo | 🟢 ≥60% · 🟡 30–60% · 🔴 <30% | [TB] 31/10/2026 | Gia hạn / NRR |

### Đèn kết quả (Lagging — nhìn hằng quý)

| Đèn | Hiện | 🟢 / 🟡 / 🔴 | Nguồn |
|---|---|---|---|
| Gross Margin, COGS chưa overhead | 68,3% trên mô hình, chưa có doanh thu | 🟢 ≥65% · 🟡 60–65% · 🔴 <60% | [MH] |

### 5 luật quyết định (⏹ = luật dừng)

1. ⏹ NẾU TTFV trung vị > 30 ngày TRÊN 3 org gần nhất VÀ mỗi org có ≥1 JD thật THÌ đóng băng pilot mới 14 ngày, cả đội chỉ sửa import → shortlist một JD KHÔNG THÌ không tuyển sales và không thêm tích hợp ATS.
2. ⏹ NẾU org dừng vì DPA/security > 20% TRONG 1 quý VÀ mẫu ≥ 5 org THÌ dừng pilot mới 14 ngày, viết xong Evidence Pack rồi mới mở lại KHÔNG THÌ không giảm giá để bỏ qua DPA.
3. NẾU Cost/Job > $0.176 TRONG 4 tuần VÀ ≥ 200 job hoàn thành THÌ đặt trần độ dài CV trên gói $49, token vượt trần tính riêng KHÔNG THÌ không nhận org mới ở cùng giá $0.32/job.
4. ⏹ NẾU containment < 67,3% TRONG 2 tuần VÀ ≥ 100 job thử THÌ tắt self-serve, giữ tối đa 3 pilot, sửa rubric trên 1 JD mẫu KHÔNG THÌ không đổi định nghĩa job hoàn thành.
5. NẾU usage depth < 30% SAU 60 ngày kể từ shortlist đầu VÀ org có ≥ 3 JD đang tuyển THÌ một người ngồi với HR org đó 2 tuần trước mọi cuộc gia hạn KHÔNG THÌ không bán thêm gói ngành hoặc seat.

### Cổng gác 90 ngày

| Ngày | Metric (1) | Ngưỡng qua cổng | Bằng chứng | Nếu trượt |
|---|---|---|---|---|
| 30 · 08/11/2026 | Số org hoàn tất đúng một vòng: ingest → screening hoàn tất → shortlist HR duyệt | ≥ 3 | Export log ẩn danh Khách A/B/C, có ngày từng bước | FIX: sửa đúng một bước gãy, không onboard thêm org |
| 60 · 08/12/2026 | TTFV | ≤ 7 ngày trên ≥ 2 org | Bảng ngày tạo account và ngày shortlist đầu | FIX nếu cổng 30 không phải lỗi onboarding. PIVOT nếu đã FIX onboarding một lần: đổi bề mặt nhúng, không thêm feature |
| 90 · 07/01/2027 | Containment | ≥ 67,3% trên ≥ 300 job thử | Pilot Report ghi tử số và mẫu số | KILL |

**KILL CRITERIA:** Nếu đến 07/01/2027 containment vẫn dưới 67,3% trên ít nhất 300 job thử sau một lần FIX, dừng sản phẩm và không mở self-serve.

**CHƯA ĐO ĐƯỢC:** TTFV, tỷ lệ dừng security, usage depth, POC → paid, Cost/Job thực, GM thực. Cost/Job $0.1013, containment 85% và GM 68,3% là giả định Day 22, không phải số pilot. Cần log account/shortlist/JD, lý do org dừng, billing, và bill API. Mốc có số vận hành đầu: 31/10/2026 (3 pilot). Mốc security: 30/11/2026. Mốc Pilot Report cho cổng 90: 07/01/2027.
