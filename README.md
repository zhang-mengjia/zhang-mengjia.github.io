# Mengjia Zhang (张梦佳) - Academic Profile

一个现代化的个人学术主页，采用复古 Windows 95 风格设计，展示学术信息、联系方式和多张头像轮播。该项目通过 GitHub Pages 部署，可直接在浏览器中访问。

## 📋 项目概述

本项目是一个功能完整的个人学术主页，集成了响应式设计、交互动画、主题切换等现代 Web 功能，同时保留了经典的复古 UI 风格。支持多种设备屏幕尺寸，提供良好的用户体验。

## 📁 项目结构

```
zhang-mengjia.github.io/
├── index.html              # 主页文件（包含 HTML 和内联 JavaScript）
├── css/
│   └── style.css           # 全局样式表（868+ 行）
├── assets/
│   ├── avatar/             # 头像文件夹（14张头像）
│   │   ├── avatar (1).jpg
│   │   ├── avatar (2).jpg
│   │   ├── ...
│   │   └── avatar (14).jpg
│   ├── icon/               # 图标资源
│   │   └── icon.png        # 网站 favicon
│   └── docs/               # 文档资源
├── README.md               # 项目说明文档
└── .gitignore              # Git 忽略文件配置
```

## ✨ 功能特性

### 核心功能

- 📱 **响应式设计**
  - 完全适配桌面、平板和移动设备
  - 媒体查询断点：768px、480px、360px
  - 灵活的布局系统，自动调整尺寸

- 🎨 **主题切换**
  - 内置亮色和暗色两种主题
  - 平滑的主题过渡动画
  - 使用 CSS 变量存储主题色值

- 🎴 **头像轮播系统**
  - 支持 14 张头像图片
  - 3D 扑克牌式切换动画
  - 多种操作方式：左右箭头、点击图片、指示点导航
  - 循环切换功能（最后一张切换回第一张）
  - Y 轴翻转 + 平移旋转的组合动画效果

- 📋 **联系方式卡片**
  - 微信公众号
  - 邮箱
  - 其他社交平台

- 🖨️ **打印导出**
  - 支持打印为 PDF
  - 专门的打印样式优化

- 🔗 **可交互元素**
  - 菜单栏操作
  - 按钮和链接交互
  - 悬停效果

## 🛠️ 技术栈

- **前端框架**：HTML5 + CSS3 + Vanilla JavaScript
- **设计理念**：复古 Windows 95 风格 UI
- **动画技术**：CSS 3D Transform、Transition、cubic-bezier 缓动函数
- **响应式**：Media Queries（移动优先设计）
- **部署平台**：GitHub Pages
- **版本控制**：Git

## 🚀 快速开始

### 方式一：本地运行

```bash
# 1. 克隆项目到本地
git clone https://github.com/zhang-mengjia/zhang-mengjia.github.io.git

# 2. 进入项目目录
cd zhang-mengjia.github.io

# 3. 使用任何 HTTP 服务器打开（推荐）
# 如果已安装 Python
python -m http.server 8000

# 如果已安装 Node.js
npx http-server

# 4. 在浏览器中打开
# http://localhost:8000
```

### 方式二：直接在浏览器打开

1. 下载项目文件
2. 用浏览器打开 `index.html` 文件即可

### 方式三：访问在线版本

直接访问 GitHub Pages 部署的在线版本：[https://zhang-mengjia.github.io](https://zhang-mengjia.github.io)

## 🎯 使用指南

### 头像切换操作

头像轮播支持三种切换方式：

1. **点击左右箭头**：快速切换到上一张或下一张
2. **点击头像**：点击当前显示的头像，自动切换到下一张（向右循环）
3. **点击指示点**：直接跳转到指定的头像

```
左箭头 ◀ [  卡片式切换头像  ] ▶ 右箭头
              ↑ 点击也能切换 ↑
         ● ● ● ● ... 指示点导航
```

### 主题切换

点击菜单栏 → "View (Switch Theme)" → 在亮色和暗色主题之间切换

### 打印为 PDF

点击菜单栏 → "File (Print to PDF)" → 使用浏览器打印功能保存为 PDF

## 🎨 样式自定义

### 修改基本信息

编辑 `index.html`，找到以下部分修改：

```html
<!-- 修改名字 -->
<h3>Your Name<br><span>Your Chinese Name</span></h3>

<!-- 修改职位 -->
<div>Your Position<br>Your Institution</div>

<!-- 修改联系方式 -->
<div class="contact-card">
  <!-- 修改卡片内容 -->
</div>
```

### 添加或替换头像

1. 将头像文件放入 `assets/avatar/` 文件夹
2. 在 `index.html` 中对应位置添加 img 标签：

```html
<img src="assets/avatar/avatar (15).jpg" alt="Avatar 15" 
     class="avatar-image" data-index="14" onclick="changeAvatar(1)" 
     style="cursor: pointer;">
```

3. 在指示点区域对应添加：

```html
<span class="dot" data-index="14"></span>
```

### 修改颜色和主题

编辑 `css/style.css`，修改 CSS 变量：

```css
:root {
    --win-gray: #c0c0c0;      /* 主色调 */
    --win-light: #dfdfdf;     /* 浅色 */
    --win-dark: #808080;      /* 深色 */
    --blue: #000080;          /* 强调色 */
    /* ... 更多颜色变量 ... */
}

[data-theme="dark"] {
    /* 暗色主题的颜色配置 */
}
```

### 调整动画效果

修改 `css/style.css` 中的头像轮播动画参数：

```css
.avatar-image {
    transition: all 0.6s cubic-bezier(0.68, -0.55, 0.265, 1.55);
    /* 调整 0.6s 改变动画时长 */
    /* 调整 cubic-bezier 改变动画缓动方式 */
}

.avatar-image.exit-left {
    transform: rotateY(-90deg) rotateZ(-8deg) 
               translateX(-60px) translateY(15px) scale(0.92);
    /* 调整各个变换值来改变切牌幅度 */
}
```

## 📐 头像规格

**推荐规格**：
- 尺寸：竖版（5:7 比例）
- 当前容器：195px × 273px
- 推荐上传：600px × 840px（高清）或 1280px × 1792px（超清）
- 格式：JPG、PNG（JPG 文件更小，加载更快）
- 大小：单个文件建议 200-500KB

## 📱 响应式设计

| 屏幕宽度 | 头像尺寸 | 用途 |
|--------|--------|-----|
| ≥ 769px | 195×273px | 桌面和平板 |
| 481-768px | 170×238px | 平板竖屏 |
| 361-480px | 150×210px | 手机横屏 |
| ≤ 360px | 120×168px | 手机竖屏 |

## 🔧 文件说明详解

### index.html（414 行）

主页文件，包含：
- HTML 结构（标题栏、菜单栏、主体布局、侧边栏）
- 内联 JavaScript（变量初始化、事件处理函数）
- 14 张头像和交互元素

### css/style.css（889 行）

完整的样式表，包含：
- CSS 变量和主题定义
- 基础元素样式（body、标题栏、菜单栏等）
- 头像轮播样式（.avatar-image、.avatar-container 等）
- 响应式媒体查询
- 打印样式

### assets/avatar/

14 张头像文件，支持头像轮播展示

### assets/icon/

网站图标和 favicon

## 🌐 部署到 GitHub Pages

```bash
# 1. 在项目目录初始化 Git 仓库
git init

# 2. 添加所有文件
git add .

# 3. 提交
git commit -m "Initial commit: Academic profile website"

# 4. 添加远程仓库（替换为你的 GitHub 用户名）
git remote add origin https://github.com/YOUR-USERNAME/YOUR-USERNAME.github.io.git

# 5. 推送到 main 分支
git push -u origin main

# 6. 等待 1-2 分钟，访问 https://YOUR-USERNAME.github.io
```

## ✅ 浏览器兼容性

| 浏览器 | 兼容性 | 备注 |
|------|------|-----|
| Chrome | ✅ 完全支持 | 推荐 |
| Firefox | ✅ 完全支持 | 推荐 |
| Safari | ✅ 完全支持 | 包括 iOS Safari |
| Edge | ✅ 完全支持 | 推荐 |
| IE 11 | ❌ 不支持 | 使用了 CSS3 3D Transform |

## 📝 常见问题

### Q: 如何更改头像幅度？
A: 编辑 `css/style.css` 中的 `.avatar-image.exit-left` 和 `.avatar-image.exit-right`，调整 `translateX`、`rotateZ` 和 `scale` 的值。

### Q: 如何加快或放慢动画？
A: 修改 `.avatar-image` 中的 `transition` 时间，例如 `0.6s` 改为 `0.3s`（更快）或 `0.9s`（更慢）。

### Q: 如何添加音效或其他交互？
A: 在 `index.html` 的 JavaScript 部分修改 `changeAvatar()` 函数，添加音频播放或其他 DOM 操作。

### Q: 为什么 GitHub Pages 上没有显示动画效果？
A: 使用浏览器的硬刷新（Ctrl+Shift+R 或 Cmd+Shift+R）清除缓存。

## 📄 许可证

个人学术项目

## 👤 关于作者

Mengjia Zhang (张梦佳)
- Ph.D. Student at CIBR & PUMC
- 详见网站主页的联系方式

## 🎓 学习资源

如果你想基于本项目进行学习或二次开发：

- [CSS 3D Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function)
- [Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries)
- [GitHub Pages 文档](https://pages.github.com/)
- [HTML5 最佳实践](https://html.spec.whatwg.org/)

## 🤝 贡献

欢迎提交 Issue 和 Pull Request 来改进本项目！

---

**最后更新**：2026年1月9日
