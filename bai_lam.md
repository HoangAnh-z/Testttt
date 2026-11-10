# BÀI LÀM –(CHỦ ĐỀ QUẢN LÝ MODEL AI)

- **Mã đề:**
- **Họ tên:** Bùi Hoàng Anh
- **Lớp:** CNTT3
- **Link repository:**
- **Hệ điều hành (Windows/macOS):** macOS

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```bash
# Ghi lần lượt các lệnh đã chạy, mỗi lệnh một dòng
pwd
ls -la
mv tai_lieu_ban_giao.txt docs
mkdir backup
cp data/chi_phi_model_thang_11.xlsx backup
rm model_cache_01.tmp
cd ./logs ; ls -la ; cd ..
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
.		..		.DS_Store	.env		backup		bai_lam.md	data		docs		evidence	logs		web

./backup:
.				..				chi_phi_model_thang_11.xlsx

./data:
.				..				chi_phi_model_thang_11.xlsx

./docs:
.			..			tai_lieu_ban_giao.txt

./evidence:
.	..

./logs:
.		..		inference.log

./web:
.		..		app.js		images		index.html	style.css

./web/images:
.		..		logo-ai-hub.png
```

## 4.3. Lọc log vận hành Model AI

### a) Lệnh lọc các dòng ERROR

```bash
grep "ERROR" logs/inference.log > logs/loi_model.txt
```

### 2 dòng đầu tiên trong logs/loi_model.txt

```text
2026-11-10 08:27:45 ERROR POST /v1/chat/completions model=CLAUDE-35
2026-11-10 08:31:12 ERROR POST /v1/audio/transcriptions model=WHISPER-V3
```

### b) Lệnh đếm số dòng WARNING và kết quả

```bash
grep "WARNING" logs/inference.log | wc -l
```

```text
       5
```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```bash
bash tong_hop.sh
```

### Nội dung file logs/tong_hop.txt

```text
===BAO CAO VAN HANH MODEL AI===
2026-11-10 08:09:18 WARNING POST /v1/embeddings model=LLAMA-2-OLD
2026-11-10 08:16:05 WARNING GET /v1/fine-tune/jobs-legacy
2026-11-10 08:38:29 WARNING GET /images/model-card-v1.png
2026-11-10 09:01:44 WARNING POST /v1/completions model=DAVINCI-002
2026-11-10 09:14:02 WARNING GET /v1/quota/expired-key
       6
```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [ ] README.md: Heading 1, hình ảnh (`![Alt](path)`), mô tả có **in đậm**, _in nghiêng_ và `inline code`, bảng, code block, task list, blockquote
- [ ] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [ ] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | -------------------------- | --------------------------- | -------------- |
| 1   | Network                           | Failed to load resource: the server responded with a status of 404 (Not Found) | Sửa dòng 10 file web/index.html thành :<img src="images/logo-ai-hub.png" alt="Logo" class="logo"> |
| 2   | Console | [Error] ReferenceError: Can't find variable: hienThiBangModel Global Code (app.js:18)                            | Sửa dòng 18 trong web/app.js thành hienThiBangModelAI();               |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context:** Tôi là sinh viên năm nhất chưa học về JS.
- **Expected:** Tôi muốn Web AIHub – Hệ thống Quản lý các Model AI hiển thị dữ liệu Bảng đơn giá Token theo Model AI.
- **Actual:** Hiện tại trang web đang không hiện dữ liệu bảng và Tab Console hiện lỗi [Error] ReferenceError: Can't find variable: hienThiBangModel Global Code (app.js:18)
- **Log:** [Error] ReferenceError: Can't find variable: hienThiBangModel Global Code (app.js:18)

### Câu tìm kiếm Google

```text
(Ghi câu tìm kiếm vào đây – xoá dòng này)
site:stackoverflow.com "ReferenceError"
```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/chi_phi_model_thang_11.xlsx`, không cần ghi vào đây.
