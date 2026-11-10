# Tự xuất bản AIRA Content Remake lên GitHub

Hướng dẫn dành cho người muốn đưa bản sao hoặc bản chỉnh sửa của mình lên GitHub. Không cần lập trình. Các bước dựa trên tài liệu GitHub đối chiếu ngày 10/11/2026.

## Tạo repo public

1. Đăng nhập GitHub, chọn **+ → New repository**.
2. Chọn tài khoản sở hữu và tên `aira-content-remake` (hoặc một tên còn trống).
3. Chọn **Public**. Không tạo thêm README hay giấy phép mẫu vì gói đã có sẵn.
4. Chọn **Create repository**.

Nguồn: [Creating a new repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-new-repository).

## Upload gói đã giải nén

1. Giải nén ZIP trên máy.
2. Trong repo trống, chọn liên kết **uploading an existing file**. Với repo đã có file, chọn **Add file → Upload files**.
3. Mở thư mục `aira-content-remake` vừa giải nén. Kéo **các file bên trong và thư mục examples** vào trang upload để `README.md` và `SKILL.md` nằm ngay ở gốc repo.
4. Kiểm tra đủ file, ghi nội dung commit như `Publish AIRA Content Remake public skill`, rồi chọn **Commit changes**.

Nguồn: [Adding a file to a repository](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository).

Chỉ upload các file của gói public. Không kéo cả thư mục dự án hay lịch sử làm việc vào repo.

## Chia sẻ link thật và file cài

- Mở trang repo sau khi upload; sao chép URL trên thanh địa chỉ để chia sẻ. Kiểm tra repo hiển thị **Public** và README xuất hiện.
- Nút **Code → Download ZIP** tải mã nguồn của repo. GitHub thường thêm tên nhánh vào thư mục; sau giải nén, đổi thư mục chứa `SKILL.md` thành `aira-content-remake` trước khi cài.
- Để người nhận có đúng gói cài đã đóng sẵn, có thể thêm ZIP gốc vào một GitHub Release hoặc thư mục `downloads/`. Trỏ link tải trong README tới đúng file đã upload rồi thử tải lại.
- Khi nén lại để upload vào Claude, ZIP phải chứa một thư mục `aira-content-remake`, bên trong có `SKILL.md` và các tài liệu kèm theo; không nén lồng thêm thư mục phiên bản.

Đăng repo công khai không tự niêm yết skill trong kho plugin của Claude hoặc ChatGPT. Người nhận vẫn chọn cách cài trong README.
