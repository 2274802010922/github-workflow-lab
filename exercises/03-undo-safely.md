# Bài 03 — Hoàn tác bằng revert

**Mục tiêu:** hoàn tác một commit thông thường bằng commit mới, giữ được lịch sử thay đổi.

Các lệnh dùng **PowerShell**. Mở terminal tại thư mục cha bên ngoài repo đang làm việc. Nếu `revert-lab` đã tồn tại, chọn tên khác.

```powershell
New-Item -ItemType Directory revert-lab -ErrorAction Stop
Set-Location revert-lab
git init -b main
```

Nếu Git chưa có danh tính, đặt `user.name` và `user.email` của chính bạn bằng `git config` trong repo này.

## 1. Tạo thay đổi cần hoàn tác

```powershell
Set-Content -Path note.txt -Value 'Phiên bản ban đầu'
git add note.txt
git commit -m 'chore: tạo ghi chú ban đầu'
Set-Content -Path note.txt -Value 'Nội dung cần hoàn tác'
git add note.txt
git commit -m 'docs: thay đổi ghi chú thử nghiệm'
git status
git log --oneline -2
```

## 2. Hoàn tác commit mới nhất

Khi working tree sạch và `HEAD` vẫn là commit đổi ghi chú ở trên:

```powershell
git revert --no-commit HEAD
git diff --cached
git commit -m 'revert: khôi phục ghi chú ban đầu'
Get-Content note.txt
git log --oneline -3
git status
```

`--no-commit` cho phép xem thay đổi trước và tự viết nội dung commit bằng tiếng Việt.

**Hoàn thành khi:** file trở về “Phiên bản ban đầu”, lịch sử vẫn có cả commit thay đổi lẫn commit hoàn tác, working tree sạch.

Bài này chỉ dùng commit thông thường. Hoàn tác merge commit cần chọn parent phù hợp, nên không áp dụng nguyên lệnh trên cho một merge commit.

[Tài liệu git revert](https://git-scm.com/docs/git-revert) · [Về danh sách bài](../README.md)
