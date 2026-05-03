# Imagen-Qwen — 阿里云百炼 AI 图像生成技能

[English](README_EN.md)

自然语言生成高质量图像的 Claude Code / OpenClaw 技能，支持中文文字渲染和写实摄影。

## 为什么选择这个技能？

| 特性 | 本技能 | 原生 Claude Code | 其他图像技能 |
|------|--------|-----------------|-------------|
| **中文文字渲染** | ✓ 通义千问专项优化 | ✗ 无图像生成能力 | 部分支持 |
| **写实摄影级图像** | ✓ 通义万相多模型 | ✗ 无图像生成能力 | 部分支持 |
| **多模型可选** | ✓ 8 个模型按需切换 | ✗ 不适用 | 通常单模型 |
| **多尺寸预设** | ✓ 7+ 尺寸比例 | ✗ 不适用 | 部分支持 |
| **负面提示词** | ✓ 精细控制 | ✗ 不适用 | 部分支持 |
| **命令行直接调用** | ✓ 脚本即用 | ✗ 不适用 | 需自行编写 |
| **多区域 API** | ✓ 中国/新加坡/弗吉尼亚 | ✗ 不适用 | 通常单区域 |

**核心优势：**
- **中文文字最佳** — 通义千问是目前在图像上渲染中文效果最好的模型之一
- **写实+艺术兼备** — 通义万相系列覆盖从快速草稿到专业级输出
- **即装即用** — `pip install` 两个包 + 一个 API 密钥即可开始

## 特性

- **通义千问 (Qwen-Image)**: 擅长在图像上渲染复杂的中英文文本
- **通义万相 (Wan Series)**: 写实图像和摄影级视觉效果
- **多种尺寸预设**: 1:1, 16:9, 9:16, 4:3, 3:4 等
- **跨平台**: 支持 Windows, macOS, Linux
- **多区域 API**: 中国（默认）、新加坡、弗吉尼亚

## 安装技能

**Claude Code（全局）：**
```bash
git clone https://github.com/Agents365-ai/imagen-qwen.git ~/.claude/skills/imagen-qwen
```

**Claude Code（仅当前项目）：**
```bash
git clone https://github.com/Agents365-ai/imagen-qwen.git .claude/skills/imagen-qwen
```

**OpenClaw：**
```bash
git clone https://github.com/Agents365-ai/imagen-qwen.git skills/imagen-qwen
```

**SkillsMP：** 在 [skillsmp.com](https://skillsmp.com) 搜索 `imagen-qwen`，一键安装。

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

### 自然语言（Claude Code）

直接告诉 Claude 你想要什么：

```
生成一只可爱的橘猫图片
创建一张带有"新年快乐"文字的海报
用 wan2.6-t2i 模型生成一张写实的山间日落照片
生成一张 16:9 的风景壁纸
```

### 命令行

```bash
# 基本用法（默认模型: qwen-image-plus）
python ~/.claude/skills/imagen-qwen/scripts/generate_image.py "一只可爱的猫咪" output.png

# 使用 Wan 模型生成写实图像
python ~/.claude/skills/imagen-qwen/scripts/generate_image.py --model wan2.6-t2i "山间日落" photo.png

# 自定义尺寸
python ~/.claude/skills/imagen-qwen/scripts/generate_image.py --size 16:9 "宽屏风景" landscape.png

# 使用负面提示词
python ~/.claude/skills/imagen-qwen/scripts/generate_image.py --negative "模糊" "高质量人像" portrait.png

# 列出可用模型
python ~/.claude/skills/imagen-qwen/scripts/generate_image.py --list-models
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
| `wanx2.0-t2i-turbo` | 早期版本 |

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

如果这个项目对你有帮助，欢迎支持作者：

<table>
  <tr>
    <td align="center">
      <img src="https://raw.githubusercontent.com/Agents365-ai/images_payment/main/qrcode/wechat-pay.png" width="180" alt="微信支付">
      <br>
      <b>微信支付</b>
    </td>
    <td align="center">
      <img src="https://raw.githubusercontent.com/Agents365-ai/images_payment/main/qrcode/alipay.png" width="180" alt="支付宝">
      <br>
      <b>支付宝</b>
    </td>
    <td align="center">
      <img src="https://raw.githubusercontent.com/Agents365-ai/images_payment/main/qrcode/buymeacoffee.png" width="180" alt="Buy Me a Coffee">
      <br>
      <b>Buy Me a Coffee</b>
    </td>
  </tr>
</table>

## 作者

**Agents365-ai**

- Bilibili: https://space.bilibili.com/441831884
- GitHub: https://github.com/Agents365-ai
