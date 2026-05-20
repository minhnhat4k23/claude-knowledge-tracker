# Setup Guide — Claude Knowledge Tracker

## Tạo Scheduled Routine trong Claude Code

### Bước 1: Mở Claude Code

### Bước 2: Tạo routine
Gõ trong Claude Code:
```
/schedule create
```

Cấu hình:
- **Name**: `claude-knowledge-tracker`
- **Schedule**: `0 10 * * *` (= 10:00 UTC = 17:00 GMT+7)
- **Prompt**: Copy toàn bộ nội dung trong block code ở file `PROMPT.md`
- **Working directory**: `f:\file linh tinh\claude-knowledge-tracker`

### Bước 3: Verify
```
/schedule list
```

## Cấu trúc thư mục

```
claude-knowledge-tracker/
├── PROMPT.md          # Prompt chính cho routine
├── SETUP.md           # File hướng dẫn cài đặt
├── schema.json        # JSON Schema cho output
├── index.json         # Index tất cả daily reports
├── sample.json        # File mẫu tham khảo
└── data/
    ├── 2026-05-20.json
    ├── 2026-05-21.json
    └── ...
```

## Timezone
- 17:00 GMT+7 (Việt Nam) = 10:00 UTC
- Cron expression: `0 10 * * *`

## Troubleshooting

### Routine không chạy
- Kiểm tra máy có internet
- Kiểm tra Claude Code đang chạy
- `/schedule list` để xem last run status

### Không có video mới
- Anthropic không upload video mỗi ngày — file JSON vẫn tạo với `items: []`

### Muốn chạy thủ công
- Mở Claude Code tại thư mục project
- Paste prompt từ PROMPT.md và chạy trực tiếp
