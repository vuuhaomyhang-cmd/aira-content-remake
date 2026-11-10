# AIRA Content Remake

**Biến bản nháp thành nội dung tiếng Việt rõ ý, tự nhiên và đúng giọng của bạn.**

Bản public **1.1.0 · 10/11/2026** · Giấy phép [MIT](LICENSE).

**[Tải gói ZIP v1.1.0](https://github.com/vuuhaomyhang-cmd/aira-content-remake/raw/refs/heads/main/downloads/aira-content-remake-v1.1.0.zip)** · [Xem repo public](https://github.com/vuuhaomyhang-cmd/aira-content-remake)

Skill giữ thông điệp và điều kiện của nội dung gốc, cải thiện hook, cách dẫn ý và nhịp câu. Dùng cho bài social, lời thoại video hoặc biên tập bài đã viết. Không cam kết viral, doanh thu hay kết quả cố định.

## Bắt đầu trong một phút

1. Tải ZIP và giải nén. Thư mục cần dùng có tên `aira-content-remake`.
2. Chọn cách cài ở bảng dưới. Nếu giao diện không hỗ trợ Skills, dùng [hướng dẫn dự phòng](FALLBACK.md).
3. Gửi yêu cầu cùng nội dung thật của bạn:

```text
Dùng AIRA Content Remake. Viết lại nội dung dưới đây thành bài Facebook
khoảng 250 từ cho người mới ứng dụng AI. Giọng gần gũi, xưng mình/bạn.
Giữ ý chính và giới hạn của thông tin gốc; không thêm câu chuyện cá nhân.
Nội dung: [Dán bản nháp của bạn vào đây]
```

`[Dán bản nháp...]` là chỗ bạn thay bằng nội dung của mình.

## Tương thích đã đối chiếu ngày 10/11/2026

| Môi trường | Cách dùng |
| --- | --- |
| Claude có Skills | Upload ZIP tại Customize → Skills; bật tính năng cần thiết. |
| Claude Code chạy cục bộ | Chép thư mục vào `.claude/skills/`; gọi `/aira-content-remake`. |
| Codex | Chép vào `.agents/skills/`; gọi `$aira-content-remake`. |
| ChatGPT desktop có Skills | Dùng luồng quản lý skill đang được tài khoản cung cấp. |
| ChatGPT/GPT không có cài skill | Dán hoặc đính kèm hướng dẫn theo [FALLBACK.md](FALLBACK.md). |
| Ứng dụng GPT qua API | Nhà phát triển cần tích hợp cơ chế Skills của môi trường chạy. |

Đây là tương thích về định dạng và hướng dẫn dựa trên tài liệu, **chưa phải chứng nhận đã cài thử trên mọi tài khoản**. Cùng một mô hình GPT có thể chạy trong các sản phẩm với khả năng cài khác nhau. ZIP này là gói skill, chưa phải plugin được niêm yết.

### Claude

Bật **Code execution and file creation** (có giao diện gọi là **Create and edit files**). Trong **Customize → Skills**, chọn **+ → Create skill → Upload a skill**, tải ZIP lên và bật skill. Tài khoản tổ chức có thể cần quản trị viên bật tính năng. [Hướng dẫn chính thức](https://support.claude.com/en/articles/12512180-use-skills-in-claude).

Với Claude Code cục bộ, vị trí file là `.claude/skills/aira-content-remake/SKILL.md` trong dự án, hoặc `~/.claude/skills/aira-content-remake/SKILL.md` cho cá nhân. Gọi `/aira-content-remake` kèm nội dung cần sửa. Các phiên Cowork/cloud không đọc thư mục cá nhân này trên máy; quản lý skill của các phiên đó qua tài khoản Claude. [Claude Code Skills](https://code.claude.com/docs/en/skills).

### Codex và ChatGPT

Với Codex, chép thư mục để có `.agents/skills/aira-content-remake/SKILL.md` trong dự án, hoặc `~/.agents/skills/aira-content-remake/SKILL.md` dùng cá nhân. Gọi `$aira-content-remake`; mở lại ứng dụng nếu chưa nhận.

Tài liệu OpenAI xác nhận standalone skills trên desktop, CLI và IDE; plugin phân phối skill rộng hơn. ChatGPT chọn skill qua `@` khi khả dụng. **Không mặc định có nút nhập ZIP trên mọi giao diện.** Nếu không có luồng cài phù hợp, dùng fallback. [Build skills](https://learn.chatgpt.com/docs/build-skills).

Với API, nhà phát triển tích hợp Skills vào công cụ shell của Responses API hoặc môi trường Agents API. Chỉ gửi tên skill vào một lời gọi mô hình không tự cài gói. [OpenAI API Skills](https://developers.openai.com/api/docs/guides/tools-skills).

## Bên trong gói

```text
aira-content-remake/
├── SKILL.md
├── README.md
├── FALLBACK.md
├── GITHUB-UPLOAD.md
├── LICENSE
└── examples/
    ├── 01-social.md
    ├── 02-video.md
    └── 03-check-cases.md
```

[SKILL.md](SKILL.md) dùng YAML frontmatter và Markdown theo [Agent Skills specification](https://agentskills.io/specification). Gói chỉ có văn bản, không cần API key, script, tài khoản AIRA hay plugin riêng.

Xem [bài social trước/sau](examples/01-social.md), [lời thoại video](examples/02-video.md) và [các ca thử](examples/03-check-cases.md). Ví dụ được tự tạo để minh họa, không trích từ khách hàng hay lịch sử trò chuyện riêng.

## Khi dùng chưa đúng ý

- Không thấy skill: kiểm tra đúng tên `SKILL.md`, đúng thư mục và tránh lồng hai thư mục cùng tên. Với ZIP, bên trong phải có một thư mục `aira-content-remake` chứa các file.
- Không đọc được link: dán phần nội dung cần remake; skill không tự cấp quyền truy cập trang web.
- Giọng chưa đúng: chỉ ra câu gượng và gửi một đoạn mẫu được phép sử dụng.
- Bài thêm dữ kiện: yêu cầu bỏ chi tiết không có nguồn; kiểm tra trước khi đăng.
- Muốn sửa bài: gửi nhận xét cụ thể như “giữ mở bài, nối đoạn 2–3 và bỏ CTA”.

## Phạm vi public và giấy phép

Bản này chỉ chứa quy trình biên tập có thể chia sẻ và ví dụ mới. Không đóng gói lịch sử chat, dữ liệu khách hàng, bài mẫu riêng, thông tin liên hệ, tài khoản, khóa truy cập hoặc cấu hình nội bộ. Nội dung đầu vào của người dùng không tự trở thành tài liệu public.

Giấy phép MIT cho phép sử dụng, sửa và phân phối, kể cả thương mại, với điều kiện giữ thông báo bản quyền và giấy phép. Giấy phép áp dụng cho các file của gói; không cấp quyền đối với tài liệu bên thứ ba bạn đưa vào. Khi giới thiệu, ghi nguồn HẰNG AIRA và không ngụ ý AIRA bảo chứng cho bản sửa đổi hay nội dung của bạn.

Muốn tự xuất bản repo? Làm theo [GITHUB-UPLOAD.md](GITHUB-UPLOAD.md).
