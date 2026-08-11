# macOS Mail 风格 Thunderbird 主题

通过 `userChrome.css` 和 `userContent.css` 将 Thunderbird 115+ 的外观改造为类似 macOS Mail 的简洁风格。

## 安装步骤

### 1. 启用自定义样式支持

打开 Thunderbird，进入 `设置 → 高级 → 常规 → 配置编辑器`（或地址栏输入 `about:config`），搜索并设置：

```
toolkit.legacyUserProfileCustomizations.stylesheets = true
```

### 2. 文件已就位

CSS 文件已放入你的 Thunderbird 配置文件目录：

```
C:\Users\xxx\AppData\Roaming\Thunderbird\Profiles\lvrho3o7.default-esr\chrome\
├── userChrome.css      ← 界面样式（侧边栏、工具栏、消息列表等）
└── userContent.css     ← 邮件正文样式（字体、引用、链接等）
```

### 3. 重启 Thunderbird

完全关闭后重新打开 Thunderbird，样式即可生效。

## 自定义调整

### 修改配色

打开 `userChrome.css`，顶部 `:root` 区域定义了所有颜色变量：

| 变量 | 作用 | 默认值 |
|------|------|--------|
| `--mac-accent` | 主题强调色 | `#007aff`（苹果蓝） |
| `--mac-sidebar-bg` | 侧边栏背景 | `#f0f0f5` |
| `--mac-content-bg` | 内容区背景 | `#ffffff` |
| `--mac-radius` | 圆角大小 | `6px` |

### 暗色模式

已内置暗色模式支持，跟随系统主题自动切换。如果你使用 Windows，可以在 `设置 → 个性化 → 颜色` 中切换系统暗色模式来测试。

### 修改字体

两个文件都使用相同的字体栈：
```css
-apple-system, "Segoe UI", "PingFang SC", "Microsoft YaHei", "Helvetica Neue", Arial, sans-serif
```
Windows 上实际会使用 Segoe UI。如需更换，搜索替换即可。

## 注意事项

- 修改 CSS 后需要重启 Thunderbird 才能生效
- 如果某些样式没有生效，可能是 Thunderbird 版本更新导致选择器变化，可以用 Thunderbird 的开发者工具（`Ctrl+Shift+I`）检查元素
- 工作目录的文件和配置文件目录的文件是独立的，修改工作目录的副本后需要手动复制过去
