# Everything AI Chat - 智能文件搜索客户端（支持10种语言）

[**English**](./README-en.md) | 中文

一个现代化的 Everything 搜索客户端，将 AI 智能与极速本地搜索完美结合。支持自然语言查询，自动转换为 Everything 精确搜索语法，让文件搜索变得前所未有的简单和高效。

## 🌟 Star History

**开发不易，求个小星星✨**

[![Star History Chart](https://api.star-history.com/svg?repos=MaskerPRC/everything-ai-chat&type=Date)](https://star-history.com/#MaskerPRC/everything-ai-chat&Date)

## 👣示例

<img width="1800" height="1200" alt="image" src="https://github.com/user-attachments/assets/27495687-79cb-4389-a747-92a17a5cb54f" />

<img width="1800" height="1200" alt="image" src="https://github.com/user-attachments/assets/e03e671e-05d3-44f5-959e-9e874c614c3e" />

<img width="1800" height="1200" alt="image" src="https://github.com/user-attachments/assets/bc22ae96-8a62-4095-a564-ab2008635c4c" />

<img width="2512" height="1320" alt="image" src="https://github.com/user-attachments/assets/ded521b6-1c63-4988-aaf3-e4c1ad71117e" />

## 👀欢迎加入微信交流群

<https://100.agitao.net/>

![100个AI产品交流群](https://proxy.agitao.me/img)

## ✨ 核心特性

### 🔧 智能自动化连接 (技术亮点)

- **一键连接Everything**: 自动搜索Everything安装位置，无需手动配置
- **多策略搜索算法**: 通过注册表、常见路径、桌面快捷方式等多种策略定位安装位置
- **智能进程管理**: 采用优雅关闭→强制终止→高级终止的三级进程管理策略
- **自动端口发现**: 智能寻找可用端口，避免端口冲突
- **配置文件自动化**: 自动修改Everything配置，支持配置备份和恢复
- **安全凭据生成**: 自动生成随机用户名密码，确保连接安全性

### 🧠 AI 智能搜索

- **自然语言理解**: 输入"今天的PDF文件"、"大于10MB的视频"等自然语言，AI自动转换为精确搜索语法
- **OpenAI 集成**: 支持 GPT-3.5/GPT-4 模型，智能理解复杂搜索意图
- **本地优化**: 即使没有AI配置也能通过本地规则优化搜索查询

### ⚡ 极速搜索体验

- **Everything 引擎**: 基于世界上最快的文件搜索引擎Everything
- **实时结果**: 毫秒级搜索响应，支持大容量硬盘
- **智能建议**: 提供搜索建议和历史记录快速访问

### 🎯 精准结果展示

- **多维度排序**: 按文件名、路径、大小、修改时间、创建时间等多维度排序
- **文件类型识别**: 自动识别文件类型并显示对应图标（文档📄、图片🖼️、视频🎬等）
- **详细信息**: 显示文件大小、修改时间、创建时间、访问时间、属性等完整信息

### 🎨 现代化界面

- **自定义标题栏**: 无边框设计，集成窗口控制按钮
- **实时状态显示**: Everything连接状态实时监控
- **搜索历史**: 自动保存并智能管理搜索历史（最多50条）
- **响应式布局**: 自适应窗口大小，支持最小化到800x600
- **玻璃态效果**: 现代化的毛玻璃效果和渐变设计
- **系统托盘**: 系统托盘集成，方便窗口管理
- **调试窗口**: 独立的调试窗口，支持流式AI响应调试
- **文件上下文菜单**: 丰富的文件操作菜单，支持文件类型特定操作
- **列调整功能**: 可调整的文件列表列宽，支持本地存储持久化

## 技术栈

- **前端**: Vue 3 + Vite
- **后端**: Electron + Node.js
- **数据库**: SQLite (搜索历史存储)
- **AI服务**: OpenAI GPT API
- **搜索引擎**: Everything HTTP API
- **状态管理**: Vue 3 Composition API
- **国际化**: Vue I18n (支持10种语言)
- **样式**: CSS3 + 现代化UI设计
- **构建工具**: Vite + electron-builder

## 系统要求

- Windows 7/8/10/11
- Everything 软件 (1.4.1+)
- Node.js 16+
- 网络连接 (用于AI功能和自动更新)

## 安装步骤

### 1. 安装Everything

1. 下载并安装 [Everything](https://www.voidtools.com/)
2. 启动Everything软件
3. 进入 `工具` → `选项` → `常规`
4. 勾选 `启用HTTP服务器`
5. 确认端口为80 (默认)

**或者使用一键连接功能**：

- 启动应用后，在设置中点击"一键连接Everything"
- 系统会自动检测Everything安装位置并配置HTTP服务
- 支持自动端口发现和安全凭据生成

### 2. 克隆项目

```bash
git clone https://github.com/your-repo/everything-ai-chat.git
cd everything-ai-chat
cd client
```

### 3. 安装依赖

```bash
npm install
```

### 4. 配置OpenAI

如需使用AI自然语言转换功能，需要配置OpenAI API:

1. 启动应用后点击右下角设置按钮
2. 输入你的OpenAI API Key
3. 选择合适的模型 (推荐GPT-3.5 Turbo)
4. 可自定义系统提示词以优化AI转换效果
5. 支持本地部署的AI服务（无需API Key）

## 运行应用

### 开发模式

```bash
# 安装依赖
npm install

# 启动开发环境
npm run dev
```

### 生产构建

```bash
npm run build
npm run build:electron
```

---

⭐ 如果这个项目对你有帮助，请考虑给它一个 Star！

💝 感谢所有贡献者的努力！
