# 🎁 盲盒旅行规划师 / Mystery Travel Box

> **2026 飞猪 AI 旅行创新大赛参赛作品**

> 🎬 **在线 Demo（真实飞猪数据）：https://luyao-bangbang.github.io/mystery-travel-box/**

一款基于阿里云百炼平台 + 飞猪官方 Skill 的 AI 旅行智能体。用户只需提供预算、时间和偏好，即可获得一份密封的「盲盒行程」——目的地保密到最后一刻才揭晓。

## ✨ 核心体验

```
你说：想出去旅游，但不知道去哪
我说：交给我，给你一个惊喜 🎁

→ 2-3 轮对话采集偏好
→ 飞猪真实数据智能规划
→ 盲盒线索卡 + 惊喜值系统
→ 倒计时揭晓完整行程
→ 行前锦囊一键出发
```

## 🚀 快速体验

### 前置条件

- 阿里云账号（[注册](https://account.aliyun.com/register/register.htm)）
- 飞猪 FlyAI API Key（[申请](https://flyai.open.fliggy.com/)）

### 部署步骤

1. 前往 [阿里云百炼平台](https://bailian.console.aliyun.com/)，选择 **Managed Agent**
2. 创建智能体，使用默认配置
3. 将 [`src/system-prompt.md`](src/system-prompt.md) 的内容复制到 System Prompt
4. 在智能体会话中安装飞猪 Skill：
   ```
   npx skills add alibaba-flyai/flyai-skill
   ```
5. 配置环境变量：
   ```
   FLYAI_API_KEY=你的APIKey
   ```
6. 开始对话：`我想出去旅游，但不知道去哪`

详细部署指南见 [docs/deployment-guide.md](docs/deployment-guide.md)。

## 📁 项目结构

```
mystery-travel-box/
├── README.md                        # 本文件
├── src/
│   ├── system-prompt.md             # 智能体 System Prompt（核心）
│   ├── agent-config.json            # 智能体配置说明
│   └── demo-conversation.md         # Demo 对话脚本
├── demo/
│   └── blind-box-demo.html          # 真实数据 Demo 演示页面（可直接浏览器打开）
├── docs/
│   ├── deployment-guide.md          # 百炼平台部署指南
│   └── proposal.md                  # 参赛方案文档
└── screenshots/                     # Demo 截图
```

## 🎬 Demo 演示

- 🌐 **在线体验（推荐）**：https://luyao-bangbang.github.io/mystery-travel-box/
- 💻 **本地文件**：[`demo/blind-box-demo.html`](demo/blind-box-demo.html)（可直接浏览器打开）

所有数据均来自飞猪 FlyAI 实时搜索结果，包括真实机票（GJ8777 ¥310）、酒店（¥567）、5 个免费景点和预订链接。完整长沙 2 日游盲盒行程，总预算 ¥1,782 / ¥2,000。

## 🎮 核心功能

### 惊喜值系统
- 初始 100 点，每次「偷看」扣 30，「忍住不看」加 20
- 揭晓时根据惊喜值生成不同等级的「旅行预言」

### 双人/多人盲盒模式
- 情侣或朋友各自输入偏好
- 智能体综合生成「最大公约数」行程

### 行前锦囊
- 定制行李清单 + 当地人私藏玩法 + 朋友圈文案

## 🛠 技术架构

- **平台**：阿里云百炼 Managed Agent
- **模型**：Qwen-Max / Qwen-Plus
- **数据源**：飞猪官方 Skill（机票/酒店/景点/度假产品真实数据）
- **交互模式**：多轮对话 + 结构化输出 + 工具调用

## 📄 License

MIT
