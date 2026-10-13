# Bài 01 — Nhánh và pull request

**Mục tiêu:** đưa một cải tiến tài liệu vào `main` qua pull request.

## 1. Chuẩn bị

Clone repo này nếu bạn có quyền push, hoặc clone bản fork của bạn. Chạy từ thư mục clone:

```sh
git status
git switch main
git pull --ff-only
git switch -c docs/cai-thien-huong-dan
```

Chỉ tiếp tục khi working tree sạch. Nếu nhánh trên đã tồn tại, chọn tên mới hoặc tiếp tục công việc cũ một cách có chủ đích.

## 2. Thực hiện một cải tiến

Chọn một bước đang thiếu giải thích hoặc ví dụ trong tài liệu. Sửa trực tiếp file liên quan, rồi kiểm tra:

```sh
git diff
git diff --check
```

Thử lại hướng dẫn đã sửa. Khi nội dung đúng, dùng `git add` với đường dẫn file cụ thể; ví dụ sau áp dụng khi bạn sửa `README.md`:

```sh
git add README.md
git diff --cached
git commit -m "docs: làm rõ hướng dẫn thực hành"
git push -u origin docs/cai-thien-huong-dan
```

## 3. Mở và merge PR

Trên GitHub, mở **Compare & pull request**, kiểm tra nhánh đích và phần **Files changed**. Nếu dùng fork, xác nhận đúng repo đích trước khi gửi.

Mô tả vấn đề đã sửa và cách kiểm tra. Sau khi các kiểm tra và yêu cầu review của repo được đáp ứng, merge PR.

## 4. Đồng bộ lại

Trong clone có `origin` trỏ đến repo vừa được merge:

```sh
git switch main
git pull --ff-only
git log --oneline -5
```

Nếu PR được merge vào repo gốc còn bạn đang dùng fork, đồng bộ fork trên GitHub bằng **Sync fork**, rồi mới chạy các lệnh trên.

**Hoàn thành khi:** PR có trạng thái **Merged**, nội dung sửa đã có trên nhánh đích và bản clone của bạn được đồng bộ.

[Về danh sách bài](../README.md)
