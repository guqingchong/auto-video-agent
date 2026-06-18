# AGENTS.md — 协作规则

## 任务路由（硬约束）
| 任务类型 | 目标Agent |
|---------|----------|
| 编码 | Claude Code |
| 审核 | CodeWhale |
| 测试 | Qwen Code |
| 文档 | Qwen Code |
| 编排 | Hermes |

## 开发流程
1. 编码 → Claude Code 实现
2. 审核 → CodeWhale 审查（P0必须修复）
3. 测试 → Qwen Code 编写+运行
4. 验收 → Hermes 逐条对照features.json

## API密钥规则
- 所有API密钥通过环境变量读取，禁止硬编码
- .env 文件加入 .gitignore
- 测试中使用mock，禁止真实API调用
