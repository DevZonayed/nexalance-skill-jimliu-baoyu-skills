# baoyu-skills

[English](./README.md) | 中文

宝玉分享的 Claude Code 技能集，提升日常工作效率。

## 前置要求

- 已安装 Node.js 环境
- 能够运行 `npx bun` 命令

## 安装

### 注册插件市场

在 Claude Code 中运行：

```bash
/plugin marketplace add jimliu/baoyu-skills
```

### 安装技能

**方式一：通过浏览界面**

1. 选择 **Browse and install plugins**
2. 选择 **baoyu-skills**
3. 选择 **content-skills**
4. 选择 **Install now**

**方式二：直接安装**

```bash
/plugin install content-skills@baoyu-skills
```

## 可用技能

### gemini-web

与 Gemini Web 交互，生成文本和图片。

**文本生成：**

```bash
/gemini-web "你好，Gemini"
/gemini-web --prompt "解释量子计算"
```

**图片生成：**

```bash
/gemini-web --prompt "一只可爱的猫" --image cat.png
/gemini-web --promptfiles system.md content.md --image out.png
```

### xhs-images

小红书信息图系列生成器。将内容拆解为 1-10 张卡通风格信息图。

```bash
# 指定文章路径
/xhs-images posts/ai-future/article.md

# 直接输入内容
/xhs-images 今日星座运势
```

### cover-image

为文章生成手绘风格封面图，支持多种风格选项。

```bash
# 从 markdown 文件生成（自动选择风格）
/cover-image path/to/article.md

# 指定风格
/cover-image path/to/article.md --style tech
/cover-image path/to/article.md --style warm

# 不包含标题文字
/cover-image path/to/article.md --no-title
```

可用风格：`elegant`（默认）、`tech`、`warm`、`bold`、`minimal`、`playful`、`nature`、`retro`

### slide-deck

从内容生成专业的幻灯片大纲，包含完整的样式说明。

```bash
# 从 markdown 文件生成
/slide-deck path/to/article.md

# 指定风格和受众
/slide-deck path/to/article.md --style corporate
/slide-deck path/to/article.md --audience executives

# 指定语言
/slide-deck path/to/article.md --lang zh
```

可用风格：`editorial`（默认）、`corporate`、`technical`、`playful`、`minimal`、`storytelling`

## 免责声明

### gemini-web

此技能使用 Gemini Web API（逆向工程）。

**警告：** 本项目通过浏览器 cookies 使用非官方 API。使用风险自负。

- 首次运行会打开 Chrome 进行 Google 身份验证
- Cookies 会被缓存供后续使用
- 不保证 API 的稳定性或可用性

## 许可证

MIT
