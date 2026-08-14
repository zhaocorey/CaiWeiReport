# PolyMath: Evaluating Mathematical Reasoning in Multilingual Contexts

**论文信息**：
- 作者：Yiming Wang, Pei Zhang, Jialong Tang, Haoran Wei, Baosong Yang, Rui Wang 等（Qwen Team, Alibaba Group + Shanghai Jiao Tong University）
- 发表/来源：arXiv:2504.18428（NeurIPS 2025收录，Published 2025-09-19）
- 时间：2025年4月（v4 2025年11月2日）
- 链接：https://arxiv.org/abs/2504.18428
- 代码：https://github.com/QwenLM/PolyMath
- 数据集：https://hf.co/datasets/Qwen/PolyMath

## 研究背景与动机

推理LLM（OpenAI o1, DeepSeek R1等）在复杂推理上取得突破，但多语言数学推理评估仍不充分。现有基准要么英语/中文为主，要么仅覆盖少量语言。PolyMath由Qwen团队构建，旨在建立全面的多语言数学推理基准。

## 核心方法/贡献

1. **PolyMath 基准**：多语言数学推理评估数据集
   - 覆盖18种高资源语言
   - 4级难度数学题（从小学到竞赛级）
   - 多语言题目来源：翻译自高质量英语数学题

2. **广泛评估**：
   - 评估20+个推理和非推理LLM
   - 推理模型：Qwen-3-235B-A22B-Thinking, Deepseek-R1-671B, OpenAI-o3-mini, Gemini-2.5-pro 等
   - 非推理模型：GPT-4.5-Preview, Claude-3.7-sonnet, Qwen-2.5-72B 等

3. **关键发现**：
   - 英语和中文性能最高，其他语言存在明显差距
   - 推理模型在跨语言上比非推理模型更一致
   - 不同语言家族的脚本差异（拉丁/非拉丁）影响性能

## 实验与结果

- 20+模型在18种语言上的全面评估
- 可视化雷达图展示各语言性能分布
- Qwen-3-235B-Thinking 和 OpenAI-o3-mini-medium 表现最优
- 推理模型相比非推理模型在多语言上更一致
- 非拉丁文字语言（阿拉伯语、泰语等）通常表现更低

## 数据集详情

- **规模**：多语言数学题，4级难度
- **语言覆盖**：18种语言（en, zh, es, de, fr, it, pt, ru, ja, ko, vi, th, ms, id, bn, ar, te, sw）
- **构建方法**：高质量英语数学题翻译 + 验证
- **许可协议**：开源（HuggingFace公开）
- **数据质量**：Qwen团队构建，高质量控制

## 局限性

- 18种语言限于高资源语言（已被PluraMath扩展到36种）
- 翻译构建可能引入语义偏差
- 部分语言的题目可能不够自然

## 对多语言数据集领域的意义

PolyMath是首个由工业级AI团队（Qwen/阿里）构建的大规模多语言数学推理基准，其4级难度设计和广泛模型评估为社区提供了重要参考。已被NeurIPS 2025收录，成为PluraMath等后续工作的基础。开源发布促进了多语言推理研究的快速发展。

## 关键要点

- Qwen团队（阿里）构建的多语言数学推理基准
- 18种高资源语言，4级难度数学题
- NeurIPS 2025收录，已被PluraMath扩展到36种语言
- 20+推理/非推理LLM的全面评估
- 英语和中文性能最高，非拉丁文字语言通常更低
- 推理模型比非推理模型在多语言上更一致
- 开源：https://hf.co/datasets/Qwen/PolyMath
