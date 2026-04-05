# Cosplayer

> AI Agent Dynamic Role Switching - Create expert perspectives on demand

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)](https://github.com/LisonEvf/cosplayer)

## What is Cosplayer?

Cosplayer is an AI agent skill that enables **dynamic role switching** for solving complex problems. Instead of maintaining a fixed list of roles, it creates ad-hoc expert perspectives when genuinely needed.

### Core Philosophy

**Don't preset. Create on demand.**

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
【Role Switch: Privacy Compliance Specialist】

**CCPA Compliance Framework**:

1. **Data Inventory**
   - Identify all personal information collected
   - Document data sources and purposes

2. **User Rights Implementation**
   - Access right: Provide data export
   - Deletion right: Implement data deletion flow
   - Opt-out right: "Do Not Sell" mechanism

3. **Technical Measures**
   - Cookie consent management
   - Privacy policy update

【Return to Base Role】

Step 1: Create data inventory, Step 2: Consult lawyer for details
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
【Role Switch: Regional Strategy Lead】

**Southeast Asia Market Assessment**:

1. **Market Size**
   - TAM: 650M population
   - Internet penetration: 75%+

2. **Competitive Landscape**
   - Singapore: Mature but competitive
   - Indonesia: Fastest growing
   - Vietnam: Blue ocean but weak infrastructure

3. **Entry Strategy**
   - Phase 1: Singapore (Test market)
   - Phase 2: Indonesia (Scale)

【Return to Base Role】

Recommend Singapore MVP validation first, decide in 3 months
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
   【Role Switch: {Role Name}】

   [Apply role's perspective and frameworks]

   【Return to Base Role】
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
├── README.md (Chinese)
├── README_EN.md (English)
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
