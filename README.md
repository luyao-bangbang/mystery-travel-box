# 🎁 盲盒旅行规划师 / Mystery Travel Box

> **2026 飞猪 AI 旅行创新大赛参赛作品**

[在线 Demo（真实飞猪数据）](https://luyao-bangbang.github.io/mystery-travel-box/)

一款基于阿里云百炼平台 + 飞猪官方 Skill 的 AI 旅行智能体。告别选择困难症——用户只需提供预算、时间和偏好，AI 就会生成 **6 个风格各异的盲盒行程**，选一个数字，当场揭晓完整方案。

## ✨ 核心体验

```
你说：想出去旅游，但不知道去哪
我说：给你 6 个盲盒，选一个拆开 🎁

→ 2-3 轮对话采集偏好
→ 飞猪真实数据生成 6 套方案
→ 6 张线索卡片，凭直觉选数字
→ 当场揭晓完整行程 + 费用明细
→ 不满意？换一个盲盒再揭晓
→ 行前锦囊一键出发
```

## 🎮 产品亮点

### 6 选 1 盲盒机制
- AI 根据画像生成 6 个差异化的盲盒方案
- **极简线索卡**：每个盲盒只展示 emoji + 一个抽象关键词（如 "🌶 辣味"、"🏖 海风"、"🎭 古韵"），凭直觉选数字
- **当场揭晓**：选中后立即展示完整行程 + 费用明细，可直接预订
- **已拆封追踪**：拆过的盲盒标记为 "已拆封"，不能重复拆开，保持探索感

### 反馈重生机制
- 不满意当前盲盒？说「换一个」继续拆未开封的盲盒
- 6 个都不喜欢？输入「反馈」+ 偏好调整，AI 重新生成 6 个新盲盒
- 所有已拆封的盲盒会被标记，确保每次都是新鲜体验

### 飞猪真实数据
- 机票/高铁价格来自飞猪实时搜索
- 酒店评分和价格真实可查
- 景点信息和门票价格实时更新
- 所有方案预算可验证，不编造数据

### 行前锦囊
- 定制行李清单 + 当地人私藏玩法 + 朋友圈文案

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

打开 [`demo/blind-box-demo.html`](demo/blind-box-demo.html) 查看完整的盲盒旅行体验演示。

所有数据均来自飞猪 FlyAI 实时搜索结果，包括真实机票、酒店、景点信息和预订链接。

在线体验：https://luyao-bangbang.github.io/mystery-travel-box/

## 🛠 技术架构

- **平台**：阿里云百炼 Managed Agent
- **模型**：Qwen（均衡模式）
- **数据源**：飞猪官方 Skill（机票/酒店/景点/度假产品真实数据）
- **交互模式**：多轮对话 + 结构化输出 + 工具调用

## 📄 License

MIT
