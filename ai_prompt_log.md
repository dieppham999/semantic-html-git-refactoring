AI Prompt Log — Tái cấu trúc giao diện và lịch sử dự án
Dự án: semantic-html-git-refactoring
Bài thực hành: Tái cấu trúc giao diện và lịch sử dự án (CodeGym)
Công cụ hỗ trợ: ChatGPT

1. Nhật ký câu hỏi và mục đích
STT	Prompt người học gửi AI	Lý do sử dụng AI / kiến thức cần làm rõ
01	“## [Thực hành] Tái cấu trúc giao diện và lịch sử dự án … tóm tắt đề bài” (kèm toàn bộ yêu cầu thực hành).	Xác định mục tiêu, các sản phẩm cần nộp, tiêu chí Semantic HTML và Atomic Commits trước khi triển khai.
02	“tạo file README.md”	Chuẩn bị tài liệu mô tả dự án, cấu trúc trang và chiến lược commit để lưu trong repository.
03	“## [Thực hành] Tái cấu trúc giao diện và lịch sử dự án — đặt tên folder cho project”	Chọn tên thư mục/repository có ý nghĩa và nhất quán với nội dung bài.
04	“css loại bỏ dấu tròn ở ul li”	Hiểu cách reset dấu đầu dòng khi biến menu điều hướng thành danh sách <ul>/<li>.
05	“cách gọi các thẻ từ css”	Học cách chọn phần tử bằng CSS selector: thẻ, class, ID, selector lồng nhau.
06	“nav ul { list-style: none; padding: 0; margin: 0; display: flex; gap: 20px; } — bỏ gạch chân”	Tìm cách loại bỏ gạch chân mặc định của liên kết <a> trong thanh điều hướng.
07	“nav ul { list-style: none; padding: 0; margin: 0; display: flex; gap: 20px; color: white; } — màu text vẫn xanh”	Làm rõ vì sao màu chữ ở <a> không tự đổi theo màu đặt cho <ul>.
08	“cho mẫu css chuyên nghiệp cho menu ngang”	Tham khảo các thuộc tính Flexbox, hover, focus và responsive cho menu; chọn lọc cách áp dụng vào bài.
09	“hướng dẫn mình cố định header”	So sánh position: sticky và position: fixed để chọn cách cố định header.
10	“header đang để style="background: #2c3e50; color: white; padding: 15px 30px; display: flex; justify-content: space-between; align-items: center;" sửa giúp”	Điều chỉnh header hiện có bằng CSS sticky, giữ lại các quy tắc layout đang dùng.
11	“<nav> ... <ul style="display: flex; ..."> ... </ul></nav> — mình muốn nav menu khi hover vào 1 menu thì đổi màu thì làm thế nào” (kèm HTML menu).	Học pseudo-class :hover và vị trí khai báo CSS để đổi màu từng liên kết.
12	“<li><a href="#" style="color: inherit; text-decoration: none; :hover{color: aqua};">Trang Chủ</a></li> — mình sửa có đúng không”	Kiểm tra một giả thuyết sai cú pháp: không thể khai báo :hover trong thuộc tính style inline.
13	“style đặt ở head, mình muốn thêm css hover cho nav menu ở header thì có cần tạo nhánh git khác để thực hiện không”	Phân biệt khi nào cần feature branch với khi nào chỉ cần một atomic commit; cân nhắc chiến lược Git phù hợp bài tập.
14	“<div class="hero-desc" ...>Chúng tôi giúp doanh nghiệp ...</div> — cai nay thi thay the nao semantic cho hop ly”	Chọn thẻ <p> cho đoạn mô tả Hero thay vì lạm dụng <div>.
15	“article dùng thế nào trong thực tế, tôi đang khó phân biệt lúc nào dùng section lúc nào dùng article”	Phân biệt nhóm nội dung theo chủ đề (<section>) và đơn vị nội dung độc lập (<article>).
16	“các thẻ semantic”	Tổng hợp chức năng các thẻ HTML ngữ nghĩa, làm cơ sở phân loại cấu trúc landing page.
17	“<section class="services-container"> ... <div class="services-list"> ... <div class="service-box"> ... </section> — <div class="service-box"> thì có nên thay semantic không” (kèm đầy đủ HTML Services).	Xem xét article cho từng dịch vụ, h2/h3 cho tiêu đề và p cho mô tả.
18	“<div class="services-list"> vậy cái này thì thay semantic gì”	Đánh giá khi nào giữ <div> làm wrapper, khi nào dùng danh sách <ul>/<li> có ngữ nghĩa.
19	“<footer class="footer-area"> ... <section class="footer-info"> ... <section class="copyright"> ... </footer> — sửa thế này có hợp lý không” (kèm HTML Footer).	Phản biện cách dùng <section>, <address>, <p> và heading trong Footer.
20	[Ảnh chụp VS Code Terminal git log] “thoat cai nay the nao”	Hiểu trình phân trang Git (less), cách thoát bằng q và cách dùng --no-pager.
21	“phim tat format code trong vscode”	Sử dụng phím tắt format HTML và chuẩn hóa cách trình bày mã.
22	“Warning: This document has heading elements but none of them has a computed heading level of 1. … <h2 class="company-name" ...>”	Phân tích cảnh báo W3C Validator, kiểm tra cấu trúc cấp tiêu đề và <h1>.
23	[Ảnh VS Code đang merge] “không hiểu đang config ở đâu khi git merge, và hướng sửa thế nào”	Nhận diện CONFLICT (content); phân biệt Current/Incoming; học cách xử lý xung đột HTML.
24	“giữ nguyên Current Change thì bấm cái nào”	Xác định tác dụng của Accept Current Change trước khi quyết định giữ phiên bản nào.
25	“sau đó làm gì”	Làm rõ các bước git status, git add và kết thúc một merge đang bị xung đột.
26	[Ảnh Terminal báo lỗi unmerged files] “bị sao đây nhỉ”	Tìm hiểu vì sao chưa thể merge Footer khi chưa hoàn thành merge Services.
27	[Ảnh Terminal feature/footer conflict] “không merge tiếp footer được”	Phân tích xung đột mới sau khi Services đã merge thành công.
28	[Ảnh VS Code/Terminal còn both modified: index.html] “chưa hiểu lắm, giờ làm thế nào, vẽ minh họa luồng đi”	Yêu cầu sơ đồ quy trình để hiểu thứ tự giải quyết conflict và hoàn tất merge.
29	[Ảnh VS Code tìm <<<<<<< HEAD nhưng không thấy] “nãy bấm apply current gì đó giờ không còn cái gì để bấm rồi”	Chẩn đoán việc editor đã xóa conflict markers sau khi chọn Current nhưng Git vẫn chờ xác nhận.
30	“git merge --abort … git merge --no-ff feature/footer -m "Tích hợp feature/footer vào main." … CONFLICT (content): Merge conflict in index.html”	Cung cấp log Terminal thực tế để nhận hướng dẫn xử lý merge lại đúng trạng thái.
31	“không làm được, không có chọn cái gì cả”	Tìm cách xử lý bằng Terminal hoặc sửa file thủ công khi không thấy giao diện Merge Editor.
32	“ai_prompt_log.md tạo file Lưu lại toàn bộ lịch sử các câu lệnh (prompts) đã trao đổi với AI, kèm theo giải thích ngắn gọn về lý do dùng câu lệnh đó.”	Tổng hợp nhật ký AI thành một tài liệu Markdown để nộp theo yêu cầu bài thực hành.


