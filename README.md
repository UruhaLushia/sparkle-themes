# Sparkle 主题编写

## 文件结构

主题文件放在 `themes/` 目录，使用 `.css` 扩展名。文件第一行的块注释会作为主题名称：

```css
/* 我的主题 */
```

## 明暗模式

分别使用 `.light` / `[data-theme="light"]` 和 `.dark` / `[data-theme="dark"]` 覆盖变量：

```css
.light,
[data-theme="light"] {
  --accent: hsl(340 80% 60%) !important;
}

.dark,
[data-theme="dark"] {
  --accent: hsl(340 75% 70%) !important;
}
```

## 设计变量

常用变量包括：

- `--background`、`--foreground`
- `--surface`、`--surface-secondary`、`--surface-tertiary`
- `--accent`、`--secondary`、`--success`、`--warning`、`--danger`
- `--default` 及 `--default-50` 到 `--default-900`
- 对应的 `-foreground` 变量
- `--border`、`--radius-sm`、`--radius-md`、`--radius-lg`
- `--app-shadow-sm`、`--app-shadow-md`、`--app-shadow-lg`

颜色必须使用完整 CSS 颜色值，例如 `hsl(340 80% 60%)`、`rgb(255 255 255 / 0.8)`、十六进制颜色或渐变。不要使用旧版 `--heroui-*` 变量，也不要写不带 `hsl()` 的色值通道。

## 自定义样式

可以在主题文件中添加普通 CSS 规则，覆盖背景、模糊、边框和组件细节。应用当前使用的主要类包括 `.main`、`.side`、`.bg-surface`、`.bg-surface-secondary` 和 `.outbound-mode-card`。

主题文件会被直接注入主窗口和悬浮窗口，因此自定义选择器应尽量限定范围，避免修改全局交互行为。

## 发布

提交主题文件后，发布工作流会将 `themes/` 目录打包为 `themes.zip`，并更新 `latest` 发布版本。
