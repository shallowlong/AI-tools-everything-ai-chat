# 开发指南
## 👨‍💻 开发说明

### 项目架构

本项目采用现代化的 Electron + Vue 3 架构，具有清晰的前后端分离设计：

```
client/
├── src/
│   ├── main/                    # Electron主进程
│   │   ├── main.js             # 主进程入口，处理窗口管理和IPC
│   │   ├── preload.js          # 预加载脚本，安全地暴露API
│   │   ├── everything-search.js # Everything HTTP API封装
│   │   └── everything-manager.js # Everything自动连接管理
│   ├── renderer/               # Vue 3渲染进程
│   │   ├── components/         # Vue组件
│   │   │   └── ConfigDialog.vue # 配置对话框组件
│   │   ├── App.vue            # 主应用组件
│   │   ├── main.js            # Vue应用入口
│   │   ├── index.html         # HTML模板
│   │   └── style.css          # 全局样式
│   ├── i18n/                  # 国际化配置
│   │   ├── locales/           # 语言文件
│   │   └── index.js           # i18n配置
│   └── database/              # 数据存储（electron-store）
├── package.json               # 项目配置和依赖
├── vite.config.js            # Vite构建配置
├── UI_DESIGN_SPEC_2.0.md     # UI设计规范文档
└── README.md                 # 项目说明文档

leading_web/
├── backend/                  # Web后端
│   ├── server.js             # Node.js服务器
│   └── database/             # SQLite数据库
├── frontend/                 # Web前端
│   ├── src/
│   │   ├── views/            # Vue页面组件
│   │   ├── components/       # Vue组件
│   │   └── main.js           # Vue应用入口
│   └── package.json          # 前端配置
└── README.md                # Web版本说明
```

### 核心技术组件

#### 🎨 前端技术栈

- **Vue 3 Composition API**: 现代化的响应式开发
- **Vite**: 极速的开发服务器和构建工具
- **Vue I18n**: 多语言国际化支持（10种语言）
- **自定义 CSS**: 精心设计的现代化界面，支持玻璃态效果和渐变设计

#### ⚙️ 后端技术栈

- **Electron 37.x**: 跨平台桌面应用框架
- **Node.js**: 后端逻辑处理
- **electron-store**: 配置和数据持久化
- **OpenAI API**: AI智能搜索转换
- **系统托盘**: 系统托盘集成和窗口管理
- **自动更新**: GitHub Releases 自动更新功能

#### 🔍 搜索引擎集成

- **Everything HTTP API**: 高性能本地文件搜索
- **智能查询优化**: 本地和AI双重查询优化
- **自动连接管理**: 智能检测和配置Everything HTTP服务
- **多策略进程管理**: 优雅关闭→强制终止→高级终止的三级进程管理
- **端口配置**: 支持自动和固定端口模式
- **安全认证**: 自动生成用户名密码保护HTTP服务

### 开发环境配置

#### 必要工具

- Node.js 16+
- npm 或 yarn
- Everything 1.4.1+
- VS Code (推荐)

#### 推荐的 VS Code 扩展

```json
{
  "recommendations": [
    "vue.volar",
    "ms-vscode.vscode-typescript-next",
    "bradlc.vscode-tailwindcss",
    "esbenp.prettier-vscode"
  ]
}
```

### 添加新功能

#### 1. 添加新的搜索功能

```javascript
// 在 src/main/everything-search.js 中添加新的搜索方法
async customSearch(query, options) {
  // 实现新的搜索逻辑
}
```

#### 2. 添加新的UI组件

```vue
<!-- 在 src/renderer/components/ 中创建新组件 -->
<template>
  <!-- 组件模板 -->
</template>

<script>
export default {
  name: 'NewComponent'
}
</script>
```

#### 3. 添加新的IPC通信

```javascript
// 在 src/main/main.js 中添加IPC处理器
ipcMain.handle('new-feature', async (event, data) => {
  // 处理新功能
});

// 在 src/main/preload.js 中暴露API
contextBridge.exposeInMainWorld('electronAPI', {
  newFeature: (data) => ipcRenderer.invoke('new-feature', data)
});
```

### 构建与发布

#### 开发构建

```bash
npm run dev          # 启动开发环境
npm run build        # 构建Vue前端
```

#### 生产构建

```bash
npm run build:all    # 完整构建（前端+Electron）
npm run dist         # 打包为安装程序
```

#### 构建产物

- `dist-vue/` - Vue前端构建文件
- `release/` - Electron应用安装包

### 项目特色

#### 🔐 安全设计

- 禁用 Node.js 集成
- 启用上下文隔离
- 使用预加载脚本安全通信
- 自动生成随机用户名密码保护HTTP服务
- 安全的凭据管理和存储

#### 📊 性能优化

- Vue 3 Composition API 提升性能
- Vite 快速开发和构建
- 搜索结果虚拟滚动（计划中）
- 智能缓存机制
- 优化的文件搜索算法

#### 🎨 界面设计

- 自定义标题栏
- 现代化 UI 设计
- 响应式布局
- 玻璃态效果和渐变设计
- 微交互动画
- 深色/浅色主题支持（计划中）
- 系统托盘集成
- 独立调试窗口

#### 🌐 多平台支持

- Windows 桌面应用
- Web 在线版本
- 多语言界面（10种语言）
- 国际化日期和时间格式

## 📄 许可证

MIT License - 详见 [LICENSE](LICENSE) 文件

## 🤝 贡献指南

我们欢迎所有形式的贡献！

### 贡献方式

- 🐛 **报告问题**: 发现 Bug 请提交 Issue
- 💡 **功能建议**: 有好想法请在 Discussions 中讨论  
- 🔧 **代码贡献**: Fork 项目并提交 Pull Request
- 📚 **文档改进**: 帮助完善文档和示例

### 提交 Pull Request

1. Fork 本仓库
2. 创建功能分支 (`git checkout -b feature/amazing-feature`)
3. 提交更改 (`git commit -m 'Add amazing feature'`)
4. 推送分支 (`git push origin feature/amazing-feature`)
5. 创建 Pull Request

### 开发规范

- 遵循现有代码风格
- 添加必要的注释
- 更新相关文档
- 确保测试通过

## 🆘 支持与反馈

### 获取帮助

- 📖 **查阅文档**: 首先查看本 README 和相关文档
- 🔍 **搜索问题**: 在 Issues 中搜索是否有类似问题
- 💬 **提交问题**: 详细描述问题并提供必要信息

### 联系方式

- **GitHub Issues**: 报告 Bug 和功能请求
- **GitHub Discussions**: 技术讨论和问答
- **Email**: 紧急问题联系开发者

### 问题反馈模板

提交问题时请包含：

- 操作系统版本
- Everything 版本
- 应用版本
- 详细的问题描述
- 重现步骤
- 错误截图（如有）
