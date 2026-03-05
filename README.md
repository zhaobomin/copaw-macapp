# CoPaw Desktop for macOS

CoPaw 是一款**本地运行的 AI 助手桌面应用**，专为 macOS 设计。它将大语言模型能力带到你的个人电脑，无需依赖云端服务，保护数据隐私的同时提供强大的 AI 辅助功能。

## CoPaw 是什么？

CoPaw 是一个**个人 AI 工作台**，你可以：

- **与 AI 对话**：接入多种大语言模型（通义千问、DeepSeek、GPT 等）进行智能对话
- **管理知识库**：创建技能、上传文档，让 AI 基于你的私有知识回答问题
- **自动化工作流**：设置定时任务，让 AI 自动执行重复性工作
- **多平台集成**：连接钉钉、飞书、Discord 等渠道，将 AI 能力扩展到团队协作
- **MCP 扩展**：通过 Model Context Protocol 连接外部工具和服务

**核心特点**：所有数据保存在本地，API 密钥由你掌控，代码开源可审计。

---

## 下载安装

### 1. 选择适合你的版本

| 版本 | 适用机型 | 文件大小 | 下载链接 |
|------|---------|---------|---------|
| **Apple Silicon (M1/M2/M3/M4)** | MacBook Air/Pro, Mac mini, iMac, Mac Studio (2020年后) | 116 MB | [CoPaw-arm64.dmg](https://github.com/zhaobomin/copaw-macapp/releases/download/v0.0.4/CoPaw-arm64.dmg) |
| **Intel (x86_64)** | MacBook Air/Pro, iMac, Mac mini, Mac Pro (Intel 处理器) | 118 MB | [CoPaw-x86_64.dmg](https://github.com/zhaobomin/copaw-macapp/releases/download/v0.0.4/CoPaw-x86_64.dmg) |

**如何确认芯片类型**：
点击屏幕左上角  → "关于本机"
- 显示 "Apple M1/M2/M3/M4" → 下载 **arm64** 版本
- 显示 "Intel" → 下载 **x86_64** 版本

### 2. 安装步骤

1. **下载 DMG**：点击上方链接下载对应版本的 `.dmg` 文件
2. **打开 DMG**：双击下载的文件，会弹出一个窗口显示 CoPaw 应用
3. **拖拽安装**：将 **CoPaw** 图标拖拽到 **Applications（应用程序）** 文件夹
4. **启动应用**：从启动台或 Applications 文件夹打开 CoPaw

### 3. 首次运行授权

由于 CoPaw 未经过 Apple 官方公证，首次打开时会显示安全警告：
> "无法打开 CoPaw，因为无法验证开发者"

**解决方法**（二选一）：
- **方法 A**：前往 **系统设置 → 隐私与安全性**，找到 "已阻止使用 CoPaw"，点击 **"仍要打开"**
- **方法 B**：按住 **Control 键**，点击 CoPaw 应用图标，选择 **"打开"**

---

## 快速开始

### 第一步：配置 AI 模型

1. 打开 CoPaw，点击左侧菜单 **"模型"**
2. 选择一个提供商（如 DashScope、OpenAI、ModelScope、Coding Plan）
3. 点击 **"设置"** 按钮，输入你的 API 密钥
4. 点击 **"保存"**
5. 在页面顶部 **"LLM 配置"** 区域，选择刚才配置的提供商和模型
6. 点击 **"保存"** 激活模型

**支持的模型提供商**：
- **DashScope**（阿里云）：通义千问系列
- **OpenAI**：GPT-4、GPT-3.5
- **ModelScope**（魔搭社区）：开源中文模型
- **Ollama**：本地运行开源模型（需先安装 Ollama）
- **Coding Plan**（阿里云百炼）：专为开发者优化的模型服务
- **自定义**：支持任何 OpenAI 兼容 API

#### Coding Plan Token 申请

1. **访问阿里云百炼控制台**：[https://bailian.console.aliyun.com/cn-beijing/?tab=doc#/doc/?type=model&url=3005961](https://bailian.console.aliyun.com/cn-beijing/?tab=doc#/doc/?type=model&url=3005961)
2. **登录阿里云账号**：如果没有账号，请先注册
3. **进入 Coding Plan 页面**：在控制台导航栏中找到 "Coding Plan" 或相关入口
4. **创建 API 密钥**：
   - 点击 "API 密钥管理" 或类似选项
   - 点击 "创建密钥" 按钮
   - 保存生成的 Access Key ID 和 Access Key Secret
5. **在 CoPaw 中配置**：
   - 选择 "Coding Plan" 提供商
   - 输入生成的 API 密钥
   - 保存并激活模型

**注意**：Coding Plan 提供免费额度，用完后将自动转为按量付费，请及时充值以保障服务持续。

### 第二步：开始对话

1. 点击左侧菜单 **"对话"**
2. 在底部输入框输入问题，按 Enter 发送
3. AI 会基于你配置的模型进行回复

### 第三步：探索更多功能

| 功能 | 说明 |
|------|------|
| **技能** | 创建可复用的 AI 技能模板，如文案生成、代码审查 |
| **工作区** | 上传文件（PDF、Word、代码等），让 AI 基于文档内容回答 |
| **定时任务** | 设置 Cron 表达式，让 AI 在指定时间自动执行任务 |
| **渠道** | 将 AI 接入钉钉、飞书、Discord，实现群聊机器人 |
| **MCP** | 连接外部工具（如数据库、搜索引擎），扩展 AI 能力 |

---

## 常见问题

### Q: 为什么需要我自己提供 API 密钥？
**A**: CoPaw 是本地应用，不收集或存储你的 API 密钥。密钥保存在你电脑的 `~/.copaw.secret/` 目录中，由你完全掌控。这种模式既保护隐私，又让你自由选择性价比最高的模型提供商。

### Q: 可以离线使用吗？
**A**: 如果使用 Ollama 运行本地模型，可以完全离线使用。使用云端 API（如 DashScope、OpenAI）需要网络连接。

### Q: 数据存在哪里？会泄露吗？
**A**: 所有数据保存在本地：
- 配置文件：`~/.copaw/` 和 `~/.copaw.secret/`
- 聊天记录、上传文件：应用内工作区目录
- 不会上传任何数据到 CoPaw 服务器（CoPaw 没有服务器）

### Q: 如何更新到新版？
**A**: 直接下载新版本的 DMG，拖拽覆盖 Applications 中的旧版本即可。配置和数据会自动保留。

### Q: 遇到 Bug 怎么办？
**A**: 请在本仓库 [Issues](../../issues) 页面提交问题，描述：
1. macOS 版本和芯片类型（Intel/Apple Silicon）
2. CoPaw 版本号（菜单栏 → CoPaw → 关于）
3. 复现步骤和错误截图

---

## 系统要求

- **macOS 10.15 (Catalina)** 或更高版本
- **Apple Silicon 版本**：macOS 11.0+ 推荐
- **Intel 版本**：macOS 10.15+
- **存储空间**：安装包约 120MB，运行时需要额外空间存储数据

---

## 版本历史

### v0.0.4 (2026-03-05)
- 新增多窗口支持，可同时打开多个 CoPaw 窗口
- 页面切换时自动刷新数据
- 优化模型配置保存流程
- 修复后端服务生命周期管理
- 支持 Apple Silicon 和 Intel 双架构

### v0.0.3
- 优化应用签名流程
- 改进 DMG 安装界面

### v0.0.2
- 修复 PyInstaller 打包问题
- 优化加载页面体验

### v0.0.1
- 初始版本

---

## 开发构建

如需从源码构建：

```bash
# 克隆主仓库
git clone https://github.com/your-org/copaw.git
cd copaw

# 构建 Apple Silicon 版本
./build.sh

# 构建 Intel x86_64 版本
./build-x86.sh
```

构建产物位于 `dist/` 目录。

---

## 许可证

Copyright (c) 2024-2026 CoPaw Team. All rights reserved.

---

**喜欢 CoPaw？** 欢迎 Star ⭐ 本仓库，分享给需要的朋友！
