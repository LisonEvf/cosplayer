# Cosplayer

> AI Agent 动态角色切换 - 按需创建专家视角

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)](https://github.com/LisonEvf/cosplayer)
[![README EN](https://img.shields.io/badge/README-English-blue.svg)](README_EN.md)

## Cosplayer 是什么？

Cosplayer 是一个 AI agent 技能，通过 **动态角色切换** 来解决复杂问题。不维护固定的角色列表，而是在真正需要时创建临时的专家视角。

### 核心理念

**不预设。按需创建。**

- ❌ 维护固定角色列表
- ✅ 根据问题动态创建角色
- ❌ 简单问题也切换角色
- ✅ 只在真正需要时切换

## 核心特性

- 🎭 **动态角色创建** - 按需创建专家角色
- 🤔 **智能切换逻辑** - AI自动判断何时需要切换
- 🚀 **轻量级** - 仅6.4KB，最小化token开销
- 📚 **实用示例** - 包含真实使用场景
- 🔧 **易于集成** - 兼容任何AI agent系统

## 安装

### 方法1：直接安装

```bash
# 下载skill文件
wget https://github.com/LisonEvf/cosplayer/releases/download/v1.0.0/cosplayer.skill

# 安装到skills目录
mkdir -p ~/.npm-global/lib/node_modules/openclaw/skills/
unzip cosplayer.skill -d ~/.npm-global/lib/node_modules/openclaw/skills/
```

### 方法2：从源码安装

```bash
git clone https://github.com/LisonEvf/cosplayer.git
cd cosplayer
# 复制到你的skills目录
```

### 方法3：ClawHub（即将支持）

```bash
clawhub install cosplayer
```

## 快速开始

### 何时切换角色

#### ✅ 应该切换

1. **问题超出通用知识**
   - GDPR合规、高频交易、法律问题

2. **多个冲突优先级**
   - 速度vs质量、增长vs利润

3. **用户明确要求特定视角**
   - "从安全角度分析"
   - "像创业公司创始人那样思考"

4. **当前方法碰壁**
   - 尝试通用方案但失败
   - 问题需要专业框架

#### ❌ 不应切换

1. **通用知识足够**
   - "如何居中div"
   - "SQL和NoSQL的区别"

2. **问题简单直接**
   - "修复这个bug"
   - "写一个函数..."

3. **已有足够上下文**
   - 理解领域知识
   - 专业框架无价值

4. **用户要快速答案**
   - 角色切换增加认知负担
   - 简洁胜过深度

## 使用示例

### 示例1：CCPA合规（需要切换）

**用户**: "我们的应用需要符合CCPA，该怎么办？"

**AI判断**: YES，需要法律专业知识

**创建角色**: "隐私合规专家"

```
【角色切换：隐私合规专家】

**CCPA合规框架**:

1. **数据清单**
   - 识别所有收集的个人信息
   - 标注数据来源和用途

2. **用户权利实现**
   - 访问权: 提供数据导出
   - 删除权: 实现数据删除流程
   - 选择退出权: "Do Not Sell"机制

3. **技术措施**
   - Cookie同意管理
   - 隐私政策更新

【角色恢复：决策者】

第一步：做数据清单，第二步：咨询律师确认细节
```

### 示例2：简单问题（无需切换）

**用户**: "Python怎么读JSON文件？"

**AI判断**: NO，通用知识足够

```python
import json

with open('file.json', 'r') as f:
    data = json.load(f)

print(data)
```

### 示例3：市场战略（需要切换）

**用户**: "是否应该进入东南亚市场？"

**AI判断**: YES，战略复杂度高

**创建角色**: "区域战略负责人"

```
【角色切换：区域战略负责人】

**东南亚市场评估**:

1. **市场规模**
   - TAM: 6.5亿人口
   - 互联网渗透率: 75%+

2. **竞争格局**
   - Singapore: 成熟但竞争激烈
   - Indonesia: 增长最快
   - Vietnam: 蓝海但基建弱

3. **进入策略**
   - Phase 1: Singapore (测试)
   - Phase 2: Indonesia (规模)

【角色恢复：决策者】

建议先做新加坡MVP验证，3个月后决定
```

## 工作原理

### 决策流程

```
问题到来
     ↓
AI通用能力够用？
     ↓
   是 → 直接解决
     ↓
    否
     ↓
需要专家视角？
     ↓
   是 → 创建角色 → 切换 → 解决 → 返回
     ↓
    否
     ↓
直接解决
```

### 角色创建步骤

1. **识别专业缺口**
   - "什么专家能更好解决这个问题？"

2. **定义角色特征**
   - 角色名
   - 核心问题
   - 思维模型
   - 盲点

3. **切换格式**
   ```
   【角色切换：{角色名}】

   [应用角色视角和框架]

   【角色恢复：决策者】
   ```

4. **提供专家方案**
   - 使用领域术语
   - 应用相关框架
   - 给可操作建议

## 文件结构

```
cosplayer/
├── SKILL.md (7.3KB)
│   ├── 核心理念
│   ├── 何时切换
│   ├── 决策流程
│   ├── 角色创建指南
│   └── 实际案例
├── references/
│   └── roles.md (5.6KB)
│       ├── 创建框架
│       ├── 角色示例
│       ├── 反模式
│       └── 角色库（可选）
├── clawhub.json (442B)
├── README.md (中文版)
├── README_EN.md (英文版)
└── LICENSE
```

## 反模式

### ❌ 为一切创建角色

**错误**:
- "帮我格式化JSON" → 切换到"数据格式专家"
- "2+2等于几？" → 切换到"数学家"

**正确**:
- 这些是简单任务 → 直接回答

### ❌ 重用相同的通用角色

**错误**:
- 每个技术问题 → "技术架构师"
- 每个商业问题 → "商业策略师"

**正确**:
- 数据库迁移 → "数据库架构师"
- API设计 → "API设计师"
- 扩展策略 → "平台架构师"

### ❌ 过度定义角色

**错误**: 解决前写500字角色定义

**正确**: 快速心理模型，然后解决

### ❌ 长时间停留在角色中

**错误**: 整个对话保持"财务分析师"

**正确**: 切换 → 回答 → 返回基础角色

## 使用场景

### 对AI Agent

- ✅ 按需获取专家视角
- ✅ 避免过度工程化
- ✅ 保持响应简洁
- ✅ 灵活适应问题

### 对用户

- ✅ 更专业的解决方案
- ✅ 更快的简单问题响应
- ✅ 更少的不必要切换
- ✅ 更清晰的逻辑

## 技术细节

- **大小**: 6.4KB
- **文件**: 3个（SKILL.md + roles.md + clawhub.json）
- **格式**: Markdown + JSON
- **依赖**: 无
- **兼容性**: OpenClaw, ClawHub

## 贡献

欢迎贡献！请随时提交Pull Request。

1. Fork本仓库
2. 创建功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 打开Pull Request

## 路线图

- [ ] v1.1 - 添加更多领域示例
- [ ] v1.2 - 优化角色创建模板
- [ ] v1.3 - 多语言支持
- [ ] v2.0 - 角色持久化（可选）

## 许可证

本项目采用MIT许可证 - 详见 [LICENSE](LICENSE) 文件。

## 作者

- **LisonEvf** - [GitHub](https://github.com/LisonEvf)

## 致谢

- 受AI agent需要按需获取专业知识的启发而创建
- 为OpenClaw社区用❤️构建

---

**🐦‍🔥 让AI在需要时成为专家，在不需要时保持简洁。**
