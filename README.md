# FuncPulse 功能验证分析技能

FuncPulse是基于PRD和测试用例分析多代码仓库变更的高级测试验证工具，通过建立需求-用例-代码的完整追踪关系，验证每条测试用例是否满足预期，并生成标准化的业务测试验证报告。

## 核心功能

### 1. 需求追踪分析
- 从PRD或测试用例中提取关键需求点
- 建立需求与代码实现的映射关系
- 识别未覆盖的需求和潜在风险

### 2. 多仓库代码分析
- 自动识别和扫描多个代码仓库
- 分析跨仓库的代码变更影响
- 建立变更与需求的关联关系

### 3. 测试用例验证
- 验证每条测试用例的代码实现覆盖度
- 识别测试覆盖缺口和冗余用例
- 计算测试覆盖率和有效性指标

### 4. 缺陷分析与管理
- 识别和分类各种级别的缺陷
- 提供具体的复现步骤和修复建议
- 关联缺陷与具体需求和测试用例

### 5. 标准化报告生成
- 生成符合模板的Markdown格式报告
- 自动保存报告到本地reports目录
- 支持跨仓库的变更追踪

## 使用方法

### 基本使用

```bash
# 进入funcpulse目录
cd .joycode/skills/funcpulse

# 生成业务测试验证报告
node scripts/generate-validation-report.js <PRD或测试用例文件路径>

# 示例
node scripts/generate-validation-report.js requirements/ProductRequirements.md
node scripts/generate-validation-report.js test-cases/LoginTestCases.md
```

### 多仓库分析

```bash
# 指定多个仓库路径进行分析
node scripts/generate-validation-report.js requirements/ProductRequirements.md --repos ../repo1,../repo2,../repo3
```

### 使用npm脚本

```bash
# 使用npm脚本生成报告
npm run generate-report -- requirements/ProductRequirements.md
```

## 报告模板

业务测试验证报告遵循标准模板，包含以下部分：

1. **执行摘要** - 测试用例总数、覆盖率、关键发现
2. **需求-代码映射分析** - 需求与代码实现的映射关系
3. **测试用例验证结果** - 每条用例的验证结果
4. **未覆盖需求分析** - 未覆盖需求的详细分析
5. **缺陷列表** - 按严重程度分类的缺陷详情
6. **需求-用例-代码追踪矩阵** - 完整的追踪关系表
7. **建议** - 按优先级排序的改进建议

## 文件结构

```
funcpulse/
├── SKILL.md                  # 技能定义和核心指令
├── package.json             # 包配置和脚本定义
├── README.md                # 使用说明文档
├── scripts/                 # 可执行脚本
│   └── generate-validation-report.js  # 报告生成脚本
└── references/              # 参考文档
    ├── test-validation-report.md      # 报告模板规范
    ├── qa-analysis-methods.md         # 测试分析方法
    ├── multi-repo-analysis.md         # 多仓库分析指南
    └── test-case-traceability.md      # 用例追踪指南
```

## 本地存储

### 1. 早期建立追踪性
在项目初期就建立需求-用例-代码的追踪关系，避免后期补建的困难。

### 2. 持续维护追踪关系
随着需求和代码的变更，持续更新和维护追踪关系，确保其准确性。

### 3. 自动化追踪管理
尽可能使用工具和脚本自动化追踪关系的管理，减少人工工作量。

### 4. 定期验证完整性
定期检查追踪关系的完整性，确保所有需求都有对应的测试用例和代码实现。

### 5. 关注关键路径
优先关注核心业务功能的追踪关系，确保关键路径的完整性和准确性。

## 相关技能

- **风险分析** - 代码风险分析和漏洞检测
- **全栈守护者** - 功能测试和端到端测试
- **Playwright专家** - 自动化端到端测试
- **DevOps工程师** - CI/CD集成和质量门禁

## 技术支持

如有问题或建议，请联系FuncPulse开发团队。
