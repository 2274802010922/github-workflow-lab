# Bài 02 — Xử lý xung đột

**Mục tiêu:** hiểu vì sao hai nhánh sửa cùng dòng có thể gây conflict.

Các lệnh sau dùng **PowerShell**. Mở terminal tại thư mục cha bên ngoài repo đang làm việc, rồi tạo thư mục thực hành mới. Nếu `conflict-lab` đã tồn tại, chọn tên khác trước khi chạy.

```powershell
New-Item -ItemType Directory conflict-lab -ErrorAction Stop
Set-Location conflict-lab
git init -b main
```

Nếu Git chưa có danh tính, đặt `user.name` và `user.email` của chính bạn bằng `git config` trong repo này. Không dùng `--global` nếu chỉ muốn cấu hình cho bài thực hành.

## 1. Tạo hai thay đổi cạnh tranh

```powershell
Set-Content -Path greeting.txt -Value 'Xin chào'
git add greeting.txt
git commit -m 'chore: tạo lời chào ban đầu'
git switch -c practice/friendly
Set-Content -Path greeting.txt -Value 'Chào bạn!'
git add greeting.txt
git commit -m 'docs: viết lời chào thân thiện'
git switch main
Set-Content -Path greeting.txt -Value 'Xin chào mọi người!'
git add greeting.txt
git commit -m 'docs: chào cả nhóm'
git merge practice/friendly
```

Lệnh cuối dự kiến báo **CONFLICT** và trả mã khác 0. Đây là tình huống bài tập muốn tạo.

## 2. Giải quyết

Chạy `git status`, rồi mở `greeting.txt`. Git đánh dấu hai phiên bản bằng các dòng bắt đầu với `<<<<<<<`, `=======` và `>>>>>>>`.

Chọn nội dung cuối cùng, bỏ toàn bộ dấu conflict. Trong ví dụ này, ghi lời chào kết hợp:

```powershell
Set-Content -Path greeting.txt -Value 'Chào tất cả mọi người!'
git add greeting.txt
git diff --cached
git diff --cached --check
git commit -m 'fix: thống nhất lời chào sau xung đột'
git status
git log --oneline --graph -5
```

**Hoàn thành khi:** working tree sạch, file chứa lời chào đã chọn và lịch sử có commit merge.

Nếu muốn dừng bài tập khi merge vẫn đang xung đột, dùng `git merge --abort` trước bước commit.

[Hướng dẫn GitHub về conflict](https://docs.github.com/en/pull-requests/how-tos/merge-and-close-pull-requests/resolving-a-merge-conflict-using-the-command-line) · [Về danh sách bài](../README.md)
