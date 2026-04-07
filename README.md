# Research Library

> **Quản lý bằng CMS tool** — Dùng `library-cms.html` để thêm/sửa chủ đề và bài viết, export `index.html` tự động. Không cần sửa code tay.

Personal research documentation, organized by topic and published via GitHub Pages.

**Live site:** `https://YOUR_USERNAME.github.io/research-library/`  
**CMS Tool:** `https://YOUR_USERNAME.github.io/research-library/library-cms.html`

---

## Truy Cập CMS Tool

Tool có thể dùng theo **2 cách**:

### Cách 1 — Qua URL (sau khi đã publish lên GitHub Pages)

```
https://YOUR_USERNAME.github.io/research-library/library-cms.html
```

Mở trực tiếp trên trình duyệt bất kỳ. Data được lưu trong `localStorage` của trình duyệt đó.

> ⚠️ Mỗi trình duyệt / máy tính lưu data riêng. Nếu đổi máy, cần Export JSON backup rồi Import lại.

### Cách 2 — Mở file local (không cần internet)

```
Mở file library-cms.html trực tiếp trong trình duyệt (double-click hoặc kéo vào browser)
```

---

## Hướng Dẫn Sử Dụng Tool

### Giao diện tổng quan

```
┌─────────────────────────────────────────────────────────┐
│ Library CMS        [Import] [JSON] [💾 Lưu] [⬇ Export] │  ← Topbar
├──────────────┬──────────────────────────────────────────┤
│ Chủ đề       │  📊 Stats (Bài viết / Chủ đề / Đang dùng)│
│ + Thêm       │                                          │
│ ──────────   │  📦 Panel từng chủ đề                    │
│ 💻 Dev    1  │    [+ Bài viết] [✏️] [🗑]                │
│ 📜 Lịch Sử 0 │    ▲▼ Card bài viết [✏️] [🗑]           │
│ ...          │                                          │
│ ──────────   │                                          │
│ 💾 Data      │                                          │
│ 📤 Export    │                                          │
│ 📂 Import    │                                          │
│ 🗑 Reset     │                                          │
└──────────────┴──────────────────────────────────────────┘
```

---

### Quản lý Chủ đề (Topic)

**Thêm chủ đề mới:**
```
Sidebar → "+ Thêm"  hoặc  Topbar → "+ Chủ Đề Mới"
→ Điền: Tên, Icon emoji, Màu chính, Màu nền
→ ID tự sinh từ tên (vd: "Triết Học" → "triet_hoc")
→ Lưu Chủ Đề
```

**Sửa chủ đề:**
```
Panel chủ đề → nút ✏️ (góc phải)
→ Sửa tên / icon / màu
→ Cập Nhật
```

**Xoá chủ đề:**
```
Panel chủ đề → nút 🗑
→ Xác nhận → Xoá luôn tất cả bài viết bên trong
```

**Đổi thứ tự chủ đề:**
```
Sidebar → ▲ ▼ bên phải tên chủ đề
```

---

### Quản lý Bài viết (Article)

**Thêm bài viết:**
```
Panel chủ đề → "+ Bài viết"
→ Điền:
  - Tiêu đề        (vd: Unity Runtime — Mono vs CoreCLR)
  - Mô tả ngắn
  - Tên file HTML  (phải khớp với file thật, vd: UnityMonoVSCLR.html)
  - Tag hiển thị   (vd: Unity · .NET)
  - Ngày đăng
  - Chủ đề
→ Lưu Bài Viết
```

**Sửa bài viết:**
```
Card bài viết → nút ✏️
→ Sửa bất kỳ trường nào, kể cả đổi sang chủ đề khác
→ Cập Nhật
```

**Xoá bài viết:**
```
Card bài viết → nút 🗑 → Xác nhận
```

**Đổi thứ tự bài viết:**
```
Card bài viết → ▲ ▼ (góc trái card)
Chỉ đổi thứ tự trong cùng 1 chủ đề
```

---

### Lưu và Export

**💾 Lưu vào trình duyệt (localStorage):**
```
Topbar → "💾 Lưu"  hoặc  Sidebar → "💾 Lưu vào trình duyệt"
→ Data được lưu trong trình duyệt, không mất khi reload trang
→ Status bar hiện "✓ Đã lưu"
```

> Tool cảnh báo nếu đóng tab mà chưa nhấn Lưu.

**📤 Export JSON backup:**
```
Sidebar → "📤 Export JSON backup"
→ Download file library-data.json về máy
→ Dùng để backup hoặc chuyển data sang máy khác
```

**📂 Import JSON backup:**
```
Sidebar → "📂 Import JSON backup"  hoặc  Topbar → "📂 Import JSON"
→ Paste nội dung JSON vào ô text
→ Import (⚠️ ghi đè toàn bộ data hiện tại)
```

**⬇ Export index.html (bước cuối):**
```
Topbar → "⬇ Export index.html"
→ File index.html được download về máy
→ Copy vào repo → git push → GitHub Pages tự rebuild
```

---

### Quy trình đầy đủ mỗi lần update

```
1. Mở tool: https://YOUR_USERNAME.github.io/research-library/library-cms.html
2. Thêm / sửa / xoá chủ đề hoặc bài viết
3. Nhấn "💾 Lưu" để lưu vào trình duyệt
4. Nhấn "⬇ Export index.html" → download về máy
5. Copy index.html + file HTML bài viết mới vào repo
6. git add . && git commit -m "Add: tên bài viết" && git push
7. Chờ ~1 phút → GitHub Pages tự rebuild
```

---

## Structure

```
research-library/
  ├── index.html              ← Homepage (generate bằng CMS tool)
  ├── library-cms.html        ← CMS tool (có thể truy cập qua URL)
  ├── README.md               ← This file
  └── UnityMonoVSCLR.html    ── Dev
```

---

## GitHub Pages Setup (first time only)

**1. Create repo on GitHub**
```
github.com → New Repository
Name: research-library
Visibility: Public
Tick: Add README
```

**2. Clone and copy files**
```bash
git clone https://github.com/YOUR_USERNAME/research-library.git
cp index.html README.md library-cms.html UnityMonoVSCLR.html research-library/
```

**3. Push**
```bash
cd research-library
git add .
git commit -m "Init"
git push origin main
```

**4. Enable GitHub Pages**
```
Repo → Settings → Pages
Source: Deploy from branch → main → / (root) → Save
```

Sau 1–2 phút: `https://YOUR_USERNAME.github.io/research-library/`

---

## Topics

| ID | Topic | Tag class |
|---|---|---|
| `dev` | 💻 Dev | `tag-dev` |
| `history` | 📜 Lịch Sử | `tag-hist` |
| `health` | 🩺 Sức Khỏe | `tag-hlth` |
| `science` | 🔬 Khoa Học | `tag-sci` |
| `psychology` | 🧠 Tâm Lý | `tag-psych` |
| `education` | 🎓 Giáo Dục | `tag-edu` |
| `space` | 🔭 Vũ Trụ | `tag-space` |
| `spiritual` | 🕯️ Tâm Linh | `tag-spir` |
