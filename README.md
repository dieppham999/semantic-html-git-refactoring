# Tái cấu trúc giao diện và lịch sử dự án

> Bài thực hành CodeGym – Semantic HTML & Git Commit Strategy

## 1. Giới thiệu

Dự án thực hành cải tiến một landing page sử dụng quá nhiều thẻ `<div>` ("div-soup") thành cấu trúc **Semantic HTML** dễ đọc, dễ bảo trì và giúp công cụ tìm kiếm hiểu vai trò của các vùng nội dung. Đồng thời, dự án áp dụng **Atomic Commits** và **Conventional Commits** để tạo lịch sử Git rõ ràng, có thể kiểm tra và hoàn tác từng thay đổi.

## 2. Mục tiêu

- Nhận diện và sử dụng đúng các thẻ `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`.
- Thay thế ít nhất **80% thẻ `<div>` không mang ý nghĩa ngữ nghĩa** khi phù hợp; vẫn giữ `<div>` cho các nhóm thuần trình bày nếu cần.
- Tổ chức hệ thống tiêu đề hợp lý với `<h1>`, `<h2>`, `<h3>`.
- Phân biệt ba trạng thái Git: **Modified**, **Staged**, **Committed**.
- Ghi lại tối thiểu **4 commits** theo từng khu vực giao diện, sử dụng Conventional Commits.
- Kiểm tra HTML bằng W3C Validator và đẩy dự án lên GitHub.

> Lưu ý: Semantic HTML hỗ trợ khả năng hiểu cấu trúc trang và accessibility; không tự động bảo đảm tăng thứ hạng SEO.

## 3. Cấu trúc dự án

```text
.
├── index.html        # Landing page sau khi tái cấu trúc
├── ai_prompt_log.md  # Nhật ký trao đổi với AI và mục đích sử dụng
└── README.md         # Tài liệu dự án
```

## 4. Sơ đồ Semantic HTML dự kiến

```text
body
├── header
│   └── nav
│       └── ul
│           └── li > a
├── main
│   ├── section (Hero)
│   │   ├── h1
│   │   └── p
│   └── section (Services)
│       ├── h2
│       └── article (mỗi dịch vụ)
│           └── h3
└── footer
    └── Thông tin liên hệ / bản quyền
```

Các thẻ được chọn theo **ý nghĩa nội dung**, không chỉ để thay thế máy móc toàn bộ `<div>`.

## 5. Chiến lược commit

| Thứ tự | Commit message dự kiến | Nội dung |
| --- | --- | --- |
| Khởi tạo | `chore: initialize legacy landing page` | Lưu phiên bản HTML ban đầu để đối chiếu |
| 1 | `refactor: semantic header and navigation` | Thay header, nav và danh sách liên kết điều hướng |
| 2 | `refactor: semantic main and hero section` | Thêm main, chuẩn hóa h1 và mô tả hero |
| 3 | `refactor: semantic services section` | Tổ chức section dịch vụ và các article |
| 4 | `refactor: semantic footer` | Cải thiện cấu trúc footer và liên hệ |

**Quan trọng:** Bảng trên là **kế hoạch**, không phải bằng chứng các commit đã được tạo. Kiểm chứng bằng lịch sử Git thực tế sau khi hoàn thành.

### Kiểm tra lịch sử Git

```bash
git status
git log --oneline --graph --all --decorate
```

- **Modified:** File đã thay đổi nhưng chưa đưa vào staging area.
- **Staged:** Thay đổi đã được `git add`, sẵn sàng để commit.
- **Committed:** Snapshot của các thay đổi đã stage được lưu vào lịch sử repository.
- `git commit -m "message"`: `-m` truyền nội dung thông điệp commit; commit chỉ ghi nhận những thay đổi đã được stage.

## 6. Cách chạy

1. Clone repository từ GitHub (điền URL ở phần Thông tin repository).
2. Mở file `index.html` trực tiếp bằng trình duyệt hoặc dùng tiện ích Live Server trong VS Code.
3. Kiểm tra bố cục, liên kết điều hướng và cấu trúc nội dung.

## 7. Kiểm thử và tiêu chí hoàn thành

- [ ] Các vùng Header, Navigation, Main, Services, Footer sử dụng thẻ HTML ngữ nghĩa phù hợp.
- [ ] Ít nhất 80% thẻ `<div>` vô nghĩa đã được thay thế phù hợp.
- [ ] Cấu trúc tiêu đề h1/h2/h3 hợp lý; liên kết điều hướng nằm trong danh sách ul/li/a.
- [ ] Không có lỗi HTML nghiêm trọng khi kiểm tra bằng [W3C Nu Validator](https://validator.w3.org/nu/).
- [ ] Có tối thiểu 4 commits refactor riêng biệt với Conventional Commits.
- [ ] `git status` sạch trước khi bàn giao.
- [ ] Đã push mã nguồn và lịch sử commit lên GitHub.
- [ ] `ai_prompt_log.md` ghi trung thực các prompt đã dùng và lý do sử dụng.

## 8. Giải thích quyết định kỹ thuật

**Tại sao cần Semantic HTML?** Các thẻ như `<nav>`, `<main>` và `<article>` thể hiện vai trò nội dung rõ hơn `<div>`, hỗ trợ máy đọc màn hình, bảo trì và khả năng phân tích cấu trúc trang của công cụ tìm kiếm.

**Khi nào dùng `<section>` và `<article>`?** `<section>` nhóm nội dung cùng chủ đề, thường có heading. `<article>` phù hợp với nội dung có thể hiểu độc lập, ví dụ từng thẻ dịch vụ có tiêu đề và mô tả riêng.

**Tại sao tách Header và Footer thành hai commits?** Chúng là hai thay đổi độc lập. Commit nhỏ giúp review, xác định lỗi và revert phần cần thiết mà không ảnh hưởng phần còn lại.

**Nếu chỉ `git commit` mà quên `git add` thì sao?** Các thay đổi chưa stage sẽ không được đưa vào commit mới (trừ trường hợp đã được stage trước đó).

## 9. Nhật ký sử dụng AI

Xem file [`ai_prompt_log.md`](./ai_prompt_log.md). Chỉ ghi các câu hỏi và phản hồi đã thực sự trao đổi; không dựng lịch sử prompt giả.

## 10. Thông tin repository

- **GitHub:** `https://github.com/<username>/<repository>` *(cập nhật bằng URL thật)*
- **Nền tảng:** HTML5, Git, GitHub
- **Bài thực hành:** Tái cấu trúc giao diện và lịch sử dự án – CodeGym

---

