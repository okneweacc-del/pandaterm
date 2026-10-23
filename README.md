# PandaTerm 🐼

PandaTerm là một terminal emulator cho Windows với giao diện tuỳ biến cao: nền trong suốt kiểu Mica/Acrylic, theme màu phong phú, banner neofetch-style, và hỗ trợ nhiều loại shell.

![platform](https://img.shields.io/badge/platform-Windows%2010%2F11-blue)
![status](https://img.shields.io/badge/status-binary%20release-lightgrey)

## ✨ Tính năng

- **Giao diện kính mờ (glass)**: hỗ trợ `mica`, `acrylic`, `tabbed` trên Windows 11, tự động fallback sang theme đặc (solid) trên Windows 10.
- **Theme có sẵn**: `default`, `dracula`, `nord`, `solarized`, `matrix`, `neon`, `rainbow`, `light`, `liquid_glass` — hoặc tự tạo theme JSON riêng.
- **Nhiều loại shell**: `pandash` (built-in command set riêng), `powershell`, `pwsh`, `cmd`, `wsl`, hoặc trỏ tới bất kỳ executable nào.
- **Chế độ pseudo-terminal (PTY)** tự động cho các chương trình tương tác như `python`, `node`, `vim`, `ssh`, `powershell`...
- **Neofetch/Linux mode**: hiển thị logo ASCII/braille cho nhiều distro (Arch, Debian, Fedora, Kali, Ubuntu, NixOS, macOS, Windows, và cả panda logo riêng).
- **Nền tuỳ chỉnh**: ảnh tĩnh, GIF động, video, hoặc màu phẳng, với opacity/blur/brightness điều chỉnh được.
- **Tích hợp Spotify** qua OAuth redirect cục bộ (`http://127.0.0.1:<port>/callback`).
- **Tối ưu hiệu năng**: 3 chế độ `eco` / `balanced` / `max` để cân bằng giữa hiệu ứng hình ảnh và FPS.

## 📦 Cài đặt

1. Tải bản release mới nhất (hoặc build/giải nén thư mục `PandaTerm/`).
2. Chạy `pandaterm.exe`.

Không cần cài đặt gì thêm — ứng dụng chạy độc lập (portable), các đường dẫn tương đối trong `config.json` được tính từ thư mục chứa file `.exe`.

### Yêu cầu

- Windows 10 hoặc 11 (64-bit).
- Để dùng chế độ PTY đầy đủ với Python, cần Python đã cài trên máy (có thể khai báo đường dẫn thủ công trong `config.json` qua `python_path`, hoặc để trống để tự động dò tìm).

## ⚙️ Cấu hình

Toàn bộ cấu hình nằm trong [`config.json`](./config.json) (hỗ trợ comment `//`). Một số mục chính:

| Mục | Mô tả |
|---|---|
| `window` | Kích thước cửa sổ, bo góc, hiệu ứng kính (`glass_backdrop`) |
| `theme` | Theme đang dùng, lấy từ thư mục `themes/` |
| `terminal.default_shell` | Shell mặc định: `pandash`, `powershell`, `pwsh`, `cmd`, `wsl`, hoặc đường dẫn chương trình |
| `terminal.pty` | `auto` / `always` / `never` — điều khiển khi nào dùng pseudo-terminal thật |
| `background` | Loại nền (`image` / `gif` / `video` / `color` / `off`) và các thuộc tính liên quan |
| `neofetch` | Logo, số dòng hiển thị, bảng màu |
| `linux` | Bật chế độ giả lập hiển thị theo phong cách Linux distro |
| `spotify.port` | Cổng redirect cho tích hợp Spotify |
| `os_fallback` | Hành vi hiển thị trên Windows 10 khi không hỗ trợ Mica/Acrylic |

Xem file `config.json` mẫu đi kèm để biết đầy đủ các tuỳ chọn và giá trị mặc định.

## 🎨 Tạo theme riêng

Theme là file JSON đặt trong thư mục `themes/`, ví dụ:

```json
{
  "name": "default",
  "background_color": "#1c1c1e",
  "text_color": "#d4d4d4",
  "prompt_color": "#4ec9b0",
  "error_color": "#f14c4c",
  "suggest_color": "#e5c07b",
  "tab_active_color": "#3a3a3f",
  "tab_inactive_color": "#26262a",
  "border_color": "#3c3c3c",
  "font_name": "Consolas",
  "font_size": 16,
  "animation_speed": 1.0,
  "effects": []
}
```

Đặt tên file trùng với tên theme muốn dùng rồi khai báo trong `config.json` → `"theme": "ten_theme"`.

## 🗂 Cấu trúc thư mục

```
PandaTerm/
├── pandaterm.exe
├── config.json
├── assets/
│   ├── icon.ico, tab.ico
│   ├── panda_dark.png, panda_light.png
│   └── logos/            # Logo ASCII cho chế độ neofetch (Arch, Debian, Kali, macOS, Windows, ...)
└── themes/                # Các theme JSON có sẵn
```

## 🙏 Credits

- Logo ASCII trong `assets/logos/` sử dụng bộ logo tương thích với [fastfetch](https://github.com/fastfetch-cli/fastfetch) (xem `LICENSE-fastfetch.txt`).

## 📄 License

Phát hành theo giấy phép [MIT](./LICENSE).