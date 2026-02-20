# ImagenTY

[中文文档](README_CN.md)

A Claude Code skill for AI image generation using Alibaba Cloud Bailian API.

## Features

- **Qwen-Image (通义千问)**: Excellent at rendering complex Chinese/English text on images
- **Wan Series (通义万相)**: Photorealistic images and photography-grade visuals
- **Multiple size presets**: 1:1, 16:9, 9:16, 4:3, 3:4, and more
- **Cross-platform**: Windows, macOS, Linux support
- **Multiple API regions**: China (default), Singapore, Virginia

## Requirements

### System Requirements

- Python 3.8+
- pip

### Installation

```bash
pip install dashscope requests
```

### API Key

Get your API key from [Alibaba Cloud Bailian Console](https://bailian.console.aliyun.com/)

```bash
export DASHSCOPE_API_KEY="your_api_key"
```

### Optional Environment Variables

```bash
# Set default model (default: qwen-image-plus)
export DASHSCOPE_MODEL="wan2.6-t2i"

# Set API endpoint (default: cn)
export DASHSCOPE_API_BASE="cn"  # or "sg", "us", or full URL
```

## Quick Start

```bash
# Basic usage (default model: qwen-image-plus)
python ~/.claude/skills/imagenty/scripts/generate_image.py "A cute cat" output.png

# Photorealistic with Wan model
python ~/.claude/skills/imagenty/scripts/generate_image.py --model wan2.6-t2i "Mountain sunset" photo.png

# Custom size
python ~/.claude/skills/imagenty/scripts/generate_image.py --size 16:9 "Wide landscape" landscape.png

# With negative prompt
python ~/.claude/skills/imagenty/scripts/generate_image.py --negative "blurry" "High quality portrait" portrait.png

# List available models
python ~/.claude/skills/imagenty/scripts/generate_image.py --list-models
```

## Models

| Model | Best For |
|-------|----------|
| `qwen-image-plus` | Chinese/English text, posters, illustrations |
| `wan2.6-t2i` | Photorealistic photos, portraits |
| `wan2.5-t2i-preview` | High quality art |
| `wan2.2-t2i-flash` | Fast generation |
| `wan2.2-t2i-plus` | Professional tier |
| `wanx2.1-t2i-turbo` | Fast execution |
| `wanx2.1-t2i-plus` | Professional tier |
| `wanx2.0-t2i-turbo` | Earlier generation |

## Size Presets

**Qwen-Image:**
- `1:1` → 1024×1024
- `16:9` → 1664×928
- `9:16` → 928×1664
- `4:3` → 1216×912
- `3:4` → 912×1216

**Wan Series:**
- `1:1` → 1024×1024
- `1:1-large` → 1280×1280
- `16:9` → 1280×720
- `9:16` → 720×1280
- `4:3` → 1200×900
- `3:4` → 900×1200
- `2:1` → 1440×720

## API Endpoints

| Region | Alias | URL |
|--------|-------|-----|
| **China** (default) | `cn` | `https://dashscope.aliyuncs.com/api/v1` |
| Singapore | `sg` | `https://dashscope-intl.aliyuncs.com/api/v1` |
| Virginia | `us` | `https://dashscope-us.aliyuncs.com/api/v1` |

## License

MIT License

## Support

If this project helps you, consider buying me a coffee:

| WeChat Pay | Alipay |
|------------|--------|
| <img src="https://raw.githubusercontent.com/nicobailon/video-podcast-maker/main/assets/wechat-pay.jpg" width="200"> | <img src="https://raw.githubusercontent.com/nicobailon/video-podcast-maker/main/assets/alipay.jpg" width="200"> |

## Author

[Agents365-ai](https://github.com/Agents365-ai)
