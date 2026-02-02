# 桌面待办 (Desktop Todo)

一款精美的 Windows 桌面待办事项应用，采用现代化设计语言，支持任务紧急度可视化、智能提醒等功能。

![Version](https://img.shields.io/badge/Version-1.0.2-blue)
![Electron](https://img.shields.io/badge/Electron-28.3.3-47848F?logo=electron)
![React](https://img.shields.io/badge/React-18-61DAFB?logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?logo=typescript)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3-06B6D4?logo=tailwindcss)

## 📥 下载安装

前往 [Releases](https://github.com/zero-but-one/DesktopTodo/releases) 页面下载最新版本：

- **Windows**: `DesktopTodo-1.0.2-Windows.exe`

## ✨ 核心特性

### 🎨 精美的视觉设计

- **现代化卡片设计** - 待办卡片采用渐变背景，悬停时显示主题色光晕效果
- **深遂星空渐变** - 优雅的深色主题背景
- **流畅交互动画** - 紧急度指示条悬停变宽、进度条光泽扫过动画
- **操作按钮动画** - 悬停时从右侧滑入显示，点击缩放反馈
- **圆润边角** - 20px 圆角设计，视觉更加柔和

### ⏰ 智能紧急度系统

根据任务剩余时间自动计算紧急程度，并以不同颜色直观展示：

| 剩余时间     | 紧急度   | 颜色       |
| ------------ | -------- | ---------- |
| > 24小时     | 充裕     | 🟢 绿色     |
| 12-24小时    | 较充裕   | 🟢 淡绿色   |
| 3-12小时     | 注意     | 🟡 黄色     |
| 1-3小时      | 较紧急   | 🟠 橙色     |
| 15分钟-1小时 | 紧急     | 🔴 红色     |
| < 15分钟     | 非常紧急 | 🔴 深红闪烁 |
| 已过期       | 过期     | ⚫ 暗红色   |

### 🔔 紧急任务提醒

- 当任务进入红色紧急状态时，自动播放提示音
- 同时弹出 Windows 系统通知，确保不错过重要任务
- 可在设置中开启/关闭此功能

### 🎯 便捷的任务管理

- **快捷时间选择** - 一键设置"一小时后"、"今晚8点"、"明天此时"
- **日历选择器** - 可视化日历，轻松选择截止日期
- **普通任务** - 回车不输入时间即可添加无截止时间的普通任务
- **一键排序** - 按紧急程度排序，最紧急的任务置顶
- **一键清空** - 快速清空所有任务或历史记录
- **过期时间验证** - 防止添加已过期的截止时间

### 🎨 主题定制

提供 5 种精心设计的主题色：

- 💜 靛蓝 (Indigo)
- 💜 紫罗兰 (Violet)
- 💚 翠绿 (Emerald)
- 🧡 珊瑚 (Coral)
- 💗 粉色 (Pink)

### 🖥️ 桌面小部件体验

- **窗口置顶** - 可固定在所有窗口之上
- **智能透明度** - 除待办卡片外的 UI 元素支持透明度调节，卡片始终清晰可见
- **自动收回** - 松开透明度滑块时面板自动收回
- **位置记忆** - 自动保存窗口位置和大小
- **系统托盘** - 最小化到托盘，随时呼出
- **开机自启** - 可选开机自动启动

### 📊 数据管理

- **历史记录** - 查看所有已完成的任务
- **数据导出** - 一键导出 JSON 格式数据备份
- **本地存储** - 数据安全存储在本地

## 🛠️ 技术栈

- **框架**: Electron 28 + React 18
- **语言**: TypeScript 5
- **样式**: Tailwind CSS 3
- **动画**: Framer Motion
- **状态管理**: Zustand
- **存储**: electron-store
- **打包**: electron-builder

## 📦 安装与运行

### 开发模式

```bash
# 安装依赖
npm install

# 启动开发服务器
npm run dev
```

### 构建生产版本

```bash
# 编译
npm run build

# 打包便携版 (portable)
npx electron-builder --win portable

# 打包安装版 (setup)
npx electron-builder --win nsis
```

生成的应用位于 `release/` 目录

## 📁 项目结构

```
desktop-todo/
├── src/
│   ├── main/           # Electron 主进程
│   │   └── index.ts
│   ├── preload/        # 预加载脚本
│   │   └── index.ts
│   ├── renderer/       # React 渲染进程
│   │   ├── components/ # UI 组件
│   │   ├── stores/     # 状态管理
│   │   ├── utils/      # 工具函数
│   │   └── styles/     # 全局样式
│   └── shared/         # 共享类型定义
├── assets/             # 静态资源
└── release/            # 打包输出
```

## 🎯 独特功能亮点

1. **实时紧急度计算** - 每30秒自动更新任务紧急状态，颜色渐变过渡
2. **智能提醒触发** - 仅在任务"首次"进入红色状态时提醒，避免重复打扰
3. **进度条可视化** - 带渐变色和发光效果，悬停时光泽扫过动画
4. **优雅的删除/完成动画** - 任务完成或删除时向右滑出，平滑补位
5. **自动隐藏滚动条** - 仅在滚动时显示，保持界面整洁
6. **智能透明度** - 待办卡片始终保持清晰，其他 UI 元素支持透明度调节
7. **单实例运行** - 仅允许一个实例运行，重复打开会激活已有窗口

## 📄 许可证

MIT License

---

**桌面待办** - 让时间管理更优雅 ✨
