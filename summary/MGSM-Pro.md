# MGSM-Pro: A Simple Strategy for Robust Multilingual Mathematical推理 Evaluation

**论文信息**：
- 作者：Tianyi Xu, Kosei Uemura, Alfred Malengo Kondoro, Tadesse Destaw Belay, Catherine Nana Nyaah Essuman, Ifeoma Okoh, Ganiyat Afolabi, Ayodele Awokoya, David Ifeoluwa Adelani
- 发表/来源：arXiv:2601.21225（v2 2026年4月28日）
- 时间：2026年1月
- 链接：https://arxiv.org/abs/2601.21225

## 研究背景与动机

LLM在数学推理上进步巨大，但多语言评估基准在难度和时效性上落后于英语。GSM-Symbolic（Mirzadeh et al., 2025）发现在同一问题的不同实例化（改变名字、数字、无关上下文）上，模型表现高方差——但该发现仅限英语。MGSM-Pro将此发现扩展到多语言场景。

## 核心方法/贡献

1. **MGSM-Pro 数据集**：基于 MGSM 数据集，结合 GSM-Symbolic 方法
   - 每个 MGSM 问题生成5个实例化：改变名字、数字和无关上下文
   - 两步构建：(1) 在英语中构建可替换模板 (2) LLM翻译 + 人工验证
2. **关键发现**：
   - 低资源语言（LRL）在数字实例化变化时性能骤降，部分情况降幅超过 -20.0
   - 高资源语言的鲁棒性不一定能迁移到低资源语言
   - 排行榜排名在5实例平均后可能大幅变动（如 Gemini 2.5 Flash 从第3降至第7）
3. **建议**：数学推理评估应至少使用同一问题的5个数字变体实例

## 实验与结果

- 评估覆盖9种语言（含高资源和低资源）
- Gemini 3.0 Pro 和 Gemini 3.5 Flash 对变化更鲁棒
- 小模型（Gemma 3 4B）和旧模型（Llama 3 70B）难以保持准确率
- 专有模型：Gemini 2.5 Flash 和 GPT-4.1 对数字变化较不鲁棒；Gemini 3.0 Pro 更鲁棒
- 开源模型：GPT-OSS 120B 和 DeepSeek v3 鲁棒性更强

## 数据集详情

- **规模**：MGSM 原始问题 × 5个实例化（名字+数字+无关上下文变体）
- **语言覆盖**：9种语言（类型学多样性选择）
- **构建方法**：英语模板构建 → LLM翻译 → 人工验证
- **许可协议**：将在论文接受后在 HuggingFace 公开发布
- **数据质量**：人工验证翻译质量

## 局限性

- 仅覆盖9种语言
- 基于 MGSM 小学数学题，难度有限
- 模板化变体可能无法捕捉更深层的语言理解问题

## 对多语言数据集领域的意义

揭示了多语言数学推理评估中的一个关键问题：单次评估结果不可靠。低资源语言在数字变化时的高方差意味着现有基准排名可能严重失真。建议的5实例评估策略简单易行，可显著提升多语言数学推理评估的可靠性。

## 关键要点

- 将GSM-Symbolic的高方差发现扩展到多语言场景
- 低资源语言在数字变化时性能降幅可达 -20.0
- 高资源语言的鲁棒性不可迁移到低资源语言
- 排行榜排名可能在5实例平均后大幅变动（Gemini 2.5 Flash: 3rd→7th）
- 建议：每个问题至少5个数字变体实例以获得可靠评估
