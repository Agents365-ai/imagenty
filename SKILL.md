# ImagenTY - 阿里云百炼文生图 Skill

## Overview

使用阿里云百炼 (Bailian) 文生图 API 生成图像。**默认使用中国区端点**，适合国内用户。

支持两大模型系列：
- **通义千问 (Qwen-Image)**: 擅长渲染复杂的中英文文本
- **通义万相 (Wan Series)**: 生成写实图像和摄影级视觉效果

**跨平台支持**: Windows, macOS, Linux

## When to Use This Skill

Automatically activate this skill when:
- User requests image generation with Chinese text or calligraphy
- Need photorealistic images or photography-style visuals
- Creating commercial posters, illustrations, or digital art
- User explicitly requests Alibaba Cloud / Bailian / 通义 models
- Any task where AI-generated image with strong Chinese support would be helpful

## Models

### Qwen-Image (通义千问) - Text Rendering Specialist

| Model | Description |
|-------|-------------|
| `qwen-image-plus` | **Default**. Best for Chinese/English text, posters, illustrations |

### Wan Series (通义万相) - Photorealistic Generation

| Model | Description |
|-------|-------------|
| `wan2.6-t2i` | **Recommended**. Latest version, flexible sizing |
| `wan2.5-t2i-preview` | High quality, up to 768×2700 |
| `wan2.2-t2i-flash` | Speed-optimized |
| `wan2.2-t2i-plus` | Professional tier |
| `wanx2.1-t2i-turbo` | Fast execution |
| `wanx2.1-t2i-plus` | Professional tier |
| `wanx2.0-t2i-turbo` | Earlier generation |

## Usage

### Basic Usage

```bash
# Default model (qwen-image-plus)
python ~/.claude/skills/imagenty/scripts/generate_image.py "一只可爱的猫咪" output.png

# Photorealistic with Wan model
python ~/.claude/skills/imagenty/scripts/generate_image.py --model wan2.6-t2i "Realistic photo of mountains at sunset" photo.png
```

### Size Options

```bash
# Use ratio preset
python ~/.claude/skills/imagenty/scripts/generate_image.py --size 16:9 "Wide landscape" landscape.png

# Use exact dimensions
python ~/.claude/skills/imagenty/scripts/generate_image.py --size 1280*720 "Custom size" custom.png
```

### Size Presets

**Qwen-Image:**
- `16:9` → 1664×928
- `9:16` → 928×1664
- `1:1` → 1024×1024
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

### Advanced Options

```bash
# With negative prompt
python ~/.claude/skills/imagenty/scripts/generate_image.py --negative "blurry, low quality" "High quality portrait" portrait.png

# List all models
python ~/.claude/skills/imagenty/scripts/generate_image.py --list-models
```

## Requirements

```bash
pip install dashscope requests
```

## Environment Variables

```bash
# Required - 阿里云百炼 API Key
export DASHSCOPE_API_KEY="your_api_key"

# Optional - 设置默认模型
export DASHSCOPE_MODEL="wan2.6-t2i"

# Optional - 设置 API 端点 (默认中国区)
export DASHSCOPE_API_BASE="cn"  # 或完整 URL
```

获取 API Key: https://bailian.console.aliyun.com/

## API Endpoints

| 地区 | 别名 | URL |
|------|------|-----|
| **中国区** (默认) | `cn` | `https://dashscope.aliyuncs.com/api/v1` |
| 新加坡 | `sg` | `https://dashscope-intl.aliyuncs.com/api/v1` |
| 弗吉尼亚 | `us` | `https://dashscope-us.aliyuncs.com/api/v1` |

```bash
# 切换到新加坡端点
export DASHSCOPE_API_BASE="sg"

# 或使用完整 URL
export DASHSCOPE_API_BASE="https://dashscope-intl.aliyuncs.com/api/v1"
```

## Model Selection Guide

| Use Case | Recommended Model |
|----------|-------------------|
| Chinese text/calligraphy | `qwen-image-plus` |
| English text on images | `qwen-image-plus` |
| Posters with typography | `qwen-image-plus` |
| Photorealistic photos | `wan2.6-t2i` |
| Portrait photography | `wan2.6-t2i` |
| Fast generation | `wan2.2-t2i-flash` |
| High quality art | `wan2.5-t2i-preview` |

## Comparison with Imagen (Gemini)

| Feature | ImagenTY (Bailian) | Imagen (Gemini) |
|---------|-------------------|-----------------|
| Chinese text rendering | Excellent | Good |
| English text rendering | Excellent | Good |
| Photorealistic images | Excellent | Good |
| Speed | Medium | Fast |
| Model variety | 8 models | 3 models |
| Max resolution | 1440×1440 | 2K |

## Examples

### Chinese Poster
```bash
python ~/.claude/skills/imagenty/scripts/generate_image.py \
  "一副精美的中国新年海报，红色背景，金色'恭喜发财'字样，周围环绕烟花和鞭炮" \
  new_year_poster.png
```

### Photorealistic Landscape
```bash
python ~/.claude/skills/imagenty/scripts/generate_image.py \
  --model wan2.6-t2i \
  --size 16:9 \
  "Breathtaking sunset over mountain range, golden hour, professional photography" \
  landscape.png
```

### Product Shot
```bash
python ~/.claude/skills/imagenty/scripts/generate_image.py \
  --model wan2.6-t2i \
  "Professional product photography of a coffee cup on marble surface, studio lighting" \
  product.png
```
