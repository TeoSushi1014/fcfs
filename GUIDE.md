# Hướng dẫn nhanh cho thành viên mới

## Bước 1: Cài đặt Git
- Tải Git tại: https://git-scm.com/download/win
- Cấu hình tên và email:
```powershell
git config --global user.name "Tên của bạn"
git config --global user.email "email@example.com"
```

## Bước 2: Nhận lời mời Collaborator
- Kiểm tra email để nhận lời mời từ GitHub
- Chấp nhận lời mời để có quyền truy cập repository

## Bước 3: Clone Repository
```powershell
git clone https://github.com/TeoSushi1014/fcfs.git
cd fcfs
```

## Bước 4: Làm việc cơ bản

### Mỗi lần bắt đầu làm việc:
```powershell
git pull origin main
```

### Sau khi sửa code:
```powershell
git add .
git commit -m "Mô tả thay đổi của bạn"
git push origin main
```

## Các lệnh hữu ích

| Lệnh | Mô tả |
|------|-------|
| `git status` | Xem trạng thái file hiện tại |
| `git log` | Xem lịch sử commit |
| `git diff` | Xem chi tiết thay đổi |
| `git pull origin main` | Lấy code mới nhất |
| `git push origin main` | Đẩy code lên GitHub |

## Khi gặp vấn đề

### "Failed to push"
```powershell
git pull origin main
# Giải quyết xung đột nếu có
git push origin main
```

### Muốn hủy thay đổi chưa commit
```powershell
git checkout -- filename.py
```

### Muốn xem ai đã sửa file
```powershell
git blame filename.py
```

## Liên hệ
Nếu gặp khó khăn, hãy hỏi trong nhóm hoặc tạo Issue trên GitHub!
