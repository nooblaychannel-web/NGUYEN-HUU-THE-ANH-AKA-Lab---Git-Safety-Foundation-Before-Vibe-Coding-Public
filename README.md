# AKA Lab - Git Safety Foundation Before Vibe Coding

Repository này được tạo ra nhằm mục đích thực hành và xây dựng nền tảng sử dụng Git & GitHub an toàn, chuẩn bị cho quá trình Vibe Coding với AI.

## 2. Mô tả chi tiết quá trình thực thi kho lưu trữ (Repository)

### 1. M1 - Git Basics
Git là hệ thống quản lý phiên bản phân tán (Distributed Version Control System). Module này tập trung vào việc hiểu cách hoạt động của hệ thống và tạo dấu mốc đầu tiên cho dự án:
* **Version Control (Quản lý phiên bản):** Hệ thống ghi lại lịch sử thay đổi của các file theo thời gian, giúp quay lại trạng thái cũ khi cần thiết.
* **Repository (Repo):** Kho lưu trữ chứa toàn bộ mã nguồn và lịch sử thiết lập của dự án dưới sự giám sát của Git. Khởi tạo bằng lệnh `git init` và kết nối với GitHub.
* **Commit:** Ảnh chụp trạng thái (Snapshot) tại một thời điểm cụ thể nhằm lưu lại các tiến trình mã nguồn một cách an toàn.
* **Log:** Nhật ký hiển thị lịch sử của toàn bộ các commit đã được thực hiện trong dự án.
* **Minh chứng thực hành:** Đã khởi tạo thành công local repository đầu tiên và tạo một commit khởi tạo thành công (Initial commit) chứa file cấu hình cơ bản.

### 2. M2 - GitHub Flow
Quy trình làm việc nhóm và quản lý luồng code chuẩn trên nền tảng đám mây GitHub:
* **Branching (Phân nhánh):** Luôn tạo một nhánh mới độc lập (ví dụ: `feature/tinh-nang-1`) tách biệt khỏi nhánh `main` khi viết tính năng mới để tránh làm ảnh hưởng tới mã nguồn chính.
* **Pull Request (PR):** Đẩy nhánh tính năng lên GitHub và mở yêu cầu kéo mã nguồn (Pull Request) để thảo luận, rà soát chất lượng code (Code Review).
* **Merge:** Hợp nhất mã nguồn từ nhánh tính năng vào nhánh `main` sau khi đã kiểm tra kỹ lưỡng.
* **Conflict (Xung đột):** Xảy ra khi hai nhánh cùng sửa đổi một dòng code trên cùng một file. Cách xử lý là mở file, thủ công chọn mã nguồn chính xác nhất, xóa bỏ các ký hiệu xung đột (`<<<<<<<`, `=======`, `>>>>>>>`) và tạo commit merge để hoàn tất.
* **Minh chứng thực hành:** Đã tạo thành công một nhánh tính năng riêng biệt, đẩy lên GitHub và thực hiện mở Pull Request gộp thành công vào nhánh `main`.

### 3. M3 - Safe Vibe Coding Practice
Khi phát triển dự án bằng phương pháp Vibe Coding (sử dụng AI như ChatGPT, Gemini, Copilot để sinh mã nguồn nhanh), việc kiểm soát rủi ro là tối quan trọng:
* **Kiểm soát code AI sinh:** AI có thể tạo ra mã nguồn chạy sai hoặc chứa lỗ hổng. Quy trình an toàn bắt buộc phải chia nhỏ tính năng, sử dụng GitHub Copilot qua câu lệnh (Prompt) rõ ràng, nhấn `Tab` để nhận mã, tạo commit theo từng bước nhỏ để dễ cô lập lỗi và thực hiện code review nghiêm ngặt trước khi merge.
* **Rollback & Revert (Sửa sai an toàn):** Khi code do AI sinh ra làm crash hệ thống, chúng ta áp dụng cơ chế "quay xe" an toàn bằng `git reset` hoặc `git revert`.
* **Minh chứng thực hành:** Hoàn thành 100% bài thực hành Rollback/Revert để gỡ bỏ đoạn code lỗi do AI tạo ra một cách an toàn, đóng ticket xử lý khủng hoảng thành công.

### 4. M4 - Final Review
Bước nghiệm thu cuối cùng để hoàn thành khóa học:
* **Nộp minh chứng:** Đóng gói toàn bộ mã nguồn dự án, lịch sử commit sạch, danh sách PR đã merge và trạng thái đóng các issue an toàn lên hệ thống quản lý học tập (Hub/aka).
* **Mentor đánh giá:** Mentor trực tiếp rà soát cấu trúc mã nguồn, tư duy phân nhánh, quản lý nâng cao (Secret Scanning, Dependabot, GitHub Projects) và khả năng xử lý lỗi Git thực tế.
* **Kết quả:** Hệ thống và Mentor xác nhận trạng thái đạt yêu cầu: **Passed**.

---

## 3. Danh sách lệnh Git cốt lõi đã làm chủ
* `git clone <url>`: Tải kho lưu trữ từ trên mạng về máy tính cục bộ.
* `git checkout -b <tên-nhánh>`: Tạo một nhánh tính năng mới độc lập và chuyển sang nhánh đó.
* `git checkout <tên-nhánh>`: Di chuyển qua lại giữa các nhánh.
* `git add .`: Đưa toàn bộ các file thay đổi vào vùng đệm (Staging Area) chuẩn bị cam kết.
* `git commit -m "tin_nhắn"`: Tạo ảnh chụp trạng thái (Snapshot) lưu lại dấu mốc lịch sử code sạch.
* `git pull`: Kéo và cập nhật toàn bộ thay đổi mới nhất từ GitHub về máy.
* `git push`: Đẩy các commit an toàn từ máy cục bộ lên kho chứa trên GitHub.
* `git reset --hard origin/main`: Khôi phục cưỡng bức trạng thái máy local sạch sẽ theo remote.
* `git revert <commit-id>`: Tạo commit đảo ngược để hủy bỏ một commit lỗi đã lên remote.
* `git log --oneline`: Xem nhật ký lịch sử commit dưới dạng một dòng ngắn gọn, tường minh.
* `git blame <tên-file>`: Kiểm tra chi tiết từng dòng code để xem ai là người sửa đổi cuối cùng.

---

## 4. Thu hoạch & Tư duy nền tảng trước khi Vibe Coding
1. **Luôn cô lập mã nguồn:** Không bao giờ code trực tiếp trên nhánh `main`. Phải luôn tạo nhánh tính năng độc lập khi làm việc với AI để tránh làm crash hệ thống chính.
2. **Quản lý prompt hiệu quả:** Chất lượng code đầu ra của GitHub Copilot phụ thuộc hoàn toàn vào cách bạn thiết kế câu lệnh (Prompt). Prompt càng chi tiết, đủ ngữ cảnh, thuật toán sinh ra càng chuẩn xác.
3. **Commit nhỏ và thường xuyên:** Chia nhỏ tính năng để commit. Khi AI sinh code sai, chúng ta có thể dễ dàng dùng `revert` hoặc `reset` để "quay xe" mà không ảnh hưởng đến các phần code đúng khác.
4. **Quy trình duyệt nghiêm ngặt:** Luôn sử dụng Pull Request, điền mô tả chi tiết, kiểm tra kỹ lưỡng các xung đột và bật các công cụ bảo mật tự động trước khi tích hợp mã nguồn vào nhánh sản phẩm chính.
