# KixTools Shared Timers

一个轻量级、隐私优先的 Web 应用，用于创建和分享带有唯一 URL 的持久倒计时器。完全单 HTML 文件构建，零依赖，全客户端功能。

![Terminal Theme](https://img.shields.io/badge/Theme-Terminal-green?style=flat-square)
![License](https://img.shields.io/badge/License-GPL%20v3.0-blue?style=flat-square)

**演示站:** [https://timer.kixtools.com/](https://timer.kixtools.com/)

## 项目概述

KixTools Shared Timers 是一款极简计时器应用，专为需要在团队、活动或个人项目中创建、分享和追踪倒计时的用户而设计。该应用完全在浏览器中运行，无需服务器端处理，提供即时创建计时器和跨会话持久化的可分享 URL。

核心特性：
- **单文件架构**：整个应用仅包含一个 HTML 文件（约 15KB）
- **无需后端**：所有功能通过原生 JavaScript 在客户端执行
- **零依赖**：无外部库、框架或 API 调用
- **即时部署**：适用于任何 Web 服务器，也可直接在浏览器中打开
- **跨平台兼容**：在所有现代浏览器和设备上功能一致

## 安全与隐私

此应用通过其架构设计优先保护用户隐私和安全：

### 纯客户端操作
所有计时器计算、数据编码和存储操作完全在用户浏览器内进行。数据不会传输到外部服务器，消除了数据泄露、未授权访问或第三方追踪的风险。

### 无服务器端数据收集
该应用无需后端基础设施，意味着：
- **零服务器日志**：不记录 IP 地址、用户代理或访问模式
- **无分析追踪**：不包含遥测、Cookie 或追踪脚本
- **无用户账户**：不收集注册、身份验证或个人身份信息

### 基于 URL 的计时器编码
计时器数据使用 Base64 编码直接嵌入可分享的 URL 中，确保：
- **临时分享**：计时器信息仅存在于 URL 本身
- **用户控制**：用户决定何时以及与谁分享计时器链接
- **无集中数据库**：计时器数据永不存储在任何服务器上

### 本地存储隐私
最近的计时器仅存储在浏览器的 localStorage 中：
- **设备特定**：计时器历史保留在用户设备上，不进行同步或上传
- **用户可控**：用户可随时清除 localStorage 以删除所有计时器历史
- **无跨设备追踪**：计时器历史不会跟随用户跨浏览器或设备

## 核心功能

### 主要功能
- **灵活时长设置**：配置从 1 秒到 365 天的计时器，精确控制天、时、分、秒
- **可分享 URL**：每个计时器生成唯一、可移植的 URL，包含所有计时器数据
- **实时倒计时**：每秒实时更新，显示准确的剩余时间
- **自动到期检测**：计时器归零时提供视觉和弹窗通知
- **最近计时器管理**：浏览、重新打开和删除之前创建的计时器

### 用户体验
- **终端风格界面**：简洁、无干扰的黑客美学绿黑主题设计
- **响应式布局**：为桌面、平板和移动设备优化
- **全屏模式**：专用全屏视图，突出显示计时器
- **时区感知**：所有时间戳自动在用户本地时区显示
- **键盘快捷键**：Ctrl+C（复制 URL）、F11（全屏）、Esc（关闭弹窗）

### 技术优势
- **无需安装**：直接在任何现代 Web 浏览器中运行
- **离线可用**：加载后，计时器功能在无网络连接时仍可正常使用
- **无状态操作**：无会话、Cookie 或持久服务器连接
- **极低资源占用**：轻量实现，CPU 和内存占用可忽略不计

## 安装说明

### 方式一：GitHub Pages 部署（推荐）
1. Fork 本仓库到你的 GitHub 账户
2. 进入仓库 **Settings** → **Pages**
3. 在 **Source** 下，选择分支（通常为 `main` 或 `master`）
4. 点击 **Save**
5. GitHub 将提供你的部署 URL

### 方式二：本地文件系统
1. 克隆或下载本仓库：
   ```bash
   git clone https://github.com/aixingma/TimerShare.git
   ```
2. 进入项目目录
3. 在 Web 浏览器中直接打开 `index.html`

### 方式三：Web 服务器部署
部署到任何静态托管服务：

**Apache/Nginx：**
```bash
# 将文件复制到 Web 服务器文档根目录
cp -r . /var/www/html/timers/
```

**Python HTTP 服务器（开发用）：**
```bash
# 在端口 8000 上提供当前目录
python3 -m http.server 8000
# 访问 http://localhost:8000
```

**Node.js HTTP 服务器：**
```bash
npx http-server -p 8000
```

### 方式四：云托管
将文件上传到以下平台：
- **Netlify**：拖拽文件到 Netlify 仪表板
- **Vercel**：通过 CLI 或 GitHub 集成部署
- **AWS S3**：上传到启用静态网站托管的 S3 存储桶
- **Cloudflare Pages**：连接仓库或直接上传
- **阿里云 OSS**：对象存储 + 静态网站托管
- **腾讯云 COS**：对象存储 + 静态网站托管

## 使用指南

### 创建计时器

1. **访问应用**：通过你的部署 URL 或本地文件
2. **配置计时器参数**：
   - **计时器标题**：输入描述性名称（如"项目截止"、"会议开始"）
   - **时长**：设置天（0-365）、时（0-23）、分（0-59）、秒（0-59）
3. **开始计时**：点击"🚀 开始计时"按钮
4. **分享计时器**：使用屏幕上显示的生成 URL

### 分享计时器

创建后，计时器可通过以下方式分享：
- **复制 URL 按钮**：点击"📋 复制链接"将链接复制到剪贴板
- **手动分享**：从浏览器地址栏复制 URL
- **直接访问**：接收者可在任何浏览器中打开 URL 查看实时倒计时

### 监控活动计时器

**计时器显示特性：**
- **实时倒计时**：每秒更新，显示 时:分:秒 剩余时间
- **视觉反馈**：计时器过期时变红并脉冲闪烁
- **完成通知**：计时器归零时弹窗提醒
- **全屏选项**：点击"⛶ 全屏"进行全屏倒计时显示

### 管理最近计时器

应用会在本地保存最近 15 个计时器的历史：
1. **查看历史**：最近计时器显示在主屏幕
2. **重新打开**：点击可返回任何之前的计时器
3. **删除**：从本地历史中移除计时器

### 键盘快捷键

| 快捷键 | 操作 |
|--------|------|
| `Ctrl+C` | 复制当前计时器 URL 到剪贴板 |
| `F11` | 切换全屏模式 |
| `Esc` | 关闭弹窗通知 |

## 浏览器兼容性

已在以下浏览器测试验证：
- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Opera 76+
- 移动端浏览器（iOS Safari、Chrome Mobile、Firefox Mobile）

## 多语言支持

本应用支持中英文双语：
- **英文版**：[https://timer.kixtools.com/](https://timer.kixtools.com/)
- **中文版**：[https://timer.kixtools.com/cn/](https://timer.kixtools.com/cn/)

右上角可点击切换语言。

## 文章与 SEO 内容

网站包含 SEO 优化的文章页面：
- [英文文章列表](https://timer.kixtools.com/article/)
- [中文文章列表](https://timer.kixtools.com/cn/article/)

## 贡献

欢迎贡献代码！参与方式：

1. Fork 本仓库
2. 创建功能分支 (`git checkout -b feature/your-feature`)
3. 修改 `index.html`
4. 在多个浏览器中充分测试
5. 提交更改 (`git commit -m '添加你的功能'`)
6. 推送到分支 (`git push origin feature/your-feature`)
7. 提交 Pull Request 并附上详细说明

## 开源协议

本项目基于 GNU General Public License v3.0 协议开源。

## 联系方式

如有问题、建议或功能需求：
- **GitHub Issues**: [https://github.com/aixingma/TimerShare/issues](https://github.com/aixingma/TimerShare/issues)
- **仓库地址**: [https://github.com/aixingma/TimerShare](https://github.com/aixingma/TimerShare)

---

**以隐私和简洁为理念构建** • 无追踪 • 无广告 • 无数据收集
