# ImagenTY

[English](README.md)

一个使用阿里云百炼 API 进行 AI 图像生成的 Claude Code 技能。

## 特性

- **通义千问 (Qwen-Image)**: 擅长在图像上渲染复杂的中英文文本
- **通义万相 (Wan Series)**: 写实图像和摄影级视觉效果
- **多种尺寸预设**: 1:1, 16:9, 9:16, 4:3, 3:4 等
- **跨平台**: 支持 Windows, macOS, Linux
- **多区域 API**: 中国（默认）、新加坡、弗吉尼亚

## 系统要求

### 环境要求

- Python 3.8+
- pip

### 安装依赖

```bash
pip install dashscope requests
```

### API 密钥

从[阿里云百炼控制台](https://bailian.console.aliyun.com/)获取 API 密钥

```bash
export DASHSCOPE_API_KEY="your_api_key"
```

### 可选环境变量

```bash
# 设置默认模型（默认: qwen-image-plus）
export DASHSCOPE_MODEL="wan2.6-t2i"

# 设置 API 端点（默认: cn）
export DASHSCOPE_API_BASE="cn"  # 或 "sg", "us", 或完整 URL
```

## 快速开始

```bash
# 基本用法（默认模型: qwen-image-plus）
python ~/.claude/skills/imagenty/scripts/generate_image.py "一只可爱的猫咪" output.png

# 使用 Wan 模型生成写实图像
python ~/.claude/skills/imagenty/scripts/generate_image.py --model wan2.6-t2i "山间日落" photo.png

# 自定义尺寸
python ~/.claude/skills/imagenty/scripts/generate_image.py --size 16:9 "宽屏风景" landscape.png

# 使用负面提示词
python ~/.claude/skills/imagenty/scripts/generate_image.py --negative "模糊" "高质量人像" portrait.png

# 列出可用模型
python ~/.claude/skills/imagenty/scripts/generate_image.py --list-models
```

## 模型

| 模型 | 最佳用途 |
|------|----------|
| `qwen-image-plus` | 中英文文本、海报、插画 |
| `wan2.6-t2i` | 写实照片、人像 |
| `wan2.5-t2i-preview` | 高质量艺术作品 |
| `wan2.2-t2i-flash` | 快速生成 |
| `wan2.2-t2i-plus` | 专业级 |
| `wanx2.1-t2i-turbo` | 快速执行 |
| `wanx2.1-t2i-plus` | 专业级 |

## 尺寸预设

**通义千问:**
- `1:1` → 1024×1024
- `16:9` → 1664×928
- `9:16` → 928×1664
- `4:3` → 1216×912
- `3:4` → 912×1216

**通义万相:**
- `1:1` → 1024×1024
- `1:1-large` → 1280×1280
- `16:9` → 1280×720
- `9:16` → 720×1280
- `4:3` → 1200×900
- `3:4` → 900×1200
- `2:1` → 1440×720

## API 端点

| 地区 | 别名 | URL |
|------|------|-----|
| **中国**（默认） | `cn` | `https://dashscope.aliyuncs.com/api/v1` |
| 新加坡 | `sg` | `https://dashscope-intl.aliyuncs.com/api/v1` |
| 弗吉尼亚 | `us` | `https://dashscope-us.aliyuncs.com/api/v1` |

## 许可证

MIT License

## 支持

如果这个项目对你有帮助，欢迎请我喝杯咖啡：

| 微信支付 | 支付宝 |
|----------|--------|
| <img src="https://raw.githubusercontent.com/nicobailon/video-podcast-maker/main/assets/wechat-pay.jpg" width="200"> | <img src="https://raw.githubusercontent.com/nicobailon/video-podcast-maker/main/assets/alipay.jpg" width="200"> |

## 作者

[Agents365-ai](https://github.com/Agents365-ai)
