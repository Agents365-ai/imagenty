# Imagen-Qwen — AI Image Generation with Chinese Text Excellence

[中文文档](README.md)

A Claude Code / OpenClaw skill for AI image generation using Alibaba Cloud Bailian API.

## Why This Skill?

| Feature | This Skill | Native Claude Code | Other Image Skills |
|---------|-----------|-------------------|-------------------|
| **Chinese text rendering** | ✓ Qwen-Image optimized | ✗ No image generation | Partial |
| **Photorealistic images** | ✓ Wan series multi-model | ✗ No image generation | Partial |
| **Multi-model selection** | ✓ 8 models to choose from | ✗ N/A | Usually single model |
| **Size presets** | ✓ 7+ aspect ratios | ✗ N/A | Partial |
| **Negative prompts** | ✓ Fine-grained control | ✗ N/A | Partial |
| **CLI direct invocation** | ✓ Script ready to use | ✗ N/A | Requires custom code |
| **Multi-region API** | ✓ China/Singapore/Virginia | ✗ N/A | Usually single region |

**Key advantages:**
- **Best Chinese text** — Qwen-Image is one of the best models for rendering Chinese text on images
- **Realism + art** — Wan series covers everything from quick drafts to professional-grade output
- **Ready to use** — `pip install` two packages + one API key to get started

## Features

- **Qwen-Image**: Excellent at rendering complex Chinese/English text on images
- **Wan Series**: Photorealistic images and photography-grade visuals
- **Multiple size presets**: 1:1, 16:9, 9:16, 4:3, 3:4, and more
- **Cross-platform**: Windows, macOS, Linux support
- **Multiple API regions**: China (default), Singapore, Virginia

## Install the Skill

**Claude Code (global):**
```bash
git clone https://github.com/Agents365-ai/imagen-qwen.git ~/.claude/skills/imagen-qwen
```

**Claude Code (project-specific):**
```bash
git clone https://github.com/Agents365-ai/imagen-qwen.git .claude/skills/imagen-qwen
```

**OpenClaw:**
```bash
git clone https://github.com/Agents365-ai/imagen-qwen.git skills/imagen-qwen
```

**SkillsMP:** Search `imagen-qwen` on [skillsmp.com](https://skillsmp.com) for one-click install.

## Requirements

### System Requirements

- Python 3.8+
- pip

### Install Dependencies

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

### Natural Language (Claude Code)

Just tell Claude what you want:

```
Generate an image of a cute orange cat
Create a poster with text "Happy New Year" in Chinese
Make a photorealistic mountain sunset photo using wan2.6-t2i
Generate a 16:9 landscape wallpaper
```

### Command Line

```bash
# Basic usage (default model: qwen-image-plus)
python ~/.claude/skills/imagen-qwen/scripts/generate_image.py "A cute cat" output.png

# Photorealistic with Wan model
python ~/.claude/skills/imagen-qwen/scripts/generate_image.py --model wan2.6-t2i "Mountain sunset" photo.png

# Custom size
python ~/.claude/skills/imagen-qwen/scripts/generate_image.py --size 16:9 "Wide landscape" landscape.png

# With negative prompt
python ~/.claude/skills/imagen-qwen/scripts/generate_image.py --negative "blurry" "High quality portrait" portrait.png

# List available models
python ~/.claude/skills/imagen-qwen/scripts/generate_image.py --list-models
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

If this project helps you, consider supporting the author:

<table>
  <tr>
    <td align="center">
      <img src="https://raw.githubusercontent.com/Agents365-ai/images_payment/main/qrcode/wechat-pay.png" width="180" alt="WeChat Pay">
      <br>
      <b>WeChat Pay</b>
    </td>
    <td align="center">
      <img src="https://raw.githubusercontent.com/Agents365-ai/images_payment/main/qrcode/alipay.png" width="180" alt="Alipay">
      <br>
      <b>Alipay</b>
    </td>
    <td align="center">
      <img src="https://raw.githubusercontent.com/Agents365-ai/images_payment/main/qrcode/buymeacoffee.png" width="180" alt="Buy Me a Coffee">
      <br>
      <b>Buy Me a Coffee</b>
    </td>
  </tr>
</table>

## Author

**Agents365-ai**

- Bilibili: https://space.bilibili.com/441831884
- GitHub: https://github.com/Agents365-ai
