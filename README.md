# FCFS Scheduling Algorithm - Bài Tập Nhóm

## Giới thiệu
Repository này chứa implementation của thuật toán First-Come-First-Served (FCFS) scheduling cho môn Hệ Điều Hành.

## Cấu trúc Project
```
fcfs/
├── fcfs.py          # Implementation chính của thuật toán FCFS
├── test.py          # File test cases
├── theory.docx      # Tài liệu lý thuyết
└── README.md        # File này
```

## Hướng dẫn cho thành viên nhóm

### 1. Clone Repository lần đầu
```powershell
git clone https://github.com/TeoSushi1014/fcfs.git
cd fcfs
```

### 2. Quy trình làm việc hàng ngày

#### Trước khi bắt đầu làm việc
**LUÔN** pull code mới nhất để tránh xung đột:
```powershell
git pull origin main
```

#### Sau khi hoàn thành thay đổi
```powershell
# Xem file nào đã thay đổi
git status

# Thêm tất cả file đã thay đổi
git add .

# Hoặc thêm file cụ thể
git add fcfs.py

# Commit với message mô tả rõ ràng
git commit -m "Mô tả ngắn gọn về thay đổi"

# Push lên GitHub
git push origin main
```

### 3. Quy trình làm việc với Branch (Khuyên dùng)

Để tránh xung đột khi nhiều người cùng làm, mỗi người nên làm trên branch riêng:

```powershell
# Tạo branch mới cho tính năng của bạn
git checkout -b feature/ten-tinh-nang

# Làm việc, commit như bình thường
git add .
git commit -m "Implement tính năng X"

# Push branch lên GitHub
git push origin feature/ten-tinh-nang
```

Sau đó vào GitHub tạo Pull Request để các thành viên khác review trước khi merge.

### 4. Giải quyết xung đột

Nếu gặp lỗi khi push (có người khác đã push trước):
```powershell
# Pull code mới nhất
git pull origin main

# Nếu có xung đột, Git sẽ báo
# Mở file bị xung đột, tìm các dấu hiệu:
# <<<<<<< HEAD
# ... code của bạn ...
# =======
# ... code của người khác ...
# >>>>>>> 

# Sửa file, giữ lại code đúng, xóa các dấu hiệu
# Sau đó:
git add .
git commit -m "Resolve conflicts"
git push origin main
```

## Quy tắc làm việc nhóm

1. **LUÔN pull trước khi bắt đầu làm việc**
2. **Commit thường xuyên** với message rõ ràng
3. **Không commit file không cần thiết** (`.pyc`, `__pycache__/`, etc.)
4. **Test code trước khi push**
5. **Thông báo cho nhóm khi có thay đổi lớn**

## Thành viên nhóm
- TeoSushi1014 (Owner)
- [Thêm tên các thành viên khác]

## Liên hệ
Nếu có vấn đề với Git/GitHub, hãy liên hệ trong nhóm hoặc tạo Issue trên GitHub.
