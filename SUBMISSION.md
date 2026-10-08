# Nộp bài

**Bài cá nhân.** Mỗi học viên tự tạo và tự nộp repo của mình.

## 1. Tên repo

```
K4-L3-DAY23-HoVaTen-MSSV-AIProductGrowth
```

Ví dụ: `K4-L3-DAY23-NguyenVanAn-2A20260000-AIProductGrowth`

Viết không dấu, không khoảng trắng, ngăn cách bằng dấu `-`.

## 2. Cấu trúc repo

```
K4-L3-DAY23-HoVaTen-MSSV-AIProductGrowth/
├── README.md        # Họ tên, MSSV, tên sản phẩm, 1 câu chốt loại mô hình
├── worksheet.md     # Trạm 1–4: bảng đèn ✅/🔧/❌, thẻ đèn, ngưỡng, phép tính [MH], 5 luật
├── dashboard.md     # Trạm 5: Operating Dashboard 1 trang
└── dashboard.pdf    # Tối đa 2 trang: trang 1 = dashboard, trang 2 = phụ lục phép tính [MH]
```

| File | Bắt buộc | Ghi chú |
|---|---|---|
| `README.md` | ✅ | Ngắn, 3–5 dòng là đủ |
| `worksheet.md` | ✅ | Bằng chứng cho điểm Threshold & Rule; giữ đủ phép tính |
| `dashboard.md` | ✅ | Bản nguồn của trang 1 |
| `dashboard.pdf` | ✅ | Bản người chấm đọc đầu tiên. Xuất từ `dashboard.md` + phụ lục [MH] |

Cách xuất PDF: mở `dashboard.md` trên VS Code (Markdown Preview) hoặc GitHub → In → *Save as PDF*. Hoặc dán sang Google Docs rồi tải PDF.

## 3. Nơi nộp và deadline

- **Nộp ở đâu:** dán link repo GitHub lên **LMS** đúng bài Day 23.
- **Deadline:** **23:59 (GMT+7) ngày làm lab**, trừ khi key coach thông báo deadline khác trong vòng 48 giờ sau buổi lab.
- Repo phải ở chế độ **public** (hoặc người chấm truy cập được) tại thời điểm chấm.
- Nộp muộn bị trừ điểm — xem [RULES.md](RULES.md).

## 4. Kiểm tra trước khi nộp

- [ ] Tên repo đúng quy tắc ở mục 1.
- [ ] Có đủ 4 file ở mục 2, mở link repo ở chế độ ẩn danh vẫn xem được.
- [ ] Dashboard in ra **vừa đúng một mặt giấy**; PDF tối đa 2 trang.
- [ ] Không đèn nào thiếu ngưỡng; mỗi ngưỡng có ký hiệu nguồn **và** một câu lý do.
- [ ] Ít nhất 2 ngưỡng [MH] có phép tính kèm theo.
- [ ] Mỗi benchmark [BM] có **ngày kiểm tra**.
- [ ] 5 luật, mỗi luật có vế **KHÔNG THÌ**; ít nhất 2 luật **dừng** (⏹).
- [ ] 3 cổng gác đều có metric + ngưỡng + quyết định; kill criteria có số và ngày.
- [ ] Mục "Chưa đo được" viết thật, không để trống cho đẹp.
- [ ] Không có API key, mật khẩu hay số liệu mật chưa ẩn danh (xem [RULES.md](RULES.md)).
