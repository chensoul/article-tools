# Changelog

本文件记录 [Article Tools](https://zhijunio.github.io/article-tools/) 仓库的主要变更。版本按日期聚合（无单独发版号时以日期为界）。

## 2026-04-14

### 核心与部署

- **脚本与字体（jsDelivr）**：封面、首页、二维码等页面的第三方脚本与 Web 字体改为通过 **jsDelivr** 加载（如 `html-to-image`、`misans` 分包样式、`@fontsource/noto-serif-sc`、`@fontsource/jetbrains-mono`；二维码页为 `qrcodejs`、`jsqr`）。不再在仓库内保留 `cover/fonts/`、`cover/vendor/` 副本，以减小体积并统一版本；**完全离线打开**需自行改回本地资源或使用私有镜像。
- **`README.md`**：工具路径与能力说明与当前页面一致（含 `cover/index.html`、`editor/index.html`、`qrcode/index.html`）。

### 封面生成器（`cover/index.html`）

#### 新增

- 右栏 **配色**：纯色与渐变色按钮按列对齐（网格布局）；新增 **午夜** 纯色（scheme 13）与渐变色列对应。
- **装饰**：**极简净底**（`clean`）等装饰选项（在既有极简几何 / 赛博 / 球体 / 简约风基础上迭代）。
- **本地保存**：使用 `localStorage`（`article-tools-cover-v1`）防抖保存封面参数，顶栏提示「已存本地」；重置时清除存储。
- **字体**：右栏 **字体 Font** 下拉可选：**思源宋体 Noto Serif**、**小米 MiSans**、**JetBrains Mono**、**系统黑体**；预设可带字体并在应用预设时切换。Noto / JetBrains 使用 `@fontsource` woff2；MiSans 使用 `misans` 包分包 CSS（`font-family: MiSans`，字重 330 等与分包一致）。

#### 变更

- **预设**：切换预设时不再整体重置文案与滑块，仅应用配色、装饰、可见性及同步内容/滑块显示。
- **作者**：默认字号 **1.9 cqi**；各比例预设中的作者字号与之一致调整。
- **可见性**：字段旁按钮文案改为「隐藏 / 显示」，与当前是否显示一致。
- **复制图片**：失败时提示中补充 HTTPS / localhost 与剪贴板权限说明。

---

如需按 [语义化版本](https://semver.org/) 发版，可将上表某一日期切块为 `v1.x.x` 并在本文件顶部增加对应标题与链接。
