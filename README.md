# Cosplayer

> AI Agent Dynamic Role Switching - Create expert perspectives on demand

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)](https://github.com/LisonEvf/cosplayer)

## What is Cosplayer?

Cosplayer is an AI agent skill that enables **dynamic role switching** for solving complex problems. Instead of maintaining a fixed list of roles, it creates ad-hoc expert perspectives when genuinely needed.

### Core Philosophy

**不预设。按需创建。** (Don't preset. Create on demand.)

- ❌ Maintaining fixed role lists
- ✅ Creating ad-hoc roles based on actual problems
- ❌ Switching roles for simple questions
- ✅ Switching only when genuinely beneficial

## Features

- 🎭 **Dynamic Role Creation** - Create expert roles on-demand
- 🤔 **Smart Switching Logic** - AI determines when role switch is needed
- 🚀 **Lightweight** - Only 6.4KB, minimal token overhead
- 📚 **Practical Examples** - Real-world usage scenarios included
- 🔧 **Easy Integration** - Works with any AI agent system

## Installation

### Method 1: Direct Install

```bash
# Download the skill file
wget https://github.com/LisonEvf/cosplayer/releases/download/v1.0.0/cosplayer.skill

# Install to your skills directory
mkdir -p ~/.npm-global/lib/node_modules/openclaw/skills/
unzip cosplayer.skill -d ~/.npm-global/lib/node_modules/openclaw/skills/
```

### Method 2: From Source

```bash
git clone https://github.com/LisonEvf/cosplayer.git
cd cosplayer
# Copy to your skills directory
```

### Method 3: ClawHub (Coming Soon)

```bash
clawhub install cosplayer
```

## Quick Start

### When to Switch Roles

#### ✅ SHOULD Switch When:

1. **Problem exceeds general knowledge**
   - GDPR compliance, high-frequency trading, legal issues

2. **Multiple conflicting priorities**
   - Speed vs quality, growth vs profitability

3. **User explicitly requests specific viewpoint**
   - "Analyze from security perspective"
   - "Think like a startup founder"

4. **Current approach hitting walls**
   - General solutions don't fit
   - Need specialized framework

#### ❌ Should NOT Switch When:

1. **General knowledge suffices**
   - "How to center a div"
   - "Difference between SQL and NoSQL"

2. **Problem is straightforward**
   - "Fix this bug"
   - "Write a function..."

3. **Already have sufficient context**
   - Understand domain well
   - Specialized framework adds no value

4. **User wants quick answer**
   - Role switch adds cognitive overhead
   - Brevity beats depth

## Usage Examples

### Example 1: CCPA Compliance (Switch Needed)

**User**: "Our app needs to comply with CCPA, what should we do?"

**AI Decision**: YES, legal expertise required

**Created Role**: "Privacy Compliance Specialist"

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

### Example 2: Simple Question (No Switch)

**User**: "How do I read a JSON file in Python?"

**AI Decision**: NO, general knowledge sufficient

```python
import json

with open('file.json', 'r') as f:
    data = json.load(f)

print(data)
```

### Example 3: Market Strategy (Switch Needed)

**User**: "Should we expand to Southeast Asia?"

**AI Decision**: YES, high strategic complexity

**Created Role**: "Regional Strategy Lead"

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

## How It Works

### Decision Flow

```
Problem arrives
     ↓
Within general AI capabilities?
     ↓
   YES → Solve directly
     ↓
    NO
     ↓
Needs expert perspective?
     ↓
   YES → Create role → Switch → Solve → Return
     ↓
    NO
     ↓
Solve directly
```

### Role Creation Steps

1. **Identify expertise gap**
   - "What expert would solve this better?"

2. **Define role characteristics**
   - Role name
   - Core question
   - Mental models
   - Blind spots

3. **Switch format**
   ```
   【角色切换：{Role Name}】

   [Apply role's perspective and frameworks]

   【角色恢复：决策者】
   ```

4. **Provide expert solution**
   - Use domain-specific language
   - Apply relevant frameworks
   - Give actionable recommendations

## File Structure

```
cosplayer/
├── SKILL.md (7.3KB)
│   ├── Core philosophy
│   ├── When to switch
│   ├── Decision flow
│   ├── Role creation guide
│   └── Real-world examples
├── references/
│   └── roles.md (5.6KB)
│       ├── Creation framework
│       ├── Role examples
│       ├── Anti-patterns
│       └── Role library (optional)
├── clawhub.json (442B)
├── README.md
└── LICENSE
```

## Anti-Patterns to Avoid

### ❌ Creating Roles for Everything

**Wrong**:
- "Help me format JSON" → Switch to "Data Format Specialist"
- "What's 2+2?" → Switch to "Mathematician"

**Right**:
- These are simple tasks → Answer directly

### ❌ Reusing Same Generic Roles

**Wrong**:
- Every tech problem → "Technical Architect"
- Every business problem → "Business Strategist"

**Right**:
- Database migration → "Database Architect"
- API design → "API Designer"
- Scaling strategy → "Platform Architect"

### ❌ Over-Defining Roles

**Wrong**: Writing 500-word role definition before solving

**Right**: Quick mental model, then solve

### ❌ Staying in Role Too Long

**Wrong**: Remaining "Financial Analyst" for entire conversation

**Right**: Switch → Answer → Return to base persona

## Use Cases

### For AI Agents

- ✅ On-demand expert perspectives
- ✅ Avoid over-engineering
- ✅ Keep responses concise
- ✅ Flexibly adapt to problems

### For Users

- ✅ More professional solutions
- ✅ Faster simple question responses
- ✅ Fewer unnecessary switches
- ✅ Clearer logic

## Technical Details

- **Size**: 6.4KB
- **Files**: 3 (SKILL.md + roles.md + clawhub.json)
- **Format**: Markdown + JSON
- **Dependencies**: None
- **Compatibility**: OpenClaw, ClawHub compatible

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Roadmap

- [ ] v1.1 - Add more domain examples
- [ ] v1.2 - Optimize role creation templates
- [ ] v1.3 - Multi-language support
- [ ] v2.0 - Role persistence (optional)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

- **LisonEvf** - [GitHub](https://github.com/LisonEvf)

## Acknowledgments

- Inspired by the need for AI agents to access specialized expertise on-demand
- Built with ❤️ for the OpenClaw community

---

**🐦‍🔥 Let AI become an expert when needed, stay concise when not.**
