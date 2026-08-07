# VS Code 配置完全指南

> 一份从安装到高效开发的完整配置手册，涵盖界面美化、编辑器核心设置、插件推荐及常用操作技巧。

---

## 📑 目录

1. [安装选项](#一安装选项)
2. [界面美化](#二界面美化)
3. [编辑器核心设置](#三编辑器核心设置)
4. [推荐插件](#四推荐插件)
5. [操作技巧与快捷键](#五操作技巧与快捷键)
6. [附录：推荐 settings.json](#六附录推荐-settingsjson)

---

## 一、安装选项

安装过程中，**建议不勾选**以下选项：

> **"将 Code 注册为受支持的文件类型的编辑器"**

### 勾选 vs 不勾选的区别

| 场景 | 勾选 | 不勾选 |
|------|------|--------|
| 双击代码文件 | 自动用 VS Code 打开 | 使用系统默认程序 |
| 文件图标 | 显示为 VS Code 样式 | 保持系统默认 |
| 右键菜单 | 出现"用 VS Code 打开" | 无此快捷选项 |
| 适用人群 | 主力编辑器是 VS Code | 偶尔使用 VS Code |

**建议**：如果你同时使用多个编辑器（如 JetBrains 系列），建议不勾选，避免文件关联冲突。

---

## 二、界面美化

### 2.1 颜色主题

**路径**：`管理` → `主题` → `颜色主题` → **现代浅色**

> 现代浅色主题对比度适中，长时间编码不易疲劳。

### 2.2 文件图标主题

**路径**：`管理` → `主题` → `文件图标主题` → **VSCode Icons**

> 需要先安装 [vscode-icons](https://marketplace.visualstudio.com/items?itemName=vscode-icons-team.vscode-icons) 插件。

### 2.3 视图优化

#### 关闭不常用侧边栏面板

**路径**：`资源管理器` → `视图和更多操作`（三个点）→ 取消勾选：
- [ ] **大纲**
- [ ] **时间线**

> 大纲和时间线会占用侧边栏空间，对于日常开发使用频率较低，建议关闭以保持界面清爽。

#### 关闭编辑器缩略图

**路径**：`查看` → `外观` → 取消勾选 **"缩略图"**

> 缩略图（Minimap）会占用右侧空间，关闭后可获得更多代码编辑区域。

---

## 三、编辑器核心设置

### 3.1 字体与缩放

**路径**：`管理` → `设置` → 搜索 **"字体"**

| 设置项 | 推荐值 | 说明 |
|--------|--------|------|
| 字体大小 | `22` | 根据个人显示器分辨率调整 |
| Mouse Wheel Zoom | ✅ 勾选 | `Ctrl` + 鼠标滚轮实现字体大小缩放 |

### 3.2 缩进设置（Tab Size）

**路径**：`管理` → `设置` → 搜索 **"tab size"**

**推荐值**：`2`

#### 2 格 vs 4 格缩进对比

| 维度 | 2 格缩进 | 4 格缩进 |
|------|----------|----------|
| **视觉密度** | 更紧凑，同屏可见更多层级 | 层级更清晰，适合嵌套深的代码 |
| **屏幕空间** | 行长度更短，适合小屏/分屏 | 占用更多水平空间 |
| **可读性** | 适合层级多但结构简单的代码 | 适合逻辑复杂、嵌套深的代码 |
| **社区惯例** | JavaScript/TypeScript、JSON、Vue、React、HTML/CSS | Python（PEP 8 强制要求）、Java、C/C++、C# |

#### 手动切换缩进

点击右下角状态栏的 **"Tab Size"** 可快速切换当前文件的缩进风格。

#### 配置 settings.json

```json
{
  "editor.tabSize": 2,
  "editor.insertSpaces": true,
  "editor.detectIndentation": true
}
```

> **团队优先原则**：始终跟随项目现有的 `.editorconfig` 或团队规范，保持一致性比个人偏好更重要。

### 3.3 保存时自动格式化

**路径**：`管理` → `设置` → 搜索 **"format on save"** → ✅ 勾选

> 保存文件时自动对齐代码，配合 Prettier 插件效果更佳。

### 3.4 文件夹显示优化

**路径**：`管理` → `设置` → 搜索 **"compact"** → 取消勾选 **"Explorer: Compact Folders"**

#### 效果对比

| Compact Folders | 显示效果 |
|-----------------|----------|
| ✅ 勾选（默认） | `src/utils/helpers` 合并为一行显示 |
| ❌ 不勾选 | `src` → `utils` → `helpers` 分层显示 |

> 建议取消勾选，使目录层级更加直观，避免误操作。

### 3.5 代码折叠标记

VS Code 支持使用区域标记实现代码折叠：

```css
/* #region 样式重置 */
body {
  margin: 0;
  padding: 0;
}
/* #endregion */
```

> 编辑器会在标记旁显示折叠箭头（▶ / ▼），点击即可收起或展开代码块。适用于管理冗长的 CSS 或配置文件。

---

## 四、推荐插件

### 必装插件

| 插件 | 用途 | 说明 |
|------|------|------|
| **Chinese (Simplified) Language Pack** | 简体中文语言包 | 将界面汉化，降低上手门槛 |
| **vscode-icons** | 文件图标美化 | 丰富的文件类型图标，提升辨识度 |
| **Live Server** | 本地开发服务器 | 一键启动，保存自动刷新浏览器 |
| **Error Lens** | 错误高亮 | 将错误/警告直接显示在行尾，无需 hover |

### 其他推荐

| 插件 | 用途 |
|------|------|
| **Prettier** | 代码格式化，支持多语言 |
| **ESLint** | JS/TS 代码规范检查 |
| **Auto Close Tag** | 输入 `<div>` 自动补全 `</div>` |
| **Auto Rename Tag** | 修改开标签时同步修改闭合标签 |
| **Path Intellisense** | 文件路径自动补全 |

### ⚠️ Live Server 使用注意

1. **必须在 VS Code 中打开文件夹**（而非单个文件），否则无法工作
2. 打开的网页需是**标准 HTML 结构**，否则无法自动刷新

---

## 五、操作技巧与快捷键

### 5.1 文件打开方式

VS Code 有两种文件打开模式：

| 操作 | 文件名样式 | 行为 |
|------|-----------|------|
| **单击** | *斜体* | 预览模式，单击新文件会替换当前标签 |
| **双击 / 修改后** | 正常字体 | 固定模式，单击新文件会新开标签页 |

> **技巧**：若想让单击直接固定文件，可设置 `"workbench.editor.enablePreview": false`。

### 5.2 编辑技巧

| 操作 | 效果 |
|------|------|
| `Ctrl + Enter` | 光标直接跳到下一行（不破坏当前行） |
| `Shift + Alt + ↑ / ↓` | 向上/向下复制当前行 |
| `Ctrl + Shift + +` | 界面放大 |
| `Ctrl + Shift + -` | 界面缩小 |

### 5.3 HTML 快速生成

在 `.html` 文件中输入 `!` 后按 `Tab` 或 `Enter`，自动生成 HTML5 模板：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>

</body>
</html>
```

> 这是 VS Code 内置 **Emmet** 功能，无需安装插件。

### 5.4 MDN 文档参考

鼠标停留在 HTML 标签（如 `<h1>`）上，弹出窗口中会显示 **MDN 参考链接**，点击可直接跳转官方文档。

---

## 六、附录：推荐 settings.json

将以下配置添加到 `settings.json` 中，可一次性完成上述核心设置：

```json
{
  // ===== 界面 =====
  "workbench.colorTheme": "Default Light Modern",
  "workbench.iconTheme": "vscode-icons",
  "workbench.editor.enablePreview": false,
  "workbench.editor.minimap.enabled": false,
  "workbench.tree.indent": 16,

  // ===== 字体 =====
  "editor.fontSize": 22,
  "editor.mouseWheelZoom": true,

  // ===== 缩进 =====
  "editor.tabSize": 2,
  "editor.insertSpaces": true,
  "editor.detectIndentation": true,

  // ===== 格式化 =====
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",

  // ===== 资源管理器 =====
  "explorer.compactFolders": false,

  // ===== 其他 =====
  "editor.hover.enabled": true,
  "editor.wordWrap": "on"
}
```

**打开 settings.json 的方法**：
- `Ctrl + Shift + P` → 输入 `Open User Settings (JSON)`

---

*本文档持续更新，建议根据实际开发需求灵活调整配置。*
