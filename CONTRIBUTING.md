# Đóng góp

Ưu tiên sửa hướng dẫn khó hiểu, bổ sung ví dụ tái tạo được hoặc cải thiện một bài thực hành.

Nếu phát hiện một bước không chạy được, mở issue ghi rõ hệ điều hành, phiên bản Git/shell, lệnh đã chạy và kết quả mong đợi. Khi PR giải quyết xong issue, thêm `Closes #N` vào mô tả PR, với `N` là số issue trong cùng repo. GitHub sẽ tự đóng issue khi PR được merge vào nhánh mặc định.

## Quy trình

1. Nếu không có quyền đẩy nhánh vào repo, fork repo về tài khoản của bạn.
2. Clone repo hoặc bản fork. Chạy `git status` và xử lý thay đổi đang có trước khi chuyển nhánh.
3. Từ `main` đã cập nhật, tạo nhánh có tên mô tả mục đích.
4. Thực hiện thay đổi và đọc `git diff`.
5. Chạy thử các lệnh đã sửa trong thư mục thực hành riêng; kiểm tra link tương đối và `git diff --check`.
6. Commit bằng tiếng Việt, sau đó push nhánh và mở pull request.
7. Trong PR, nêu vấn đề, kết quả sau sửa và cách đã kiểm tra. Merge khi thay đổi đáp ứng yêu cầu.

## Commit

Ví dụ:

```text
docs: làm rõ bước cập nhật nhánh sau khi merge
fix: sửa đường dẫn trong bài thực hành hoàn tác
```

Ghi đúng tác giả thực sự tham gia thay đổi. Mỗi PR nên giải quyết một vấn đề rõ ràng.

[Về trang chính](README.md)
