# GitHub Workflow Lab

Repo thực hành Git và GitHub của [O Bao Tri](https://github.com/2274802010922).

Mục tiêu: luyện cách tạo nhánh, viết commit rõ ràng, mở pull request, xử lý xung đột và hoàn tác thay đổi.

## Chuẩn bị

- Cài Git và đăng nhập GitHub.
- Clone repo về máy:

```sh
git clone https://github.com/2274802010922/github-workflow-lab.git
cd github-workflow-lab
```

## Quy ước

- Mỗi nhánh giải quyết một bài thực hành hoặc một cải tiến cụ thể.
- Tiêu đề và nội dung commit viết bằng tiếng Việt; có thể giữ prefix `feat:`, `fix:` hoặc `docs:`.
- Đọc diff và kiểm tra kết quả trước khi merge pull request.
- Dùng dữ liệu mẫu trong bài tập.

## Bài thực hành

| Bài | Kết quả cần đạt |
| --- | --- |
| [01. Nhánh và pull request](exercises/01-branches-and-pull-requests.md) | Một thay đổi có mục đích, được kiểm tra và merge qua PR. |
| [02. Xử lý xung đột](exercises/02-resolve-conflicts.md) | Tái tạo xung đột trong repo cục bộ và tự giải quyết. |
| [03. Hoàn tác bằng revert](exercises/03-undo-safely.md) | Đảo ngược một commit bằng commit mới. |

Bài 01 dùng repo này hoặc bản fork của bạn. Bài 02 và 03 dùng thư mục cục bộ riêng, không cần push.

Xem [hướng dẫn đóng góp](CONTRIBUTING.md) trước khi mở PR.
