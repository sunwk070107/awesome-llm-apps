# 🎮 AI 3D PyGame Visualizer with DeepSeek R1

基于 DeepSeek R1 大模型的 AI 驱动 PyGame 代码生成与可视化系统。通过自然语言描述即可生成完整的 PyGame 游戏代码，并自动在浏览器中运行可视化效果。

### 🎓 FREE Step-by-Step Tutorial 
**👉 [Click here to follow our complete step-by-step tutorial](https://www.theunwindai.com/p/build-an-ai-3d-pygame-visualizer-with-deepseek-r1) and learn how to build this from scratch with detailed code walkthroughs, explanations, and best practices.**

## 📋 项目概述

该项目展示了 DeepSeek R1 模型在代码生成领域的强大能力，构建了一个完整的多智能体系统，包含以下核心功能：

- **自然语言到代码**：用户输入自然语言描述，系统自动生成可执行的 PyGame 代码
- **推理与解释**：DeepSeek Reasoner 提供详细的代码推理过程和解释
- **代码提取**：OpenAI GPT-4o 从推理内容中提取纯净代码
- **自动可视化**：浏览器自动化智能体将代码部署到 Trinket.io 并自动运行
- **直观界面**：基于 Streamlit 的交互式 Web 界面

## 🏗️ 系统架构

```
┌─────────────────────────────────────────────────────────────────┐
│                        用户界面 (Streamlit)                      │
└─────────────────────────────────────────────────────────────────┘
                              │
          ┌───────────────────┼───────────────────┐
          ▼                   ▼                   ▼
┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐
│  DeepSeek R1    │  │  OpenAI GPT-4o  │  │  Browser Agents │
│  (代码推理)      │  │  (代码提取)      │  │  (可视化执行)    │
└─────────────────┘  └─────────────────┘  └─────────────────┘
                              │
                              ▼
                    ┌─────────────────┐
                    │   Trinket.io    │
                    │  (PyGame运行环境)│
                    └─────────────────┘
```

### 核心组件

| 组件 | 作用 | 技术实现 |
|------|------|----------|
| **DeepSeek Reasoner** | 分析用户查询，生成带推理过程的代码 | DeepSeek API (`deepseek-reasoner` 模型) |
| **代码提取器** | 从推理内容中提取纯净 Python 代码 | Agno + GPT-4o |
| **浏览器智能体** | 自动化导航、代码输入、执行和查看 | browser-use + LangChain |
| **Web 界面** | 用户交互、代码展示、流程控制 | Streamlit |

## ✨ 功能特性

### 代码生成
- ✅ **自然语言描述转代码**：支持用中文或英文描述游戏需求
- ✅ **推理过程展示**：展示 DeepSeek R1 的完整推理思考过程
- ✅ **纯净代码提取**：自动提取可直接运行的 Python 代码

### 多智能体系统
- 🤖 **导航智能体**：自动导航到 Trinket.io PyGame 编辑器
- 🤖 **编码智能体**：等待用户输入代码到编辑器
- 🤖 **执行智能体**：点击运行按钮执行代码
- 🤖 **查看智能体**：查看运行结果

### 用户界面
- 🖥️ **Streamlit 交互式界面**
- 📱 **响应式布局**
- 🔑 **安全的 API Key 管理**（密码输入模式）
- 📋 **代码高亮展示**

## 🚀 快速开始

### 环境要求

- Python 3.8+
- 网络连接（用于调用 API 和浏览器自动化）
- 现代浏览器（Chrome 或 Edge）

### 安装步骤

1. **克隆仓库**
```bash
git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
cd awesome-llm-apps/advanced_ai_agents/autonomous_game_playing_agent_apps/ai_3dpygame_r1
```

2. **安装依赖**
```bash
pip install -r requirements.txt
```

3. **获取 API Key**
- 注册 [DeepSeek Platform](https://platform.deepseek.com/) 获取 API Key
- 注册 [OpenAI Platform](https://platform.openai.com/) 获取 API Key

4. **启动应用**
```bash
streamlit run ai_3dpygame_r1.py
```

5. **访问界面**
浏览器会自动打开，访问控制台输出的 URL（通常是 `http://localhost:8501`）

### 📦 依赖说明

| 依赖包 | 版本要求 | 说明 |
|--------|----------|------|
| `agno` | >= 2.2.10 | 轻量级 AI 代理框架 |
| `langchain-openai` | - | LangChain OpenAI 集成 |
| `browser-use` | - | 浏览器自动化工具 |
| `streamlit` | - | Web 应用框架 |

## 📖 使用方法

### 基本流程

1. **配置 API Key**：在左侧侧边栏输入 DeepSeek 和 OpenAI 的 API Key
2. **输入查询**：在文本框中用自然语言描述你想要创建的 PyGame 效果
3. **生成代码**：点击 "Generate Code" 按钮，系统会：
   - 调用 DeepSeek R1 进行推理
   - 展示推理过程
   - 提取并展示生成的代码
4. **生成可视化**：点击 "Generate Visualization" 按钮，系统会：
   - 自动打开浏览器导航到 Trinket.io
   - 输入代码并执行
   - 展示运行结果

### 查询示例

```
Create a particle system simulation where 100 particles emit from the mouse position and respond to keyboard-controlled wind forces
```

```
制作一个弹跳的彩色方块，当碰到屏幕边缘时改变颜色
```

```
创建一个简单的太空射击游戏，玩家控制飞船躲避障碍物
```

## 🔄 工作流程

### 阶段一：代码生成

1. **用户输入**：自然语言描述游戏需求
2. **DeepSeek R1 推理**：分析需求，生成带推理过程的代码
   - 使用 `deepseek-reasoner` 模型
   - 返回 `reasoning_content` 包含完整推理
3. **代码提取**：GPT-4o 从推理内容中提取纯净代码
   - 去除解释和格式标记
   - 返回可直接运行的 Python 代码
4. **结果展示**：在界面中展示推理过程和生成的代码

### 阶段二：可视化执行

1. **浏览器初始化**：创建浏览器上下文
2. **导航智能体**：访问 Trinket.io PyGame 编辑器
3. **编码智能体**：等待代码输入
4. **执行智能体**：点击运行按钮
5. **查看智能体**：观察运行结果

## 📁 项目结构

```
ai_3dpygame_r1/
├── ai_3dpygame_r1.py    # 主应用程序
├── requirements.txt     # Python 依赖
└── README.md            # 项目说明文档
```

### 文件说明

| 文件 | 说明 |
|------|------|
| `ai_3dpygame_r1.py` | Streamlit 主应用，包含所有业务逻辑和界面代码 |
| `requirements.txt` | 项目依赖列表 |
| `README.md` | 项目说明文档 |

## ⚠️ 注意事项

1. **API Key 安全**：请妥善保管您的 API Key，不要提交到版本控制系统
2. **网络要求**：需要稳定的网络连接以调用 API 和浏览器自动化
3. **浏览器兼容性**：推荐使用 Chrome 或 Edge 浏览器
4. **Trinket.io 限制**：免费版 Trinket.io 可能有运行时长限制
5. **代码质量**：生成的代码质量取决于查询描述的清晰度和模型能力

## 🔧 常见问题

**Q: 为什么代码生成失败？**
- 检查 API Key 是否正确配置
- 确保网络连接正常
- 尝试使用更清晰的描述

**Q: 可视化失败怎么办？**
- 检查浏览器是否正常安装
- 手动复制代码到 Trinket.io 运行
- 查看错误提示信息

**Q: 如何优化生成的代码？**
- 使用更详细的描述
- 明确指定功能需求
- 参考示例查询格式

## 📝 许可证

MIT License
